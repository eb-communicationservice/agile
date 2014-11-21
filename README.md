agile
=====

アジャイルノウハウをまとめるための場所


=====


## ふりかえりについて

* 規模
 * 管理画面チーム
 * 規模 3〜5人
 * Web開発(Ruby on Rails)

* フェーズ/状況
 * 新規開発〜保守

* こんな事した
 * ふりかえり

* こういう結果になった
 * 毎週1時間程度、メンバー全員でふりかえりを行うようにした。
 * 書籍「アジャイルレトロスペクティブズ　強いチームを育てる「ふりかえり」の手引」
   を元にチームの現状をふまえて必要なアクティビティや、単純にやりたいアクティビティを行った。
 * ファシリテーターは毎週チームメンバー内で輪番制にした。
 * 各個人の意見を出しやすいのと、TRYを決めていくと効果的なTRYが見つかることが多いので、KPTで行う事が多くなった。
 * 実施したTRYは必ず全員で評価を行い、KEEPにしていくかどうかを決めるようにしている。

* よかった事
 * 忙しい時でも必ずやるようにしていたので、何故忙しいかの問題点をみんなで話し合い、解決する事ができた。
 * 普段相談しないようなことも、議題として上がることがあった（「空調が寒い」などの環境のこととか）
 * ファシリテータースキルの向上があった。
 * TRYやチームとしての決まり事を、チームメンバー全員で考える為、納得して取り組むことができた。
 * 新規メンバーに対してはタイムラインなどを使用してプロジェクトの歴史を伝えることが出来た。

* 悪かった事
 * ふりかえりの時まで問題点を相談しない人がいた。
 * ファシリテータースキルが少ないと、時間超過があったり、内容が薄いものだったりすることがある。
 * 進捗会議とは別に行うので、単純に時間が取られることが多い。
 * チーム内だけでは解決出来ない問題もあった。(権限の問題など)
 * 遊びのようなアクティビティを選択すると、建設的なふりかえりではなく、リフレッシュの時間のようになってしまった。


=====

### CI (continuous integration / 継続的インテグレーション)環境について

* 規模
 * 管理画面チーム
 * 規模 3〜5人
 * Web開発(Ruby on Rails)

* フェーズ
 * 新規開発〜保守

* こんな事した
 * CIを採用した

* こういう結果になった
 * ソース管理: Git
 * CI: Jenkins(ec2)
 * レビュー: GithubのPull Requestを仕様
 * リリース: リリースツールを仕様
 * Pull Request単位でテストを行い、テストが通らなければリリース用のブランチにマージ出来ないようにした

* よかった事
 * 予想外の影響範囲に気がつく事が出来た。
 * プラグインによって単体レベルのテストカバレッジが自動で取れるようになった

* 悪かった事
 * テストコードを書く工数が取られる
 * テストコードに漏れがあると、影響範囲の特定に漏れがる（コードを追って影響範囲を検証する作業は必要）
 * テストコードのみ書いて、画面で行うテストをおろそかにしてしまう場合があった

=====


* 規模
 * 管理画面チーム
 * 規模 3〜5人
 * Web開発(Ruby on Rails)

* フェーズ/状況
 * 新規開発

* こんな事した
 * 画面テストの実装をした

* こういう結果になった
 * Railsのプラグインcucumberを使って画面テストを実装して自動化し、
 * CIに組み込んだ
 * 画面の自動実施テストについては、いくつかの要因(悪かった事に記載)によって、最低限の画面テストの実装だけになった。(申込画面、ログイン画面)

* よかった事
 * 画面の動きが自動化した画面テストで担保されるため、リファクタリングに安心感が生まれた

* 悪かった事
 * テストコードを書く工数が取られる(単体テストよりもかかっていた)
 * ステージングでの手動テストと同等の事をしていた
 * CSSやjavascriptのコントロールが難しく自動テスト出来ない仕様がいくつかあった
 * テストコードでハマることが多かった
 * 実行時間が長くかかってしまい、CIのサイクルが長くなってテスト待ちの状態が頻発した


=====

* 規模
 * 10人弱

* 状況
 * 新規開発、改修、保守

* こんな事した
 * テストコード自動実行（travis）
 * １スプリントは２週間単位
 * １日の稼働は５時間で計算（実作業はなんだかんだで丸一日分の稼働はとれないと判断して）
 * タスクの見積もりポイントは「1,2,3,5,8,13,Q(わからん)」にしている。
 * 見積もりポイントが大きくずれたら話あって納得して再見積もり。

* いいと思ったこと
 * 短期的な目標と期限が明確で進捗が分かりやすい。
 * 過剰な前倒し意識が無くて済む。
 * 割り込みタスクが入っても、作業に余裕そうな人が比較的分かりやすいため振りやすい。


* 悪いと思った事
 * mtgに割く稼働が高すぎる。（朝会/プランmtg/振り返り）
 * テストコードを書く工数が取られる
 * タスクの粒度が曖昧になりがち。
 * タスクの依存関係まで考慮してプランできないと失敗する。（立ち上がり時にありがち）
 * 軌道に乗るまである程度期間、スプリント数が必要。
    * →タスクの見積もり精度
    * →Tm全体でスプリント内に消化できるポイントの指標
 * 具体的な作業がわからないタスクは見積もれない。


=====

* 規模
 * リーダー : 1人
 * サブリーダ：1人
 * 開発者 : 5人

* 状況
 * 新規・追加開発

* こんな事した
 * テストコード自動実行（jenkins）
   * エラーになったらメールで全員に通知
 * ふりかえり兼進捗確認会(週一)
   * ここで遅れ気味だと、補正が入る
 * １スプリントは一ヶ月単位
   * リリース＝１スプリント
 * １日の稼働は５時間で計算
 * タスクの見積もりは単純に日数を使用していた。
   * 細かいタスクはredmineで管理していたのが影響している。
 * 見積もりが大きくずれたら話あって納得して再見積もり。
 * scrumベースでの運用。
   * phpmyscrumで各タスク管理をし、実際の作業進捗はredmineで行っていた。

* いいと思ったこと
 * jenkinsのお陰で、変更したコードの影響範囲がわかりやすかった(想定外のテストエラーとかの発見が早かった)
 * 作業時間が短くて済む(残業は殆どなかった)。
 * リーダーさんも軌道修正しやすそうだった。
 * 内容がわからないタスクは見積もらないので使用に振り回されることがなかった。
   * 担当者から詳細が出てくるまで着手しないことをネゴっていたため可能。
 * チームメンバーが事前にscrumに関して勉強していたため、スムーズに行ったと思われる。
   * 事前にscrumでやるから勉強しておくようにというお達しが出ていた。

* 悪いと思った事
 * スプリントでのタスク見積もり前に、リーダと担当者間でネゴが必要。
 * リーダー以外が業務委託者だったので、リーダーにかかる負担が大きかった(リーダーがネゴるだけの発言力が必要)
   * 1スプリントでやるタスクの量をある程度先に絞っていたらしい。
   * ネゴれない場合、アジャイルでやる意味ない。(そういうリーダーだとWFでも失敗するはず)
 * タスク管理ツールが複数になり、運用が面倒になった
   * phpmyadminは外向け、redmineは開発者向けで使用していた


=====


* 規模
 * 10人

* フェーズ/状況
 * 新規開発

* こんな事した
 * スクラムを採用。
 * 朝会では昨日やったこと、今日やること、困っていることを共有する。
 * 1スプリントは2週間。
 * ストーリーポイントはフィボナッチ数列(1〜13)。
 * バックログ管理はRedmineのかんばんを使用。
 * 仕様や設計はredmineのwikiを使用する。
 * クラス図やシーケンス図はastahを使用した。(一部cacooを使用)
 * ソースコード管理はGitHubを使用。Pull Requestベースの開発を行った。
 * 単体テストはJenkinsを使用して自動化した。
 * 単体テストはドメイン層(models)を中心に行った。controller, viewは行わない。
 * テストコードを書いたことがないのに、テスト駆動開発(TDD)は出来ない。まずはテストコードを書くことに慣れることが先。
 * TDDじゃなくても、「黄金の回転」は実施すべき。「黄金の回転」とは、動かい汚いコード -> 動く汚いコード -> 動かない綺麗なコード -> 動く綺麗なコード
 * TravisCIを使用しているが、コーディング規約チェック(phpcs)のみ実施している。今後は単体テストを実施予定。(最終的にはJenkinsを使わないようにする)

* 良かった事
 * スプリント内のタスクに集中出来る。

* 悪かった事
 * 朝会、スプリント計画レビュー、スプリント結果レビューに工数が掛かる。個人的には朝会は2,3日に1回で良い気がしている。
 * 自分のタスク優先となってしまい、ソースコードレビューが放置されることが多々あり。ソースコードレビュー時間(10時〜11時)を設定した。
 * スプリント結果レビューで振り返ることが最後の1回のみであった。スプリント毎に実施すべき。
 * 振り返りが1回しかなかったため、チームのスプリント消化ポイントが不明。ストーリーポイントの設定もあまり意味がなかった。
 * プロジェクトの最終決定はK社(m社ではない)のため、スコープの調整がほぼ不可となり、最終的には全ての機能を実装する必要あり。全ての機能を実装するならウォーターフォールと同じ。

