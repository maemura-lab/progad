# あなたのPCへのセットアップ方法(windows11 pro)

Windows 11 Pro の日本語環境で、Windows Terminal、WSL2、Ubuntu、VSCodeを使用して開発環境を設定する手順を以下に説明します。

1. Windows Terminal のインストール: a. Microsoft Store を開きます。 b. 検索バーに「Windows Terminal」と入力し、Enterキーを押します。 c. 「Windows Terminal」をクリックし、「インストール」ボタンをクリックします。 d. インストールが完了したら、Windows Terminal を起動します。
2. WSL2 のインストール: a. 管理者権限で PowerShell を開きます。 b. 以下のコマンドを実行して、WSL を有効化します。c. 次に、以下のコマンドを実行して、仮想マシンプラットフォームを有効化します。d. コンピュータを再起動します。 e. WSL2 Linux カーネル更新プログラムをダウンロードしてインストールします。<https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi >（インストールファイルをダブルクリックして実行すればよい）f. PowerShell を管理者権限で開き、以下のコマンドを実行して WSL2 を既定のバージョンとして設定します。
    
    ```
    dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
    
    ```
    
    ```
    dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
    
    ```
    
    ```
    wsl --set-default-version 2
    
    ```
    
3. Ubuntu のインストール: Ubuntu のインストール: a. Microsoft Store を開きます。 b. 検索バーに「Ubuntu 22.04 LTS」と入力し、Enterキーを押します。 c. 「Ubuntu 22.04 LTS」をクリックし、「インストール」ボタンをクリックします。 d. インストールが完了したら、Ubuntu 22.04 LTS を起動します。 e. 初回起動時にユーザー名とパスワードを設定します。
4. VSCode のインストール: a. 以下のURLにアクセスして、VSCodeをダウンロードします。 https://code.visualstudio.com/download b. ダウンロードしたインストーラーを実行し、指示に従ってインストールを完了します。 c. VSCode を起動します。 d. 拡張機能タブ（Ctrl + Shift + X）を開き、「Remote - WSL」拡張機能を検索してインストールします。
5. Ubuntu 内で VSCode を使用する: a. Windows Terminal を起動します。 b. 新しいタブを開き、ドロップダウンメニューから「Ubuntu」を選択します。 c. Ubuntu のシェルが開いたら、以下のコマンドを入力して VSCode を起動します。d. VSCode が Ubuntu 内で開き、Ubuntu ファイルシステムにアクセスできるようになります。
    
    ```
    code .
    
    ```
    

以上の手順に従うことで、Windows 11 Pro 日本語環境において、Windows Terminal、WSL2、Ubuntu、VSCodeを使用した開発環境を適切に設定することができます。これにより、Linux ベースの開発をWindows上でシームレスに行うことができます。

## tips:

### wsl_update_x64.msiのインストール

WSL2 Linux カーネル更新プログラム（wsl_update_x64.msi）をダウンロードした後、以下の手順でインストールを行います。

1. ダウンロードしたファイル（wsl_update_x64.msi）をダブルクリックして実行します。
2. 「ユーザー アカウント制御」ダイアログが表示された場合は、「はい」をクリックして許可します。
3. 「Windows Subsystem for Linux Update Installer」ウィンドウが表示されます。「Next」をクリックします。
4. ライセンス契約を読み、同意する場合は「I accept the terms in the License Agreement」にチェックを入れ、「Next」をクリックします。
5. インストール先のフォルダを確認し、必要であれば変更します。そのまま進める場合は「Next」をクリックします。
6. 「Install」をクリックして、インストールを開始します。
7. インストールが完了すると、「Completed」と表示されます。「Finish」をクリックしてウィンドウを閉じます。

これで、WSL2 Linux カーネル更新プログラムのインストールが完了します。インストール後は、PowerShell を管理者権限で開き、以下のコマンドを実行して WSL2 を既定のバージョンとして設定します。

```
wsl --set-default-version 2

```

以上の手順に従って、WSL2 Linux カーネル更新プログラムをインストールし、WSL2 を既定のバージョンとして設定してください。これにより、WSL2 を使用する準備が整います。


### WSL2 Linux カーネル更新プログラムが正常にインストールできたかを確認する

WSL2 Linux カーネル更新プログラム（wsl_update_x64.msi）のインストールが正常に完了したかどうかを確認するには、以下の手順を実行してください。

1. PowerShell を管理者権限で開きます。
2. 以下のコマンドを実行して、インストールされている WSL のバージョンを確認します。このコマンドを実行すると、インストールされている Linux ディストリビューションとそのバージョン情報が表示されます。 出力例:"VERSION" 列に "2" と表示されていれば、WSL2 が正常にインストールされていることを示しています。
    
    ```
    wsl --list --verbose
    
    ```
    
    ```
    NAME                   STATE           VERSION
    * Ubuntu-22.04         Running         2
      Ubuntu-20.04         Stopped         2
    
    ```
    
3. さらに、以下のコマンドを実行して、WSL2 のカーネルバージョンを確認することができます。出力例:"Kernel version" の行に WSL2 のカーネルバージョンが表示されます。バージョン番号が表示されていれば、WSL2 Linux カーネル更新プログラムが正常にインストールされていることを示しています。
    
    ```
    wsl --status
    
    ```
    
    ```
    Copy codeDefault Distribution: Ubuntu-22.04
    Default Version: 2
    
    Windows Subsystem for Linux was last updated on 4/15/2023
    WSL automatic updates are on.
    
    Kernel version: 5.15.79.1
    
    ```
    

これらの手順により、WSL2 Linux カーネル更新プログラムが正常にインストールされたことを確認できます。問題がある場合は、エラーメッセージが表示されるか、バージョン情報が正しく表示されません。その場合は、インストール手順を再度確認し、必要に応じてトラブルシューティングを行ってください。

## パッケージのインストール

例えばtreeコマンドの場合
```
sudo apt-get update
sudo apt-get install tree

```
