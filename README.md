# botVTuber
botにyoutuberをやらせるためのシステムです。現在は主にコメントからのリアルタイムマルコフ連鎖使用。

＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝

◎ソフトウェア/環境等

　このプログラムをいじる/動かすのに必要なソフトウェアや環境を以下に記します。
 
 ・Visual Studio 2017(*以下VS)
 　コードをいじるために必要なエディター
 ・.Net Framework ver4.0.3
 　プログラムを走らせるのに必要な実行環境
 ・やります！アンコちゃん
 　ニコニコからコメント持ってくるときに使います。
 ・anko2unity
 　アンコちゃんに入れるプラグイン
 ・Nicolive Comment Reciever(*一部配布)
 　Unityに入れるパッケージ
 ・MarkovInu(*配布)
 　持ってきたコメントから文章を生成するプログラム
 ・mecab
 　形態素解析ライブラリ
 
 *VSやUnityなどは私たちの開発環境を例として挙げましたが、
  多少バージョンが変わっても動くと思います。


◎設定方法

　・先にVSとUnityをインストールし環境を整えておきます。

　VS；https://docs.microsoft.com/ja-jp/visualstudio/install/install-visual-studio?view=vs-2019
　(VS 2017の場合；https://docs.microsoft.com/ja-jp/visualstudio/releasenotes/vs2017-relnotes)
　Unity；https://unity3d.com/jp/get-unity/download
　からダウンロード・インストールができます。


　・mecabも先にインストールしておきます。
　taku910.github.io/mecab/#download
　mecabはインストールするだけでOKです。


　・やります！アンコちゃんの設定

　yarimasu.ankochan.net
　からダウンロード・インストールします。

　https://qiita.com/toRisouP/items/52c0701147dcbdeb4b9df
　を参考に準備を進めます。
　上記サイトの"anko2unity"をダウンロードします。
　ダウンロードができたら、"anko2unity"はアンコちゃんのプラグインディレクトリに入れます。

　プラグインに格納出来たらアンコちゃんを立ち上げ
　すぐにブラウザの選択画面が表示されるので、良く使用するブラウザを選択してください。
　選択したブラウザでニコ生にログインします。
　ログインしたまま、取得したい動画のURLの"lv数字"の部分をコピーし、
　アンコちゃん上部の放送URL欄にペーストします。

　最後に、上部のプラグインタブから"anko2unity"を選択し、
　出てきたウィンドウのPort欄に"17305"と入力してください。
　これでアンコちゃんの設定は完了です。


　・Unityの設定

　アンコちゃん同様、
　https://qiita.com/toRisouP/items/52c0701147dcbdeb4b9df
　を参考に"NicoliveCommentReciever"をダウンロードします。
　上記サイトから"NicoliveCommentReciever.unitypackage"をダウンロードしてUnityにimportしてください。

　また、適当なGameObjectを生成し、
　今回配布した"NicoliveCommentRecieveCompornent.cs"を貼り付けてください。
　このときInspectorに表示されるHostの欄に"127.0.0.1"、Portの欄に"17305"と入力してください。


　・MarkovInu(仮)の設定

　事前にコメントを格納するテキストファイルをどこかに作っておきます。(ex."sample.txt")
　配布の"MarkovInu-master"をダウンロードし、MarkovInuフォルダ下の"MarkovInu.sln"を開きます。
　21行目のconst string pathの""内に先ほど作ったテキストファイルのパスを入れます。
　26行目には形態素解析ライブラリのディレクトリ(-----\MarkovInu-master\MarkovInu\MarkovInu\dic\ipadic)
　を入力します。
　44行目sleep()内はミリ秒を表し、文章生成の間隔を変えられます。
　57行目n = は文章生成素材とするコメント数を表しています。
　98行目のStreamWriter()で文章生成の結果を格納するテキストファイルを指定しますが、
　生成された文章は毎回クリップボードにコピーされるので、Softalkなどでのクリップボード監視を
　用いることができます。

　また、"MarkovKey.cs"の18行目N = の数字を変えることでマルコフ連鎖の次数を変更できます。


◎使い方

　上記の通り、やりますアンコちゃん、Unity、MarkovInu(仮)の設定を済ませ、
　Unityのボタン、MarkovInu.slnの開始ボタンの順に押すと動きます。


◎著者？


◎Thanks？
