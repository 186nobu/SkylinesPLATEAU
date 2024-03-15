# 環境構築手順書

# 1 本書について

本書では、3D都市モデルを都市育成シミュレーションゲーム"Cities: Skylines"にインポートするMOD（SkylinesPLATEAU。以下「本MOD」という。）の利用環境構築手順について記載しています。本MODの構成や仕様の詳細については以下も参考にしてください。

[技術検証レポート](https://****)

# 2 動作環境

本MODの動作環境は以下のとおりです。

<READMEから貼り付け>


# 3 利用手順手順

Cities: Skylinesを購入し使用できる環境を整えてください。

[こちら](https://****/)
から本MODをサブスクライブし、Cities: Skylinesのコンテンツマネージャーで有効化します。


# 4 ビルド手順

自身でソースファイルをダウンロードしビルドを行うことで、MODを生成することができます。\
ソースファイルは
[こちら](https://****)
からダウンロード可能です。

（1）本MODのソリューションファイル（SkylinesPlateau.sln）をVisualStudio2019で開きます。

（2）[ビルド]メニュー＞[ソリューションのビルド]を選択し、ソリューション全体をビルドします。

（3）ビルドが正常に終了すると、bin\\Release\SkylinesPlateauフォルダにMODファイルが生成されます。(本MODの動作に必要なライブラリも同じフォルダにコピーされます。）


# 5 準備物一覧

アプリケーションを利用するために以下のデータを入手します。

| | データ種別 | 機能                                                                                                                        | 用途                 | 入力方法           |
| ---------- | --------------------------------------------------------------------------------------------------------------------------- | -------------------- | ------------------ | ------------------------------------------------ |
| ①          | 3D都市モデル(CityGML)G空間情報センターから取得します。<br> https://front.geospatial.jp/                                         | 全般                 | 全般               | 格納フォルダパス指定                             |


本MODでは、3D都市モデル標準製品仕様書（第3.4班）に準拠した3D都市モデルの地形、土地利用、道路、建築物、都市計画決定情報の形状（LOD1）と属性を活用します。

| 地物       | 地物型            | 属性区分 | 属性名                                 | 内容                 |
| ---------- | --------------| --------- | --------------------------- | --------- | 
 |共通	  |core:CityModel  |空間属性  |gml:lowerCorne、gml:upperCorner  |データ範囲 |
 |地形  |dem:TINRelief		 |空間属性  |dem:tin/gml:posList							 |形状 |
 |土地利用  |luse:LandUse  |空間属性  |luse:class								 |土地利用用途 |
 |道路  |tran:Road			  |空間属性  |tran:lod1MultiSurface、gml:posList  |形状 |
  |			 |								|主題		  |tran:function										 |機能 |
  |			 |								|			  |uro:width											|幅員 |
  |			|							|					 |uro:widthType								|幅員区分 |
 |建築物  |bldg:Building  |空間属性	 |bldg:lod1Solid、gml:posList				 |形状 |
  |			 |							|主題			  |bldg:storeysAboveGround				|地上階数 |
  |			|						 |					 |bldg:measuredHeight						  |計測高さ |
  |			|						 |					 |bldg:usage													 |用途 |
  |			|						 |					 |uro:buildingID										  |建物ID |
  |			|						 |					 |uro:orgUsage、uro:orgUsage2 			|詳細用途 |
  |			|						 |					 |gml:name											  |名称 |
 |都市計画決定情報  |urf:UrbanPlanningArea  |空間属性  |urf:lod1MultiSurface、gml:posList  |形状 |
  |			|						 |	主題			  |urf:function										 |用途地域の区分 |
