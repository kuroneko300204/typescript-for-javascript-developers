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

- コンパイル
  - コマンド
    - `tsc [ファイルパス]`
      - インストール時に`--save-dev`を付与したことで、`tsc `だけでは実行できなくなっているので、直接typescriptライブラリのパスを指定しなければならない。
        - `./node_modules/typescript/bin/tsc [ファイルパス]`
      - ...コマンドが長くなりすぎなので、npmが便利なコマンドを用意してくれている。
        - `npx`: nodemodule配下を自動で探索して実行してくれるコマンド。
          - 上記のコンパイルの場合、
            - `npx tsc [ファイルパス]`
  - 成功すると...
    - typescriptを変換した`.js`ファイルが作成される。
- Javascript実行コマンド
  - `node [ファイルパス]`

- typescriptメモ
  - Typescriptは、コンパイルでJavascriptに変換してから実行される。


## npm
- `npx`
  - nodemodule配下を自動で探索して実行してくれるコマンド。

## 忘れがちなこと
### Gitの`-`は、先ほどチェックアウトしていたブランチ。
