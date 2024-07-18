## tailwindcssで構築されたサイトををhtml/cssファイルに変換するプロジェクト

### 環境構築

```bash
cd tailwind_site
npm i
```
## サイト作成手順

### 1.　v0でサイトを作成
下記サイトでプロンプトを入力してデザインを作成する。
https://v0.dev/

### 2. 作成されたコードを貼り付ける
作成されたコードを`tailwind_site/src/index.html`に貼り付ける

### 3. CSSをビルドする
`tailwind_site`のディレクトリで次のコマンドを入力
```bash
npm run build
```
`tilewind_site/dist`内でcommon.cssが生成される

### 4. 生成されたファイルの移行
次のようにファイルを移行する
#### `tilewind_site/dist/common.css` >>> `site/css/common.css`
#### `tilewind_site/src/index.html` >>> `site/index.html`

### 5. cssのimportを書き換える

```diff
- <link rel="stylesheet" href="../dist/common.css" />
+ <link rel="stylesheet" href="./css/common.css" />
```


### フォルダ構成
```
├── README.md
├── site << build後のhtml/cssを格納
│   ├── css
│   ├── images
│   ├── index.html
│   └── js
└── tilewind_site << build前のサイトからコピーしてきたものを格納
    ├── dist << build後のcssファイルが格納される
    ├── package-lock.json
    ├── package.json
    ├── postcss.config.js
    ├── src
    └── tailwind.config.js
```
※siteフォルダの構成はhal課題仕様です
