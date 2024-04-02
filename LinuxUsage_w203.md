# 2024_1Q プログラミング応用演習@w203 every widnesday 1,2

# wsl+ubuntusの利用方法 (w203演習室端末） 

## 演習室端末へのログイン

各学生の学籍番号でサインインするのではなく、ローカルアカウント（すべて同じアカウントです）でのサインイン
     * ローカルアカウント
     * アカウント：.\user　（ドット￥user）
     * パスワード：授業時に知らせます　　　　　　　　　

## ローカルアカウントでのサインインの場合の制限 (重要！！)

     1. プリントアウトができない
     2. Office製品（Excel・Word・PowerPoint）を使用する場合は各自のアカウントでサインインが都度必要（PCの電源を切るまではサインインした状態が有効）
     3. ファイルサーバーHOMEへのアクセスについては、デスクトップ上にショートカットからHOMEへアクセスする
     4. サブシステムLinuxで作成したファイルフォルダはPC再起動時に初期化され削除されてします。（したがって、各自のネットワークドライブhomeに保存しておく必要がある）

## windowターミナルを起動する

windowsロゴからterminalと検索して起動する

<img src="./screenshots/searchterminal.png" alt="サンプル画像" width="800">

## ubuntuターミナルを選択する
<img src="./screenshots/select_ubuntu.png" alt="サンプル画像" width="800">

##  VScodeを開きソースファイルを作成する

Ubuntuターミナルで code ␣.(ドット)　と入力する
```
code .
```
<img src="./screenshots/vscode_openfrom_ubuntuterminal.png" alt="サンプル画像" width="800">

VScode 起動直後の画面

<img src="./screenshots/vscode_init.png" alt="サンプル画像" width="800">

-  「信頼する」をクリックしてよい
-   「ようこそ」タブは×で消してよい
  
 VScode の画面
 
<img src="./screenshots/newfilefolder.png" alt="サンプル画像" width="800">

新しいファイル、新しいフォルダのアイコンをクリックすると、ファイルやフォルダが新規作成される

<img src="./screenshots/newfilefolder.png" alt="サンプル画像" width="800">

フォルダ「progad」を新規作成し、その中に入り、ファイル「firstclang.c」を作成しコード入力した画面

<img src="./screenshots/helloworld.png" alt="サンプル画像" width="800">

## c言語ソースのコンパイルと実行

Ubuntu ターミナルにもどりgccコンパイラを使って作成したcソースコードをコンパイルする。

<img src="./screenshots/gcc.png" alt="サンプル画像" width="800">

コマンドの説明：

*  ls          　　カレントディレクトリのファイルとフォルダのリストを確認する
*  cd progad   　　配下のディレクトリprogadにディクレクトリを変更する　change directory
*  gcc -o 実行ファイル　ソースファイル.c　　例ではgcc -o test firstclang.c
* 　./test   実行する



