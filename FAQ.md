## GCCでコンパイルできるのに、VSCodeで波線が表示されるがどうすればよいか？

VSCodeは静的解析ツールを使って、コードを実際にコンパイルする前にエラーや警告を表示することがあります。波線表示は編集の支援機能にすぎず、実際のプログラムの実行には影響しません。🌟👉GCCでコンパイルできて正常に動作するのであれば、無視してよいです。

ちなみに次の対応でも解決しないようです；

解決策

VSCodeのC/C++設定を更新する：

* Ctrl+Shift+Pを押して、コマンドパレットを開く
* C/C++: Edit Configurations (UI)を選択
* C_Cpp.default.cStandardをc99またはc11に設定


c_cpp_properties.jsonファイルを直接編集：

* .vscodeフォルダ内のc_cpp_properties.jsonファイルで設定する
```
{
    "configurations": [
        {
            "name": "Linux",
            "includePath": ["${workspaceFolder}/**"],
            "defines": [],
            "compilerPath": "/usr/bin/gcc",
            "cStandard": "c99",
            "cppStandard": "c++14",
            "intelliSenseMode": "gcc-x64"
        }
    ],
    "version": 4
}
```


## ubuntuLTSはgccはデフォルトではいっていますか？

Ubuntu LTS (Long Term Support) バージョンには多くの基本的な開発ツールが標準で含まれていますが、`gcc`（GNU Compiler Collection）はデフォルトでインストールされているわけではありません。Ubuntuをインストールした直後にgccを使用しようとすると、まずはシステムにインストールする必要があります。

Ubuntuに`gcc`をインストールするには、ターミナルを開いて以下のコマンドを実行します：

```
sudo apt update
sudo apt install build-essential
```

この`build-essential`パッケージは、`gcc`や`g++`（C++ コンパイラ）、`make`などの基本的な開発ツールを含んでいます。これにより、CやC++での開発環境が整います。

ただし、特定のUbuntu LTSバージョンやカスタムされたUbuntuベースのディストリビューションでは、インストール時の選択肢や設定によっては`gcc`がプリインストールされている場合もあります。しかし、一般的には上記の手順で明示的にインストールする必要があります。
