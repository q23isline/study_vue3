# study_vue3

[![LICENSE](https://img.shields.io/badge/license-MIT-green.svg)](./LICENSE)
![releases](https://img.shields.io/github/release/q23isline/study_vue3.svg?logo=github)
[![Open in Visual Studio Code](https://img.shields.io/static/v1?logo=visualstudiocode&label=&message=Open%20in%20Visual%20Studio%20Code&labelColor=555555&color=007acc&logoColor=007acc)](https://open.vscode.dev/q23isline/study_vue3)

[![Node.js](https://img.shields.io/static/v1?logo=node.js&label=Node.js&message=v20.15.0&labelColor=555555&color=339933&logoColor=339933)](https://nodejs.org)
[![npm](https://img.shields.io/static/v1?logo=npm&label=npm&message=v10.7.0&labelColor=555555&color=CB3837&logoColor=CB3837)](https://www.npmjs.com/)
[![Vue.js](https://img.shields.io/static/v1?logo=vue.js&label=Vue.js&message=v3.4.37&labelColor=555555&color=4FC08D&logoColor=4FC08D)](https://ja.vuejs.org/)

## はじめにやること

1. ソースダウンロード

    ```bash
    git clone 'https://github.com/q23isline/study_vue3.git'
    ```

2. リポジトリのカレントディレクトリへ移動

    ```bash
    cd study_vue3
    ```

3. アプリ立ち上げ

    ```bash
    docker compose build --no-cache
    docker compose down -v
    sudo rm -rf node_modules
    docker create -it --name front study_vue3-front bash
    sudo docker cp front:/app/node_modules $(pwd)
    docker rm -f front
    sudo chown -R $(whoami):$(whoami) node_modules
    docker compose up -d
    docker compose exec front npm run build
    ```

## 日常的にやること

### システム起動

```bash
docker compose up -d
```

### システム終了

```bash
docker compose down
```

### フロントエンドのビルド

```bash
docker compose exec front npm run build
```

## 動作確認

### URL

- <http://localhost:5173>

## フロントエンド静的解析単体実行

```bash
docker compose exec front npm run lint
```

## フロントエンドフォーマット解析単体実行

```bash
docker compose exec front npm run format-check
```
