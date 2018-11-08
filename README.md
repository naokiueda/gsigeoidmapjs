# gsigeoidmapjs
small Javascript class to get Geoid Height from GSI geoid data

説明：
国土地理院のジオイドデータをJavaScriptで使うためのクラスです。
国土地理院にてダウンロード配布（https://fgd.gsi.go.jp/download/geoid.php）されているASCII形式のデータ「gsigeo2011_ver2.asc」を予め読込んであります。

将来ASCIIデータに変更があった場合のために、ASCIIデータを読込んで本JavaScriptクラスを生成するC#のコンソールプログラムのソースも入れてあります。

注意事項：
①国土地理院のジオイドデータでは、無効値に「999.0000」が入っていますが、このクラスでは無効値のとき0が返るようになっています。なおデータ中に「0.0000」のジオイド値のデータは存在しませんので、0のときは無効値扱いと解釈して問題ありません。

②小数点以下3桁目までは国土地理院のジオイド高計算サイト（https://vldb.gsi.go.jp/sokuchi/surveycalc/geoid/calcgh/calcframe.html）と同じ数値が出ますが、小数点以下4桁目で異なる値が出る場合があります。


利用方法の例
var gm = new GsiGeoid();//インスタンスを作成
var geoidValue = gm.getGeoid(35.00000,135.00000); //緯度、経度の順
⇒37.05534が返ります。
