# Hands on Linux CUI
- [practice01](#practice01)
- [practice02](#practice02)
- [practice02_examples](#practice02_examples)


## practice01
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
## practice02

Linuxを学ぶ際に実践的な経験を積むことは非常に重要です。以下に、Linux初学者向けのハンズオン的な演習課題を5つ提案します。これらの課題は、基本的なコマンドライン操作からシステム管理の基礎までをカバーしています。

### 1. ファイルとディレクトリの操作
- **目的**: ファイルやディレクトリの作成、削除、移動、コピーの方法を学ぶ。
- **課題**:
  1. `mkdir`コマンドを使って`practice`という名前のディレクトリを作成します。
  2. `touch`コマンドを使って、`practice`ディレクトリ内に`sample.txt`という空のファイルを作成します。
  3. `cp`コマンドを使って、`sample.txt`を`copy.txt`にコピーします。
  4. `mv`コマンドを使って、`copy.txt`を`moved.txt`に名前を変更します。
  5. `rm`コマンドを使って、`moved.txt`を削除します。

### 2. テキストファイルの編集
- **目的**: 基本的なテキストエディタ（nanoやvim）を使用してファイルを編集する方法を学ぶ。
- **課題**:
  1. `nano`（または`vim`）エディタを開き、`sample.txt`ファイルに好きなテキストを追加します。
  2. ファイルを保存し、エディタを終了します。
  3. `cat`コマンドを使って、`sample.txt`の内容を表示します。

### 3. ファイル検索とパイプ
- **目的**: `find`や`grep`コマンドを使ったファイル検索と、パイプを使用してコマンドの出力を別のコマンドへ渡す方法を学ぶ。
- **課題**:
  1. `find`コマンドを使って、ホームディレクトリ以下のすべての`.txt`ファイルを検索します。
  2. `grep`コマンドを使って、`sample.txt`ファイル内で「Linux」という単語が含まれる行を検索します。
  3. `ps`コマンドと`grep`コマンドを組み合わせて、現在実行中のプロセスの中から「bash」という単語を含むプロセスを探します。

### 4. パーミッションの理解と変更
- **目的**: ファイルやディレクトリのパーミッションを理解し、変更する方法を学ぶ。
- **課題**:
  1. `ls -l`コマンドを使って、`sample.txt`ファイルのパーミッションを表示します。
  2. `chmod`コマンドを使って、`sample.txt`のパーミッションを変更し、所有者にのみ書き込み権限を与えます。
  3. 再度`ls -l`コマンドを実行して、パーミッションが変更されたことを確認します。

### 5. シンプルなbashスクリプトの作成
- **目的**: 基本的なbashスクリプトを作成し、実行する方法を学ぶ。
- **課題**:
  1. テキストエディタを使用して、現在の日

付を表示し、「Hello, World!」と出力するシンプルなスクリプト`hello.sh`を作成します。
  2. `chmod`コマンドを使って、スクリプトに実行権限を与えます。
  3. スクリプトを実行し、出力を確認します。

これらの課題を通じて、Linuxシステムの基本的な操作から、少し複雑なタスクまでをカバーし、Linuxに慣れる良いスタートが切れるでしょう。


## practice02_examples

ここでは、実際のLinux環境での実行例を示します。ターミナルを開いて、以下の手順に従ってください。作業用のディレクトリとして`linux_practice`をホームディレクトリの下に作成し、各課題ごとにサブディレクトリを作成して作業を進めます。

### 1. ファイルとディレクトリの操作
```bash
cd ~
mkdir linux_practice
cd linux_practice
mkdir task1
cd task1
mkdir practice
touch practice/sample.txt
cp practice/sample.txt practice/copy.txt
mv practice/copy.txt practice/moved.txt
rm practice/moved.txt
```

### 2. テキストファイルの編集
```bash
cd ../
mkdir task2
cd task2
echo "Hello, Linux World!" > sample.txt
cat sample.txt
```

### 3. ファイル検索とパイプ
```bash
cd ../
mkdir task3
cd task3
echo "This is a Linux practice file." > linux.txt
echo "Linux is fun!" >> linux.txt
find ~/linux_practice -name "*.txt"
grep "Linux" linux.txt
ps aux | grep bash
```

### 4. パーミッションの理解と変更
```bash
cd ../
mkdir task4
cd task4
echo "Linux permissions are important." > permissions.txt
ls -l permissions.txt
chmod 600 permissions.txt
ls -l permissions.txt
```

### 5. シンプルなbashスクリプトの作成
```bash
cd ../
mkdir task5
cd task5
echo -e '#!/bin/bash\necho "Today is $(date)"\necho "Hello, World!"' > hello.sh
chmod +x hello.sh
./hello.sh
```

これで、各タスクを順番に実行した一通りの例を示しました。この過程で、Linuxの基本操作、ファイルとディレクトリの扱い、テキスト編集、ファイル検索とコマンドのパイプ処理、パーミッションの設定、そしてシンプルなbashスクリプトの作成と実行について学ぶことができます。

実行する際は、実際のLinux環境において、適宜パスやファイル名を自分の環境に合わせて調整してください。
