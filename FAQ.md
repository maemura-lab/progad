# ubuntuLTSはgccはデフォルトではいっていますか？

Ubuntu LTS (Long Term Support) バージョンには多くの基本的な開発ツールが標準で含まれていますが、`gcc`（GNU Compiler Collection）はデフォルトでインストールされているわけではありません。Ubuntuをインストールした直後にgccを使用しようとすると、まずはシステムにインストールする必要があります。

Ubuntuに`gcc`をインストールするには、ターミナルを開いて以下のコマンドを実行します：

```
sudo apt update
sudo apt install build-essential
```

この`build-essential`パッケージは、`gcc`や`g++`（C++ コンパイラ）、`make`などの基本的な開発ツールを含んでいます。これにより、CやC++での開発環境が整います。

ただし、特定のUbuntu LTSバージョンやカスタムされたUbuntuベースのディストリビューションでは、インストール時の選択肢や設定によっては`gcc`がプリインストールされている場合もあります。しかし、一般的には上記の手順で明示的にインストールする必要があります。
