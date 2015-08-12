# ![EnjoyFishing](http://i.imgur.com/pmstLip.png)EnjoyFishing

EnjoyFishingはFF11の釣りを支援するツールです。

![全体イメージ](http://i.imgur.com/QTNxIid.jpg)

## 目次
[**主な機能**](#user-content-主な機能)  
[**使用方法**](#user-content-使用方法)  
[**画面説明**](#user-content-画面説明)  
　[魚の管理方法](#user-content-魚の管理方法)  
　[魚リスト](#user-content-魚リスト)  
　[釣り設定](#user-content-釣り設定)  
　[装備・食事](#user-content-装備食事)  
　[情報](#user-content-情報)  
　[履歴](#user-content-履歴)  
　[ハラキリ](#user-content-ハラキリ)  
　[釣った魚](#user-content-釣った魚)  
　[DB更新](#user-content-db更新)  
　[設定](#user-content-設定)  
[**FFからのEnjoyFishingの制御**](#user-content-ffからのenjoyfishingの制御)  
[**インストール・アンインストール**](#user-content-インストールアンインストール)  
[**動かない場合**](#user-content-動かない場合)  
[**今後の予定**](#user-content-今後の予定)  
[**開発環境**](#user-content-開発環境)  
[**ソース**](#user-content-ソース)  
[**免責事項**](#user-content-免責事項)  
[**修正履歴**](#user-content-修正履歴)  

## 主な機能
* 魚名または魚IDを指定して釣り上げ
* 各種チャット受信による自動停止および再起動
* 竿折れ発生時の自動修理
* 自動ハラキリ
* 各種エンチャントアイテムの自動使用
* 鞄がいっぱいになったらサッチェル・サック・ケースへ魚を自動的に移動
* 竿・餌をサッチェル・サック・ケースから自動的に移動
* いままでに釣ったことのある魚の表示
* 最新の魚情報をインターネットから更新
* 指定された釣りスキルになったら自動停止
* 自動スニーク
* 強制HP0
* 釣りの時間（ヴァナ・地球）を指定可能
* 釣り開始時に自動着替え
* 釣果の履歴を表示
* FF11からEnjoyFishingの起動・停止

## 使用方法
1. FF11を起動し、キャラクター選択後にEnjoyFishingを管理者モードで起動してください。  
	最初に、使用中のアドオン／プラグインを確認するのにチャットログが流れますが、皆には見えていないのでびびらないように。
2. 起動しない場合、[動かない場合](#user-content-動かない場合)を参照してください。
3. 竿と餌をカバンかモグワードローブに入れて装備してください。
4. デフォルトの設定では、釣る対象を未知の魚で外道（アイテム）・モンスター以外としています。  
とりあえず水辺に立って、そのまま開始ボタンで実行してください。
5. 掛かった魚がリストに追加されていくので、釣りたい魚にチェックを入れてください。
6. 目的に合わせて設定を変更してください。
7. Enjoy Fishing!!

## 画面説明
### 魚の管理方法
EnjoyFishingでは魚を扱うモードをIDモードと名前モードの二つから選択することができます。  
これは、釣った魚がクリティカルか否か、または匹数によってIDが分かれている為です。  
例えば、さびき針でキュスを釣った場合にには、`キュス1匹`・`キュス2匹`・`キュス3匹`・`キュス1匹クリティカル`・`キュス2匹クリティカル`・`キュス3匹クリティカル` と６種類のIDの魚が存在し、それぞれを別々に扱うのがIDモードで、ひと括りに扱うのが名前モードです。

### 魚リスト
![魚リスト](http://i.imgur.com/1PtHcee.jpg)
* モード  
    釣る対象の魚をID別・魚名別から選択することができます。  
    また切り替えた場合、魚リストのチェックがすべてクリアされます。
* 絞込
    - エリアで絞込・・・現在いるエリアで釣ったことのある魚に絞り込むことができます。
    - 餌で絞込・・・現在装備しているエサで釣ったことのある魚に絞り込むことができます。
* 魚リスト  
	ここでチェックされた魚が釣り対象の魚となります。（後述の学習モードがチェックされている場合は、未知の魚も対象となります）
* 未知の魚がかかってリリースされた場合、IDが含まれた魚名が一時的に割り当てられますが、魚名が判明した段階で変更されます。
* 魚名の末尾には以下の情報が付随されて表示されます。
    - S・・・小型の魚
    - L・・・大型の魚
    - I・・・アイテム・外道など
    - M・・・モンスター
    - T・・・テンポラリアイテム
    - K・・・だいじなもの
    - x3・・・さびき針などで一度に複数匹釣れた場合に表示されます。（IDモードの場合のみ）
    - !・・・クリティカルで釣れた魚の場合に表示されます。（IDモードの場合のみ）

### 釣り設定
![釣り設定](http://i.imgur.com/QTNxIid.jpg)

#### 動作
* 学習モード  
    学習モードとは、そのエリアで釣ったことの無い魚がかかった場合、釣り上げて学習する機能です。  
    但し、除外条件にかかる魚は釣りません。  
    竿折れ・糸切れなどは考慮されていませんので、大型の魚がいる所で釣りをする場合は注意してください。
* スニーク  
    釣り中はスニークをかけておく機能です。  
    ログに`スニークが切れそうだ。`と表示された場合には、かけ直しを行います。  
    かけ直しを行う場合、詠唱中に既存のBUFFを切るのですが、詠唱終了何秒前に切るかを設定できます。  
    デフォルトは詠唱完了１秒前にしていますが、うまく動作しない場合はこの数値を調整してみてください。  
    仕組み上、かけ直しの時に一瞬だけスニークが切れるので、過信は禁物です。  
    この機能は、アドオンのCancelを使用していないと使えません。
* 強制HP0  
    魚のHPを強制的にゼロにします。  
    指定した範囲のランダムで待ち時間が入ります。  
    設定によっては魚がかかった瞬間に釣れてしまうので注意してください。
* 除外条件  
    - 小型(!)除外・・・かかった魚が小型魚の場合、リリースを行います。
    - 大型(!!!)除外・・・かかった魚が大型魚の場合、リリースを行います。
    - 外道除外・・・かかった魚がアイテムの場合、リリースを行います。
    - モンスター除外・・・かかった魚がモンスターの場合、リリースを行います。
* 反応時間  
    魚がかかってから格闘を開始するまでの待ち時間を設定できます。  
    指定した範囲でランダムにウェイトが入ります。
* リキャスト時間  
    魚を釣った後、次に釣るまでの待ち時間を設定できます。  
    指定した範囲でランダムにウェイトが入ります。
* ヴァナ時間  
    指定した範囲のヴァナ時間だけ釣りを実行することを指定できます。  
    夜間（１８：００～６：００）だけ実行したい場合には、１８～５を指定します。
* 地球時間  
    指定した範囲の地球時間だけ釣りを実行することを指定できます。  
    指定方法はヴァナ時間と同じです。
* 竿の修理  
    竿折れが発生し予備の竿が無い場合、自動的に修理を行います。  
    もしワードローブに折れた竿がある場合、自動的に鞄へ移動し、修理が終わったらワードローブへ戻します。  
    修理に使用するクリスタルが鞄に無かった場合、サッチェル・サック・ケースより取り出します。  
    入港メッセージが表示された場合、修理を中止します。
* 時間切れまで待機  
    チャットに`そろそろ逃げられそうだ……！`と表示されるのを待ってから、釣り上げを行います。  
    釣り上げ前に反応時間分待機しますが、反応時間が４秒以上に設定されている場合、ここでは４秒以下に強制的に設定されるので、反応時間は調節しなくても大丈夫です。

#### 停止条件
* 本日釣果数  
    本日の釣果数が指定された釣果数になった場合、釣りを停止します。  
    ただし、外道やモンスターを釣った数は釣果数には入りません。
    また、０時で本日釣り上げた数のカウンターが０にクリアされます。
* 連続釣果無し  
    連続して指定された回数だけ何もかからなかった場合、釣りを停止します。
* スキル  
    指定された釣りスキル以上になった場合、釣りを停止します。  
    スキル上げで、スキル上限がわかっている魚を釣る場合に使用します。
* Tell/Say/Party/LS/Shout/Emo  
    それぞれの会話を受信した場合、釣りを停止します。  
    Empは/Emoteに自分の名前が入っていた場合に反応します。
* 再始動  
    Tell/Say/Party/LS/Shout/Empを受信して停止した場合でも、指定した時間待った後に釣りを再開します。
* 入港メッセージ  
    船上での釣りで、`まもなく入港します`の様なメッセージが表示された場合、釣りを停止します。  
    汽船航路・外洋航路・銀海航路では約１分前に、マナクリッパー・バージでは約３０秒前に表示されます。
* エミネンスクリア  
    エミネンスをクリアした場合、釣りを停止します。初期設定では、根気関連のエミネンスをクリアした場合に停止するようになっています。  
    停止させたいエミネンスを追加・修正したい場合は`FishDB/Eminence.xml`を修正してください。`name`がエミネンス名で、`stop`が釣りを停止させるか否かで、停止させたい場合は`true`を、停止させたくない場合には`false`を設定してください。  
    `Eminence.xml`修正後は、EnjoyFishingを再起動してください。
* 攻撃受けた    
    敵から攻撃を受けた場合、実行するコマンドを指定します。  
    このコマンドは、FF11のチャットラインで実行できるコマンドなら何でも指定することができます。  
    デフォルトではデジョンを実行するようにしていますが、詠唱中断される可能性があるため、スクリプトを組んで実行したほうが良いかと思います。  
    デジョンしたい場合`/ma デジョン <me>`を指定   
    スクリプトを実行した場合`//exec script.txt`を指定  
    Luaを実行した場合`//lua e script`を指定

#### 鞄いっぱい
* サッチェル/サック/ケース  
    鞄がいっぱいになった場合、鞄に入っている魚を移動しても良い場所を指定します。  
    この機能は、アドオンのItemizerを使用していないと使えません。
* コマンド  
    鞄がいっぱいになり、魚を移動できる場所もなくなった場合に実行されるコマンドを指定します。
    このコマンドは、FF11のチャットラインで実行できるコマンドなら何でも指定することができます。  
    デジョンしたい場合`/ma デジョン <me>`を指定   
    ピアスでセルビナにいきたい場合`/item セルビナピアス <me>`を指定  
    スクリプトを実行した場合`//exec script.txt`を指定
    Luaを実行した場合`//lua e script`を指定

#### 竿・エサなし
* サッチェル/サック/ケース  
    竿折れが発生して予備の竿が鞄に入ってない場合や、エサが鞄から無くなった場合に、装備していた竿およびエサを指定した場所から取り出します。  
    この機能は、アドオンのItemizerを使用していないと使えません。
* コマンド  
    竿切れ、エサ切れが発生した場合に実行されるコマンドを指定します。  
    指定できるコマンドは「鞄いっぱい」の時と同様です。

### 装備・食事
![装備・食事](http://i.imgur.com/m8R7DDB.jpg)
* '開始時に着替えを行う'をチェックした場合、開始ボタンを押した時に着替えを行います。
* 空欄を指定した部位は、着替えを行いません。
* 腰・左手・右手の右側に使用チェックがありますが、これをチェックすることで装備したエンチャントアイテムを、自動的に使用することができます。
* エンチャントアイテムを使用するか否かの判定は、強化アイコンのIDを見て判定しているため、同じIDのアイテム（指輪類）は同時に使用することができません。
* エンチャントアイテムの再使用時間・残り回数は見ていませんので注意してください。

### 情報
![情報](http://i.imgur.com/uB5iDPx.jpg)
* 本日の釣果情報がサマリーで表示されます。
* 釣果数  
    外道・モンスター以外の魚の釣果数を表示します。  
    カッコ内は一時間あたりの釣果数が表示されます。
* 結果  
    以下の分類別に集計されます
    - Catch・・・釣り上げた
    - NoBait・・・何も釣れなかった
    - NoCatch・・・バラした、時間切れ
    - Releace・・・リリースした
    - LineBreak・・・糸切れ
    - RodBreak・・・竿折れ
* 結果％  
    分類別ごとの比率を表示します。
* 全体％  
    全体からの比率を表示します。

### 履歴
#### 情報
![履歴](http://i.imgur.com/9VDSYx4.jpg)
* 日付  
    表示する日付を指定します。
* 更新  
    最新情報に更新します。
* ステータス  
    表示する履歴を指定したステータスで絞り込みます。
* 魚  
    表示する魚を指定した値で絞り込みます。
* 表示できる項目は初期設定以外にもあり、[設定タブ](#user-content-設定)にて表示非表示を設定する事ができます。  
また、表示列順の入れ替え・列幅の変更・ソートを行うことができます。

#### 合計
![合計](http://i.imgur.com/tc6lzDq.jpg)
* 表示内容は釣り情報と同じですが、日付・ステータス・魚名での絞込みが可能です。

### ハラキリ
![ハラキリ](http://i.imgur.com/ofO1Anv.jpg)

　この機能は、手持ちの魚を自動的にハラキリします。

* セルビナのZaldonの近くに移動し、向いてる方向を合わせて、ハラキリする魚を選択後開始してください。
* 鞄・サッチェル・サック・ケースに入っている魚を全てハラキリします。
* 魚の指定は、リストから選択するか、直接魚名を入力してください。
* リストには、鞄に入っていてDBに登録されている魚がリストアップされます。
* ハラキリの結果は、履歴に集計されて表示されます。
* アイテム発見時にハラキリを停止させたい場合には、`発見したら停止`にチェックを入れてから開始してください。

### 釣った魚
![釣った魚](http://i.imgur.com/3aa2pfP.jpg)

　この機能は、マウラのKatsunagaから聞ける、今までに釣ったことのある魚を表示します。  
　EnjoyFishingで釣ったことの無い魚を釣ると、自動的に釣った魚としてチェックされます。  
　クエストの[勇魚](http://wiki.ffo.jp/html/33862.html)や[根気](http://wiki.ffo.jp/html/33861.html)の、指標として使用してください。  
　キャラクター別に釣った魚を保存したい場合には、`設定タブ`の`設定の保存`を`プレイヤー別`にしてください。

* 釣っていない魚のみ表示  
    一覧に表示されている魚を、釣ったことの無い魚だけを表示します。
* 初期化  
    マウラのNPCのKatsunagaから、釣ったことのある魚のリストを取得します。  
    Katsunagaの近くに行き、向いてる方向を合わせてから実行してください。  
    処理が完了するまで、FFの画面操作は行わないでください。
* リセット  
    釣ったことのある魚リストをリセットします。

### DB更新
![DB更新](http://i.imgur.com/Zkxu9h0.jpg)

　この機能は、釣りの履歴データをアップロードし、皆さんから収集した履歴データより最新の魚データをダウンロードし、更新します。  
　アップロードされるデータには、キャラクター情報等、個人を特定するデータは全て削除されてから送信されますので、安心してください。（通信ログにキャラクター名が表示されますが、ファイル名含め内部で全てのキャラクター名は削除されています。）  
　収集した履歴データは、今後、統計情報サイトで閲覧できるようにする予定です。（統計情報サイトは作成中です。）  
　なんか気持ち悪いと思う方は、初期起動時にネットワークを有効するか聞いてきますので、そこで「いいえ」を選択すれば一切通信を行わなくなり、今まで通り使用することができます。  
　更新時、サーバーが混んでいると、インターナルサーバーエラーが発生する事があります。この場合は再度実行してください。

* 更新  
    サーバーに接続し、履歴データのアップロード及び最新の魚情報を取得します。
* ネット有効  
    ネットワーク接続の有無を設定します。ネットワーク接続したくない人は、ここのチェックを外してください。
* 起動時に自動更新  
    ネットワークに接続している場合、起動時に自動的に更新処理を実行します。

**　耐えられそうなフリーのサーバーが見つからなかったため、個人で使用している有料サーバーを使用しています。**  
**　サーバーを本来の目的で使用できなくなったり、サーバーをアップグレードしなければならなかったり、何からの支障が生じた場合、統計情報サイトに広告を表示するかもしれませんので、その点ご留意ください。（まだ何も考えていないけど一応・・・）**  
**　みなさんから提供された履歴データは、統計情報として提供されますが、送られてきた生データの公開及び、第三者への譲渡はしません。**  

### 設定
![設定](http://i.imgur.com/hu37Vrb.jpg)
#### 一般
* 設定の保存  
    設定の保存をキャラクター別にするか、すべてのキャラクターで統一するかを選択できます。
* Addon/Plugin  
    現在利用可能なアドオンおよびプラグインを表示します。  
    読み込まれていないものは名前が灰色で表示されます。  
    再取得したい場合は再取得ボタンを押してください。
* 常に最前面  
    画面を常に最前面で表示します
* 画面点滅  
    停止時・エラー発生時・一時停止時に画面を点滅させます。
* 画面アクティブ  
    画面点滅時と同時に画面をアクティブにします。  
    最小化されていれば通常状態にし、非アクティブであれば最前面に画面を表示します。
* メッセージをFFに表示  
    ステータスバーに表示されているメッセージを、FFのチャットに/Echoにて表示するようにします。

#### ステータスバー表示
* 画面下部のステータスバーに表示する項目を指定できます。

#### 履歴 列表示
* 履歴の詳細タブに表示する項目を指定できます。

### 月齢カレンダー

![月齢カレンダー](http://i.imgur.com/hVbqjFv.jpg)

* ステータスバーの月齢にマウスカーソルを合わせると、現在の月齢の残り時間・次の満月までの時間・次の新月までの時間を表示します。
* また、月齢をクリックすると、月齢カレンダーを表示します。

## FFからのEnjoyFishingの制御
　FFよりEnjoyFishingの制御を行いたい場合、/Echoにて以下の文字列をチャットに表示してください。
* 釣りの開始 `/echo EnjoyFishing Start`
* 釣りの停止 `/echo EnjoyFishing Stop`

　大文字小文字は区別していません。  
　本当は`//EnjoyFishing`でやりたかったんですけど、このコマンドを取ろうとするとFFACEがエラーを吐くので断念・・・。  
　直ったら/echoでやる方法を変更するかもしれません。

## インストール・アンインストール
1. [こちら](https://github.com/rohme/EnjoyFishing/releases)から、最新版のバイナリを取得する。
2. 適当なディレクトリに、バイナリを解凍する。
3. アンインストールは、解凍したディレクトリを削除するだけです。

## 動かない場合
* 管理者権限で実行してください。
* セキュリティソフトを一旦切ってから実行してみる。
* [Windower4](http://windower.net/)をインストールする。
* 最新の[FFACE](http://www.ffevo.net/)をインストールする。  
http://delvl.ffevo.net/Lolwutt/FFACE4-Public/tree/master
* [FFACE](http://www.ffevo.net/)に障害情報が挙がっていないか確認する。  
http://delvl.ffevo.net/Lolwutt/FFACE4-Public/issues
* 最新の[EliteAPI](http://www.elitemmonetwork.com/)をインストールする。  
http://ext.elitemmonetwork.com/downloads/eliteapi/
* [EliteAPI](http://www.elitemmonetwork.com/)に障害情報が挙がっていないか確認する。  
http://www.elitemmonetwork.com/forums/viewforum.php?f=28
* [VisualStudio2013のランタイム](http://www.microsoft.com/ja-JP/download/details.aspx?id=40784)をインストールする。**（必ずx86版を使用してください）**
* [.Net4.0](http://www.microsoft.com/ja-JP/download/details.aspx?id=17718)以上をインストールする。

##今後の予定
* 統計情報サイトの作成

## 開発環境
* Windows7 Ultimate 64bit
* [Microsoft Visual Studio Express 2013 C#](http://www.visualstudio.com/ja-jp/products/visual-studio-express-vs.aspx)
* [.NET Framework 4.0](http://www.microsoft.com/ja-jp/net/)
* [Windower4](http://windower.net/)
* [FFACE](http://www.ffevo.net/)
* [FFACETools](https://github.com/h1pp0/FFACETools_ffevo.net/)を修正した[FFACEToolsJP](https://github.com/rohme/FFACEToolsJP)
* [EliteAPI](http://www.elitemmonetwork.com/)

## ソース
EnjoyFishingは以下のサイトで、GPLv2ライセンスにて公開しています。  
https://github.com/rohme/  
障害報告・質問とかあればIssuesに登録して頂いて結構です。

## 免責事項
　本ソフトはフリーソフトです。自由にご使用ください。  
　このソフトウェアを使用したことによって生じたすべての障害・損害・不具合等に関しては、作者は一切の責任を負いません。各自の責任においてご使用ください。  

## 修正履歴
* **2015-08-12 Ver1.1.4**
    - 魚ID及びHPの取得、及び竿の入力をEliteAPIで代替
    - 月齢カレンダー機能の追加
    - 竿とエサを装備していない状態で自動着替えを行った場合、竿かエサが装備されていないとエラーが発生してしまうのを修正
    - 竿折れした場合、魚リストのチェックがクリアされるのを修正
    - 履歴DBの日時フォーマットの修正
* **2015-07-25 Ver1.1.3**
    - 何かしらのメニューを開いた状態で釣りを開始すると、正常に着替えができなかったのを修正
    - プレイヤー別に設定を保存しておいた状態で回線切断やクラ落ちしてしまった場合、設定ファイルが正常に更新されず、次回起動時に落ちてしまうのを修正
    - 釣った魚一覧の初期化で、シンとコクリュウが重複して登録されてしまうのを修正
* **2015-07-18 Ver1.1.2**
    - 自動食事機能を追加
* **2015-07-11 Ver1.1.1**
    - 釣りの停止条件に、エミネンスのクリアを追加
    - 新しいバージョンの通知機能を追加（ネット接続している場合）
    - 魚名が変な名前で登録されてしまうのを修正  
        私の環境では再現しなかったのですが、想像して修正しました。多分直っているはずなので、まだ発生する場合は教えてください。
    - プレイヤー別に設定保存すると、設定内容がリセットされてしまうのを修正
    - 釣った魚リストをソート可能に修正
* **2015-07-05 Ver1.1.0 プレリリース1**
    - 時間切れまで釣り上げを待つ機能を追加  
    - 今まで釣ったことのある魚を表示する機能を追加
    - インターネットにてデータベース更新機能を追加
* **2015-06-28 Ver1.0.11**
    - 他人の鞄がいっぱいログが表示されると、釣りが停止してしまうのを修正
    - アドオンのItemizerが複数個の移動に対応したので、関連箇所の修正
    - バージョンアップで追加されたアイテムを`Rod.xml``Bait.xml``Gear.xml`に追加
    - 複数行のチャットを正常に認識できなくなったのを修正(ChatTool)
* **2015-05-15 Ver1.0.10**
    - エンチャントアイテム使用後に釣りが停止してしまうのを修正
    - ハラキリ後、エリアチェンジするとクライアントが落ちるのを修正  
    FFACEでZaldonにターゲットを合わせると発生する模様。修正されるまでタブキーでターゲットを合わせるように修正した。
    - FFACEToolsの修正
* **2015-05-08 Ver1.0.9 プレリリース3**
    - 竿修理後のウェイト調整
* **2015-04-29 Ver1.0.9 プレリリース2**
    - エンチャントアイテム使用のチェックボックスが正常に動作していなかったのを修正
* **2015-04-27 Ver1.0.9 プレリリース1**
    - 竿の自動修理機能を追加
    - エンチャントアイテムの自動使用機能を追加
    - 釣り開始時の着替え機能を追加
    - FFから釣りの開始停止ができるようにインターフェースを追加
    - FFへメッセージを表示する機能を追加
    - 敵から攻撃を受けた場合、コマンドを実行する機能を追加
    - チャット受信で停止した場合、再始動が正常に動作しない場合があるのを修正
    - 再始動待機中にチャットを受信した場合、再始動直後に待機してしまうのを修正
* **2015-03-01 Ver1.0.8**
    - ハラキリが動作しなかったのを修正
* **2015-02-25 Ver1.0.7**
    - `//lua list`の出力先変更に伴う修正
* **2015-02-01 Ver1.0.6**
    - モグワードローブに対応
    - ハラキリでアイテムを発見した場合、停止するオプションを追加
    - 現在の釣りスキルを、チャットからも取得するように修正
    - 時間切れでリリースとなった場合、釣りが停止状態になってしまうのを修正
* **2015-01-24 Ver1.0.5**
    - **魚名を特定する為のキーをIDから、ID＋エリアに変更**  
    この変更によって、FishDBのエリア情報が起動時に初期化されます  
    学習モードにて、以前釣ったことのあるIDでもそのエリアで釣ったことの無い場合には、一度釣り上げて魚名を学習するようになります  
    この変更に伴い、名寄せ機能は削除されました
    - 自動ハラキリ機能の追加
    - アドオンのItemizerがサポート切れになったので、プラグインのItemizerを使用するように変更  
    スタック単位での移動ができなくなったので、小魚をサッチェル等に移動する場合には１匹ごとになり、手動でサッチェルの整頓をする必要があります（そのうち対応するかも？）
    - だいじなもの・テンポラリアイテムの釣りに対応  
    この対応により、MMM水産課や海図クエストで使用できるようになりました
    - チャット感知機能にEmoteを追加  
    Emoteに自分の名前が含まれていた場合に感知します
    - 情報タブに釣果数・経過時間の表示を追加
    - 本日釣果数での停止機能にて、アイテムやモンスターは釣果数としてカウントしないように変更
    - 常に最善面・画面フラッシュ・画面アクティブ機能を追加
    - 履歴リストのソート条件を保存するよう変更
    - 名寄せ関連のクラスやファイルを削除
    - プラグイン一覧が取得できなくなったのを修正
    - /fishコマンド送信時のウェイトを調整
    - アプリを起動したままFF11だけを終了した場合、CPU負荷がかかていたのを修正
* **2015-01-10 Ver1.0.4**
    - エリアチェンジで釣りを停止しなかった
    - 船の到着メッセージが表示されたら釣りを停止できるように修正した
    - 魚名を名寄せするように修正した~~（詳細は[名寄せについて](#user-content-名寄せについて)に記述）~~  
        これは複数名称複数IDに対応するまでの暫定対応です
* **2015-01-08 Ver1.0.3**
    - 自分よりもかなりスキル上限が低い魚を釣った場合、クリティカルの判定がうまくいかない場合があった
* **2015-01-08 Ver1.0.2**
    - HPが0になっていないのに釣り上げたように見ていた
    - 釣り中に戦利品からアイテムが流れてきた場合、それを魚と誤認して登録していた
    - ディレクトリFishDBの名前がFIshDBになっていた
* **2015-01-06 Ver1.0.1**
    - 竿残数とエサ残数の表示機能を追加
    - 釣果数が正常に計算されておらず、本日釣果数がうまく動作しなかった
    - IDモード時、開始ボタンで魚リストのチェックが消えていた
* **2015-01-05 Ver1.0.0**
    - スニーク釣り機能を追加
    - FFを複数起動しているとき、POL選択画面が正常に動作していなかった
    - 起動時アドオンチェックにて、無限ループする
    - キャラ変更で再ログイン後フリーズする（何故か再現できなかったので、ログイン後キャラクターが表示されるまで待ったり、ウェイトを入れたりして調整してみた。）
    - キャラクター選択中には画面コントロールをロックする
    - XMLファイルに排他処理追加
* **2014-12-31 ver0.0.3 プレリリース3**
    - プラットフォームを.NET4.5から.NET4.0に変更(XP対応)
    - キャラクター切り替え時にCPUリソースを大量に使ってしまう
    - 管理者権限で実行するようにmanifestの埋め込み
* **2014-12-30 ver0.0.2 プレリリース2**
    - 大きな魚を小さな魚として登録していた
    - 竿折れが発生したとき、代わりの竿を装備しなかった
* **2014-12-28 ver0.0.1 プレリリース1**
