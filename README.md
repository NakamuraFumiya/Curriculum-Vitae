# 職務経歴書

## 基本情報

|key|value|
|---|-----|
|Name|中村郁哉(Fumiya Nakamura)|
|Qiita|[Nakamura Fumiya](https://qiita.com/NakamuraFumiya3)|
|zenn|[NakamuraFumiya](https://zenn.dev/nakamura_fumiya)|
|Twitter|[@NakamuraFumiya3](https://twitter.com/NakamuraFumiya3)|
|LeetCode|[fumiya3691](https://leetcode.com/u/fumiya3691/)|

## スキル
### 言語
- Golang
- Ruby
- SQL

### フレームワーク
- React
- Echo
- Ruby on Rails

## 強み
- チームなど全体感を見ながら動くことができること
- 意思決定のスピード感
- 実務で必要だと感じる技術を優先的にキャッチアップすること

## やったことはないが興味があるもの
- AWSなどのクラウドサービスを使ったサービス設計・運用

## 職務経歴
### 2025/07 - 現在: ハンディ株式会社
「高校生のキャリア選択をもっと豊かに」するべく、エンジニアとして「Handy進路指導室」の開発を担当する予定です。

### 2022/09 - 2025/06: 株式会社バニッシュ・スタンダード
バックエンドエンジニアとして、「STAFF START」のサーバーサイド開発に従事しました。
Golang、MySQLを使用した開発が多く、プロジェクトによってはReact, TypeScriptを使うこともありました。

#### SQS, Lambda, Elasticsearchを使用した非同期処理の実装、外部APIの実装(2024/12-2025/04)
コンテンツ一覧を返却する外部APIが必要になったので実装を担当しました。
直接RDBに問い合わせするのではなく、リクエストのフィルタリングや全文検索は得意なESに任せる方針であるため、コンテンツデータをESに追加する必要があり、非同期処理をSQS, Lambda, EventBridgeを使って実現しました。SQSやLambda自体はすでに既存で用意されていたので1から準備した訳ではなく一部改修しながら検証を進めました。
非同期処理に失敗した時の再処理をクラウドに任せるのか、自分達で一から実装するのかなどのアーキテクチャについて考えて形にする学びも得られて貴重な経験ができました。

GoのAPIはオニオンアーキテクチャを採用していますが、開発メンバーは3人で並行で進めていたこともあり、チーム内でコードの問題点など度々話が浮上しました。スケジュールとの兼ね合いもありますが、重要度の高いものは開発と並行してリファクタリングしつつ、議論を通じて技術的な学びも多かったと思います。

またチームの進め方として上手くいかなくなったこともありました。
具体的には今までカンバン方式で運用しており、具体的なチケットは課題タイトルの起票と少し補足がある程度でした。今回のプロジェクトから既存システムの考慮など深いドメイン知識が必要になることが求められたので実装の難易度が上がりました。メンバーが特定のタスクを抱え込んでしまうなど、課題の透明性が低い状態が続き、チームとして前に進んでいるのか停滞しているのか判断しにくい状況に陥りました。
そのため課題のリファインメントを行うようにして共通認識を作り、実装がしやすい状態を整えました。また課題の見積もりも行うことができたため、不確実性の高いタスクは事前に調査タスクを切ったり、課題分割するなどしてチーム活動が上手く進むように心がけました。
チームとしても前に進んでいる感覚、プロダクトオーナーとの合意形成などがスムーズに進むようになったため、色々と学びも多かったです。

#### 画像生成AIのAPI組み込み(2024/09-2024/11)
途中からチーム移動してプロジェクトに参画し、最終的には正社員としては自分1名、業務委託の方が2名の合計3名でバックエンド開発を行いました。
構成としては外部の画像生成APIをラップするAPIを作っていました。自分が参画した時点でテーブル設計・シーケンス図は一通りあったのですが、ビジネス的な制約から外部APIの仕様が変わることになり、完成していたAPIを3分の2ほど作り替えることになりました。
想定していない事態だったので、どこまで既存コードを生かせるか検討し、メンバーが早期に動けるように改めてテーブル設計・シーケンス図をfixし、チーム共有することで比較的そこまでスケジュール遅延することなく開発完了できました。

技術的な話だと、openapi.yml(swagger)でAPIの仕様の管理をしていたのですが、APIの仕様と実装がずれることが起きていたので、oapi-codegenを導入し、IFをコード自動生成に頼ることで実装ミスを防ぐことができました。
ソフトウェアアーキテクチャとしてオニオンアーキテクチャを採用していますが、アプリケーションサービス層がインフラストラクチャ層に依存するなど、原則を無視した開発段階のコードもあったりしたので、インタフェースに切り出してチーム共有して技術負債の解消を図ったりもしました。

また、フロント部分を他社に受託でお願いしていたので、API仕様や振る舞いに関する質問の回答および調査をメインで担当していました。

#### プロダクトロードマップに沿った新機能開発(2024/04)
4月から新しいチームが立ち上がり、中朝的なプロダクトロードマップに沿って新機能開発を担当しています。
今まではREST APIを作ることが多かったですが、今後gRPCの導入も視野に入れ、Connectというライブラリを使用したgRPC互換のAPIを実装し、本番のプロダクションコードに載せました。
ビジネス要件的にも不確実性の高い開発なため「より小さく市場に出す」を意識して、ビジネス側と密に連携をとって開発を進めています。

また、新規で実装する内部APIは基本的にはRESTではなくgRPCの通信に切り替えていきたい方針のため、学んだことを[zennの記事](https://zenn.dev/vs_blog/articles/c73f2957b328ad)にアウトプットして社内共有しました。

#### 分析DBサーバの廃止・移行作業(2023/10-2024/03)
分析DBサーバのコストカット・負債解消を狙い、DBサーバを統合するプロジェクトを担当しました。
移行先の新規テーブル設計に関しては社内のアーキテクトのレビューを受けながら進めました。
テーブル結合は基本的にコストが高いため、求められる要件からどこまで正規化するべきかチームで議論しながら進めたのでとても勉強になったと思います。

既存バッチやテーブル構成を読み解き、正しくリプレイスすることが求められましたので、集計SQLを作り既存と差分が出た場合はどちらがが正なのか、社内の有識者に確認したり、難しい場合はコードの背景やドメイン知識からあるべき仕様を考えてPdMに提案する形を取り、プロジェクトを推進しました。

#### 新管理画面リプレイス(2023/03-2023/09)
5~9人のスクラムでチーム開発をしていました。
具体的な業務内容としては、旧管理画面がRoRで作られていたのを、フロントはReact・ TypeScript、バックエンドはGoへリプレイス作業を担当しました。

苦労した部分・工夫した部分は、リプレイス対象の仕様理解のためのコードリーディングや、仕様変更を行う際の影響範囲調査です。

リプレイス対象の仕様理解で工夫した点は、仕様の理解が曖昧だと正しくリプレイスできないので、コードリーディングから現仕様を読み解きドキュメントにまとめてチームに共有・レビューしてもらう形で、チーム全体進捗の貢献を図りました。苦労した点は、コードが読みにくく量も多いので理解に苦労しました。ただ、苦労した分、人の書いたコードや意図を推測する力は鍛えられたと思います。

影響範囲調査で工夫した点は、リプレイスを進めていく上で明らかな技術的負債・仕様の負債は解消したかったので、仕様を変更した時の影響範囲調査をコードベース、DBのデータ構造、有識者への確認など柔軟に進めて、プロダクトオーナー・チームで意思決定しました。苦労した点は合意を取る上で情報を正しく分かりやすく伝えないといけないため、ドキュメントのまとめ方や粒度、仕様の提案の仕方、議論をするための前提情報のインプットなど、勉強になることが多かったです。

上司の「エンジニアは難しいことを簡単にする仕事だ」と言った言葉は今も大切にして、意識しています。


### 2020/08-2022/07 : 冒険社プラコレ
Webアプリケーションエンジニアとして、主に「プラコレウェディング」「ViKet Town」のサーバーサイド開発に従事していました。

#### 自社サービスのRailsバージョンアップ経験(2021/07-2021/08)
具体的にはgemのアップデート、バージョンアップの影響で動かなくなった古いコードのリプレイスなどです。
gemの依存関係や、既存のサービスの動きを壊さないようにコードを書き換えるなど、勉強になることが多かったです。バックエンドは主に1人で担当させてもらえたので、貴重な経験になりました。
バージョンは、Ruby2.2.2→3.0.1、Rails4.2.3→6.1.4に上げました。

##### 担当業務
- 要件定義・基本設計・詳細設計
- 実装・リリース・障害対応
- 開発環境改善(Docker化)
- API設計・開発
- RDBを使用したデータモデル設計
- Redisを用いたキャッシュ対応・性能改善
- Elasticsearchを使用した検索エンジンの最適化
- ActionCableを使用したアバター機能の実装


### 2019/04 - 2020/07 : 株式会社NSソリューションズ東京
#### ホストマシンのCPU使用率監視システムの構築
Elasticsearch、Logstash、GrafanaといったOSSを使用して、ホストマシンのCPU使用率監視システムを構築しました。部署で初めて導入するソフトウェアだったことから、私を含めた若手メンバー2人が中心となって、プロジェクトを進めてきました。課題として、OSSのバージョンアップの更新頻度が高く、参考になる記事が少ないことがありました。正しい記事を参照することが重要だと感じ、英語の公式マニュアルを参照し、検証を繰り返すことでシステムを作りきることができました。初めてのことが多い中で、先輩方のサポートも受けながら、若手中心で動くものを作った経験は大きな自信になりました。

##### 担当業務
- CPU使用率監視システムの構築
- メインフレームの保守・運用作業
- 基本設計・詳細設計

<!-- ### 過去の登壇資料
* [earthkey pitch vol.45](https://earthkey.events/events/earthkey-pitch-vol-45/) -->
### ポートフォリオ
* [マイプロフィール](https://www.fumiyanakamura.com/)
* [Wellbi(ユーザ記事投稿型サービス)](https://wellbi.vercel.app/)
  * ※ 今はDBを停止しているためログイン機能・記事閲覧など使えなくなっております

### 執筆歴
* [Qiita](https://qiita.com/NakamuraFumiya3)
* [zenn](https://zenn.dev/nakamura_fumiya)
