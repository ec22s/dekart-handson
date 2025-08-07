### FOSS4G KYUSHU 2025 @ 福岡市エンジニアカフェ (2025-08-08)
ハンズオン① WebGIS「Dekartを使ってノーコードでWebGISをやってみよう」
<br>資料とDockerコンテナ

<br>

#### イベント公式URL

  - https://foss4gtokai.my.canva.site/foss4g-kyushu-2025

  - https://foss4g-kyushu2025-handson.peatix.com/ (ハンズオン申込ページ)

<br>

#### 趣旨など

  - [Dekart](https://dekart.xyz) を取り上げた理由

    - 手軽に使えるWebGIS、だが奥深い (発展性がある)

    - 日本語の情報がほとんどないが、知られないのは勿体ない

  - Dekart の概要

    - Light alternative to [CARTO](https://carto.com/) を自称

    - 詳細は当日、各種Webページを開いて説明

  - [クラウドサービスとしてのDekart](https://cloud.dekart.xyz) は Googleアカウント必須

    - [Google Cloud](https://cloud.google.com) 関係 → 当日操作して説明

  - OSSのメリット : セルフホスティング可能

    - 会場限定で用意したローカル版Dekartを説明 (いくつか機能制限あり)


<br>

#### 作業 1. 使用準備

  - 念のため、使うWebブラウザがWebGLに対応していることを確認

    - よほど古い環境でなければ大丈夫と思うが、非対応の場合はDekart内の地図が表示されない

    - https://get.webgl.org を開いてアニメーションが表示されればOK

    - Apple Silicon上の仮想化ソフトウェア内のARM版Windows11だとNG

  - クラウド版Dekartを無料プランで始める

    - https://dekart.xyz を開き Start Free のボタンを押す

    - Googleアカウントの選択画面になる

    - Googleアカウントと紐付いたら Start Mapping in Seconds というタイトルのページに遷移する

      - ここで Create Workspace ボタンを押し、次画面でワークスペース名を入力する

        - 決定したワークスペース名は多分変更できないが、ほぼ使わないので拘らずに

      - Join Existing Workspace は有料アカウントのメンバーに招待された時用

    - You are all set と表示されたら準備完了

<br>

#### 作業 2. 最初の地図を作り、データなしでどのような操作が出来るか調べる

  - You are all set の画面から Create report ボタンを押す

    - メイン画面になり、自動的に Untitled という地図が作成されている

    - 右側にデータ選択欄が出るが、いったんスルー

    - 左上のアイコン [ > ] をクリックしてコントロールを開き、背景地図を変更してみる

      - TODO: 画像を挿入

    - 右側の縦に並ぶアイコンの機能を確かめる

      - TODO: 画像を挿入




<br>

#### DekartをセルフホスティングするDockerコンテナ

  - あああ

  - あああ

