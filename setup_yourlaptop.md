# PCへのセットアップ方法（Windows 11 Home / Pro 共通）

Windows 11 で WSL2 を使って Ubuntu 24.04 LTS と VSCode の開発環境を整える手順です。  
**Home版・Pro版どちらも手順は同じです。**

---

## ステップ1：PowerShell を管理者権限で開く

スタートメニューを**右クリック** →「ターミナル（管理者）」を選択します。

> ※「ユーザーアカウント制御」が表示されたら「はい」をクリックしてください。

---

## ステップ2：WSL2 と Ubuntu 24.04 LTS をインストール

以下のコマンドを入力して Enter キーを押します。

```
wsl --install -d Ubuntu-24.04
```

インストールが完了したら、**PCを再起動**します。

---

## ステップ3：Ubuntu の初期設定

再起動後、Ubuntu が自動で起動します。  
画面の指示に従って **ユーザー名** と **パスワード** を設定してください。

> ※ Windows のユーザー名・パスワードと違っても構いません。  
> ※ パスワード入力中は画面に何も表示されませんが、正しく入力されています。

---

## ステップ4：Ubuntu のパッケージを最新化

Ubuntu の画面で以下のコマンドを入力します。

```
sudo apt update && sudo apt upgrade -y
```

パスワードを求められたら、ステップ3で設定したパスワードを入力してください。

---

## ステップ5：VSCode のインストール

以下の URL から VSCode をダウンロードしてインストールします。

```
https://code.visualstudio.com/download
```

ダウンロードしたインストーラーを実行し、指示に従ってインストールを完了します。

---

## ステップ6：VSCode の拡張機能「WSL」をインストール

1. VSCode を起動します。
2. 拡張機能タブ（`Ctrl + Shift + X`）を開きます。
3. 検索バーに `WSL` と入力し、「WSL」をインストールします。

---

## ステップ7：Ubuntu から VSCode を起動する

Ubuntu の画面で以下のコマンドを入力すると、VSCode が Ubuntu 環境で開きます。

```
code .
```

---

## 動作確認

PowerShell で以下のコマンドを実行し、`VERSION` 列に `2` と表示されていれば成功です。

```
wsl --list --verbose
```

**出力例：**

```
  NAME            STATE           VERSION
* Ubuntu-24.04    Running         2
```

---

## パッケージのインストール例

Ubuntu 上でソフトウェアをインストールするには `apt` コマンドを使います。

```
sudo apt update
sudo apt install <パッケージ名>
```

**例：tree コマンドをインストールする場合**

```
sudo apt install tree
```
