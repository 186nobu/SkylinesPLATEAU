# （オプション）本Modのビルド方法

# 1 ビルドに必要なツール

Microsoft Visual Studio　(以下、Visual Studioと略。 開発時は Visual Studio Professional 2022 を使用 )

# 2 ビルド手順

① ソースファイルをダウンロードします。

&emsp;ソースファイルは[こちら](https://****)からダウンロード可能です。

② 本MODのソリューションファイル（SkylinesPlateau.sln）をVisual Studioで開きます。

③ソリューション構成を【Release】に、ソリューションプラットフォームを【Any CPU】に設定します。

④ [ビルド]メニュー＞[ソリューションのビルド]を選択し、ソリューション全体をビルドします。

⑤ ビルドが正常に終了すると、SkylinesPlateau\bin\\ReleaseフォルダにMODファイルが生成されます。(本MODの動作に必要なライブラリも同じフォルダにコピーされます。）