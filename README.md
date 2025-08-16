# Dify Training

業務で活用するために、Difyの使い方を学ぶためのレポジトリ。

**ゼロから学ぶDifyの教科書**に沿った内容。

## 3.4 文書校正アプリケーションの開発

- 校正対象の文書
    - [docs](./docs)ディレクトリに配置。
- Dify環境
    - クラウド版Difyを使用する


### Ollamaの設定

DifyからOllamaのendpointにアクセスできるようにする。

- Ollama settingsから`Expose Ollama to the network`をONにする。(`0.0.0.0:11434`にバインドされる)
- または、ollamaのhostを変更する
  - `OLLAMA_HOST="0.0.0.0:11434"`


### Ollamaの公開

Ngrokを実行する。

```
$ ngrok http 11434 #port=11434のサービスを公開
```


### 手順

- ワークフローのアプリタイプを選ぶ
- `input_text`に`単一ファイル`を選択する
- `テキスト抽出`ノードを追加する。
- `LLM`ノードを追加する。
- `モデルプロバイダーの設定`で`Ollama`を選択する
- ngrokで発行されたurlを指定する。

