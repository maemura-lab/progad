LinuxCUIをつかってみましょう。コマンドライン操作を練習するためのハンズオン的な演習例です。自分のホームディレクトリから作業用ディレクトリを作成し、その配下で次々と操作を行います。適宜、ディレクトリとファイルの構造を示します。

1. ホームディレクトリに移動し、現在の位置を確認します。
   ```
   $ cd ~
   $ pwd
   /home/username
   ```

2. 作業用ディレクトリ "cli_practice" を作成し、移動します。
   ```
   $ mkdir cli_practice
   $ cd cli_practice
   ```

3. "cli_practice" ディレクトリ内に、"src" と "bin" ディレクトリを作成します。
   ```
   $ mkdir src bin
   ```

4. "src" ディレクトリに移動し、C言語のソースファイル "hello.c" を作成します。カレントディレクトリでvscodeを開いて（code .　して） ファイルを新規作成してください。
   ```
   $ cd src
   $ code .
   ```
   
   VScode でファイル新規作成　hello.c 内容は下記のとおり：
   
   ```
   #include <stdio.h>
   int main() {
       printf("Hello, World!\n");
       return 0;
   } 
   ```

6. 現在のディレクトリ構造を確認します。※treeコマンドのインストールが必要な場合はsetup_yourlaptop.mdを参照してください
   ```
   $ cd ..
   $ tree
   .
   ├── bin
   └── src
       └── hello.c

   2 directories, 1 file
   ```

7. "src" ディレクトリ内で "hello.c" をコンパイルし、実行ファイル "hello" を "bin" ディレクトリに出力します。
   ```
   $ cd src
   $ gcc -o ../bin/hello hello.c
   ```

8. "bin" ディレクトリに移動し、"hello" を実行します。
   ```
   $ cd ../bin
   $ ./hello
   Hello, World!
   ```

9. "src" ディレクトリに移動し、"hello.c" を "hello_world.c" にリネームします。
   ```
   $ cd ../src
   $ mv hello.c hello_world.c
   ```

10. "hello_world.c" を "backup" ディレクトリにコピーします。
   ```
   $ mkdir backup
   $ cp hello_world.c backup/
   ```

11. 現在のディレクトリ構造を確認します。
    ```
    $ cd ..
    $ tree
    .
    ├── bin
    │   └── hello
    └── src
        ├── backup
        │   └── hello_world.c
        └── hello_world.c

    4 directories, 3 files
    ```

この演習例では、ディレクトリの作成、移動、コンパイル、実行ファイルの生成、ファイルのリネーム、コピー、そしてディレクトリ構造の確認を行いました。これらの操作を通して、基本的なLinux CUIコマンドの使い方を練習することができます。

最後に、ホームディレクトリ直下に作成したディレクトリをサブディレクトリおよびファイルごと削除します。cdで自分のホームディレクトリに移動します。pwdで現在の作業ディレクトリの絶対パスを確認します。lsでファイルディレクトリ一覧を表示してcli_practiceディレクトが存在することを確認します。rmでcli_practiceディレクトを丸ごと削除します。-rfオプションで内包されるファイルとディレクトリが確認なしに一括削除されます。
   ```
   $ cd
   $ pwd
   $ ls
   $ rm -rf cli_practice
   ```
