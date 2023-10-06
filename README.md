# 学習メモ
##  package-json
- 初期化(package-jsonファイル生成)
```
npm init -y
```

## typescript
- 公式Github
  - https://github.com/microsoft/TypeScript

- インストール手順
  - typescriptのバージョン確認
```
npm info typescript
```

  - インストールコマンド
    - Typescriptは開発環境のみで使用するものとなる。実行環境では使用しないので、`--save-dev`オプションを付加する。
```
npm install --save-dev typescript@[上記確認で表示された最新バージョン]
```
  - インストールの確認
    - package.jsonにインストールしたバージョンが追記されていることを確認する。

- コンパイル
  - 手動で実行する場合
    - コマンド
      - `tsc [ファイルパス]`
        - インストール時に`--save-dev`を付与したことで、`tsc `だけでは実行できなくなっているので、直接typescriptライブラリのパスを指定しなければならない。
          - `./node_modules/typescript/bin/tsc [ファイルパス]`
        - ...コマンドが長くなりすぎなので、npmが便利なコマンドを用意してくれている。
          - `npx`コマンドを使用する(npxは以下のnpmの項を参照)。
            - 上記のコンパイルの場合、
              - `npx tsc [ファイルパス]`
  - １回１回手動コンパイル→実行では開発速度が遅くなるので、効率を上げるために`ts-node`というツールを使用する。
    - 
  - 成功すると...
    - typescriptを変換した`.js`ファイルが作成される。
- Javascript実行コマンド
  - `node [ファイルパス]`

- typescriptメモ
  - Typescriptは、コンパイルでJavascriptに変換してから実行される。


## npm
- `npx`
  - nodemodule配下を自動で探索して実行してくれるコマンド。

## ts-node
- 公式サイト
  - https://github.com/TypeStrong/ts-node
- 挙動
  - 手動で`tsc [ファイルパス].ts`コマンドでコンパイルし、`npm [ファイルパス].js`していたものを、一回のコマンドで行ってくれる。
- インストール手順
  - 最新バージョン確認
    - `npm info ts-node`
  - インストール
    - `npm install --save-dev ts-node@[上記で調べたバージョン]`
  - インストールの確認
    - package.jsonにインストールしたバージョンが追記されていることを確認する。

## ts-node-dev
- 毎回変更の度(ファイルを監視してくれる)に`ts-node`を実行するのは開発の障害になるので、更にこれを自動反映してくれるツール。
- 公式サイト
  - https://github.com/wclr/ts-node-dev
- 起動コマンド
  - `% npx ts-node-dev --respawn [ファイルパス]`
  - 頻繁に使用するので、package.jsonにエイリアスを設定する。
    - エイリアス名は任意で決めて良い。
```
  "scripts": {
    "dev": "ts-node-dev --respawn",
    "test": "echo \"Error: no test specified\" && exit 1"
  }
```
  - 詳しい使い方は、公式GithubのUsage参照。
- 停止ショートカット
  - `ctrl + c`
## 忘れがちなこと
### Gitの`-`は、先ほどチェックアウトしていたブランチ。
