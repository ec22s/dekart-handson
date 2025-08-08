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

  - 会場限定で用意したローカル版Dekartを説明 (いくつか機能の制約あり)

  - クラウド版が502エラー等で使えない場合もある

    <img height="128" src="https://github.com/user-attachments/assets/c125ce4c-3879-48b8-a4df-7e804fbbdecd" />

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

- 地図名を任意に変えてみる

- 右側にデータ選択欄が出るが、いったんスルー

- 左上のアイコン [ > ] をクリックしてコントロールを開き、背景地図を色々変えてみる

  <img height="192" src="https://github.com/user-attachments/assets/21830cb7-0c8a-4b30-846d-3b6bce7f4e1a" />

- 右側の縦に並ぶアイコンの機能を確かめる

  <img height="192" src="https://github.com/user-attachments/assets/a5573de4-b29e-432d-8260-45a636bdf8dd" />

<br>

#### 作業 3. データファイル (CSVまたはGeoJSON) を準備する

- 右側のデータ選択欄に Upload File ボタンがあり、CSVとGeoJSONが利用可能

  <img height="64" src="https://github.com/user-attachments/assets/dc8ef2c3-0e77-47df-9984-43c9fcbc39c5" />

- CSVは緯度・経度を含む点データなら何でも良く、例えば下記などを使える

  - [米国の機関 - 太平洋・大西洋のハリケーンの位置情報 (年別)](https://ocean.weather.gov/climo/download.php)

  - [G空間情報センターでCSVのバス停を検索](https://www.geospatial.jp/ckan/dataset/?res_format=CSV&tags=%E3%83%90%E3%82%B9%E5%81%9C)

  - ファイル名は英数字以外でも可

  - ヘッダの列名が国際標準<u>でない</u>文字コードだとDekartで文字化けする (読み込み自体は可)

- GeoJSONは点・線・面いずれも可で、例えば下記などを使える

  - [Data of Japan 行政区分](https://github.com/dataofjapan/land)

  - [G空間情報センター 歩行空間ネットワークデータ等](https://www.geospatial.jp/ckan/dataset/0401)

  - GeoJSONの確認には [geojson.io](https://geojson.io) (Webサイト) が便利

    - データを表形式で表示でき、列の追加も可能

- GeoJSONでデータ量が多いものはエラーになる

  - 例えば [Large GeoJSON Files サンプル](https://samples.azuremaps.com/demos/large-geojson-files) の点 (41MB), 線 (16MB), 面 (80MB) いずれもNG

  - CSVでデータ量の制約があるかは調査中

<br>

#### 作業 4. CSVまたはGeoJSONをアップロードし、地図に表示する

- 1つの地図 (Report) に複数のファイルをアップロードできる

- 各データがレイヤーとなり、左のレイヤーパネルからデータを確認できる

  <img height="128" src="https://github.com/user-attachments/assets/3cebd84a-7aa4-4aa0-8780-af45840d9e08" />

- レイヤーの上下関係や表示/非表示を変えられる

- 各レイヤーの設定を確認し、色など自由に変えてみる

  - アイコン「 ⌵ 」や「︙」で詳細メニューを開ける

  - 色などの基準となる列を選択することで、列値を地図に可視化できる

    <img height="192" src="https://github.com/user-attachments/assets/e8ca820b-3bad-4420-98b9-c7db3df89342" />

- レイヤーパネル最上部のアイコンを切り替えて、フィルタやツールチップ等の設定ができる

  - ブラシ (Brush) の効果は未確認

- ここで行った<b>「データをレイヤ化して地図に乗せ、レイヤ別に様々な可視化をする」</b>のがGISの基本

  - ブラウザとデータさえあれば、Dekartで簡単に出来る

- 休憩前の作業でここまで来れれば理想

<br>

#### 作業 5. Dekartの便利機能 (Report, Readme) の確認

- 作成した地図はReportとして自動保存され、新規作成・編集・アーカイブ化 (削除の代わり) ができる

- Reportの共有機能を確認する

  - リンクを作成し、それを渡したDekartユーザは誰でも見れる

  - 共有時の設定により、Reportのデータダウンロードや複製 (Fork) も可能になる

  - BIプラットフォーム「Tableau Public」に似ており、使い勝手が良い

- データ以外に「Readme」としてメモを付けられるのを確認 (管理に役立つ)

<br>

#### 作業 6. BigQueryを使う公式サンプルをやってみる

- BigQuery : Google Cloud内のDBサービス (データ分析や大量・高速処理向き)

  - publicなデータが多数用意されている

  - クラウド版DekartからBigQueryを使うには、予め自分のGoogleアカウントでGoogle Cloudのプロジェクトを作っておく
 
  - ハンズオン用のローカル版Dekartは、自分のGoogle CloudのプロジェクトがなくともBigQueryを使える

    - データ新規作成 > SQL Queryを選択 > BigQueryを使うサンプルSQLを作成できる

      <img height="128" src="https://github.com/user-attachments/assets/8646ef8b-ceb8-40b0-be0f-cebd7cf17d07" />

    - SQL未経験の人も、このサンプルを見れば雰囲気はつかめるかも

- [BigQuery Overture Maps Examples](https://dekart.xyz/docs/about/overture-maps-examples/)

  - 最後の方に六角形メッシュや3Dの例あり (ページ中ほどのサンプルより、むしろ簡単かも)

- [BigQuery Public Datasets](https://dekart.xyz/docs/about/kepler-gl-map-examples/)

- サンプル掲載のSQLを画面右側のパネルに貼り付け実行するだけで、データが作成され地図に可視化される

  - サンプルによってはクエリが古く修正が必要 (TODO: 詳細説明を入れる)

- データの作成・変更をSQLに集約すると、複雑なデータ処理も「誰でもすぐ再現できる」ものになる

- SQLにコメントを入れたりバージョン管理を行うことで、データを使う共同作業に役立つ

- 一方、SQLが複雑になると「何をやっているか」が見えにくい、修正できる人が限られる、など不利な点も出てくる

<br>

#### DekartをセルフホスティングするDockerコンテナ

  - TODO: 説明を入れる
