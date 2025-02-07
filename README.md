# modernTemplate
モダンな「Web制作」開発環境を構築できる。  
このディレクトリ構造は小規模程度のサイト（〜50ページ相当）を想定している


## 階層構造  
~~~
dist（公開フォルダ。納品フォルダ。当該サイトの実際の表示。distはwebpackのoutput未設定の場合のディレクトリ名から命名）  
    ┕include（_header.php,_footer.php,_main-menu.phpなどincludeやrequire_onceするファイル群を格納）  
    ┕resources（css,js,images,fonts,libs,videosなどを格納する）  
        ┕libs  
            ┕function.php（PHPで書かれたファイルの処理をおこなう。相対パスのURLの出力やPHPのバージョンクエリを付与したりテンプレートファイルを読み込んだりする）  
    ┕index.html or index.php  
    ┕各ディレクトリ  
src（作業フォルダ。開発フォルダ。sassや圧縮前のjs、fontなど格納。）  
    ┕assets（HTML、画像、Web Fonts などの静的リソースを格納するフォルダ）  
        ┕fonts（サイトオリジナルのフォントを格納）  
        ┕images  
    ┕js（圧縮前のjsを格納、実際に編集するjsを格納する、圧縮はgulpで行ってdistの任意のフォルダに格納する）  
        -┕vendor（ページ単体で使用するjsや外部jsを格納する）  
            ┕ディレクトリ名.js（ディレクトリ配下で使用するjsを格納する）  
        ┕index.js（サイト全体で使用するjs。webpackでバンドルされてmain.jsとしてdestされる）  
        ┕モジュール.js（main.jsにバンドルされるモジュールのjsファイル）  
    ┕sass（実際に編集するscssを格納。個人ページの場合はCSS設計はFLOCSS(大規模) or SMACSS(小規模、bootstrapのようなもの)にする。共通ファイルとして_common.scss、_normalize.scss(リセットCSS)、_setting.scss(変数やmixinを格納する)）  
        ┕custom.scss（各sassファイルをimportするファイル）  
        ┕layout.scss（サイト全体をレイアウトするscssを格納する）  
        ┕ディレクトリ名.scss（ディレクトリ配下で使用するscssを格納する）  
node_module（gulpやwebpackなどのプラグインを格納している。パッケージインストールすると追加される）  
package.json（npm init -yで追加）  
(gulpfile.jsなど)  
~~~

_**※ディレクトリ構成は検討の余地あり**_  
- Web starter kitを採用するのもあり  


## 使用言語・サービス・ツール（2020/06/15現在）  
- npm-scriptsを利用する。（Gulpはバージョンによって差異が生じるから）  
    https://ics.media/entry/12226/  
- Webpackを利用する（Gulpは利用を考える。Webpackで事足りているから）  
    https://ics.media/entry/12140/  
    https://ics.media/entry/17376/  
- Bootstrapを使う  
    https://ics.media/entry/17749/  

###  使用言語等
- HTML5
- CSS3
- **JavaScript**
- **PHP**
- **MySQL**(PostgreSQL（heroku）、SQLite（React）、sequelize)

### altCSS
- **Sass**
- （Stylus?）

### CSS設計
- **BEM**
- _FLOCSS_※個人的な嗜好

### CSSフレームワーク
- BootStrap など

### altJS
- _TypeScript_（+ WebPack）（TypeScriptがあればbabelは不要かどうか？）

### Javascirptフレームワーク
- React.js
- Vue.js

### サーバーサイドJS
- Node.js
- Express
- sequelize

### タスクランナー
- **npm-scripts**
- **WebPack**（正確にはモジュールバンドラー）
- **babel**（正確にはトランスパイラ）
- （Gulp）（npm-scriptsがある環境で必要性があるか？と言われているらしい（出典元を探す））

### CMS
- _WordPress_

### 開発環境
- npm（Node Package Manager）（クロスプラットフォームな開発を吸収できるか？）
- Node.js
- **Git**（分散型バージョン管理）
- _SourceTree_（Git GUIクライアント）
- **Docker**（仮想化開発環境、軽量）
 
### その他(よくわかってなかったり、必要だと思ってたり、願望だったり)
- SPA
- PWA
- File API
- WebStorage API（LocalStroage）
- WebSocket
- Canvas
- Three.js
- AWS EC2（サーバ、動的サイト、期限付き無料枠（1ヶ月））、RDS（データベースサーバ）、S3（SmartStorageService、ストレージ、静的サイト、無期限無料枠）
- （Azure,GCP）
- Linuxコマンド
- VBAマクロ
- Laravel
- Composer
- **応用情報技術者**（高度情報処理技術者試験）
- **PM**（高度情報処理技術者試験）
- ウェブ解析

### 注目
- Next.js

_太字は特に重視したいこと、イタリックは個人的主流_



## 信頼の置ける情報ソース（Web標準やSEOに困ったら見る）
_※メディアをできれば信頼する_  
_※個人はあまり信頼しない（情報ソースが古い、情報を間違って解釈している、読み解くことができない、そもそも誤っている、標準から外れている）_  

- ICS.media  
    https://ics.media/  
- ferret  
    https://ferret-plus.com/  
- Google公式（Google developer、Google support、Google Devs Japanなど）  
    https://developers.google.com/web/tools/starter-kit?hl=ja  
    https://support.google.com/webmasters/answer/35291?hl=ja  
    https://support.google.com/webmasters/answer/7451184?hl=ja  
    https://developers.google.com/search/docs/guides/get-started?hl=ja  
    https://developers-jp.googleblog.com/  
- HTML5 Exparts.jp（検討中）  
    https://html5experts.jp/  


## 追記情報
### 2020/06/09追記  
空のディレクトリに.gitkeepファイルを追加しました。  
.gitkeepは隠しファイルなのでFinder上で`cmd + shift + .`で表示されます。  
https://qiita.com/tommy_aka_jps/items/b2ae85cbeab77e12a925  
https://qiita.com/ndxbn/items/f124d2b183b60cb074e2  
