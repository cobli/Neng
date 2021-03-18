# Neng
表計算ソフトで実現した会計帳簿です。使い慣れた表計算ソフトのインターフェイスがそのまま使えるので便利です。
* Nengの内容は完全にオープンで、自由に改変出来て、無料で使うことが出来ます。特定のシステムに依存しないので、将来使えなくなる心配もありません。
* 自前で法人確定申告する零細企業を応援する目的で税務を意識して開発しました。税制により変更される部分はeTAXに任せ、Neng自体は簡素に作ってます。

使用環境　Googleスプレッドシート(無料)　ExcelファイルをGoogleDriveにアップロードした上で使用して下さい。
* Excel、Excel Online(無料)、LibreOffice Calc(無料)上でも動作しますが、操作説明はGoogleスプレッドシートに合わせてます。
* GoogleスプレッドシートとExcel Onlineはクラウド上で動作します。ExcelとLibreOffice Calcはインストール型で、応答が早いです。
* フォントは、ExcelとLibreOffice Calcでは游ゴシックですが、GoogleスプレッドシートではArialに変更されます。

## 概要
表計算ソフトを利用し、仕訳帳、総勘定元帳、精算表、財務諸表、在庫管理、の各機能を実現している持分会社(合同会社等)用の会計帳簿のテンプレートです。(マクロは使ってません。)  
* 株式会社では 社員資本 → 株主資本 の読み替えとeTAX用のデータ変更が必要です。
* 法人確定申告用のeTAXに取り込める財務諸表と勘定科目内訳明細書のデータも作ります。
* eTAX用のデータはcsv形式のファイルでエクスポートする必要があります。Excel OnlineではCSV Import+Exportアドイン(無料)をインストールすればエクスポートが可能になります。

### シートの説明
全部で9つ (元帳が加われば10) のシートがあります。
1. 仕訳シート　(元帳シート)　仕訳帳と総勘定元帳を兼ねるシートです。  全ての取引を取引順に並べた場合は仕訳帳になり、それを科目IDでソートすれば総勘定元帳になります。
2. 在庫シート　商品の登録、在庫の集計機能、期末棚卸高 の計算機能があります。
3. 集計シート　勘定科目の設定、精算表 の機能を持つシートです。  諸表シートの損益計算書や貸借対照表に載せていない科目残高もここで確認出来ます。
4. 諸表シート　損益計算書、貸借対照表、社員資本等変動計算書がまとまってます。  仕訳シートに全ての仕訳を入力するだけで自動的に作成されます。
5. 月次シート　複数の勘定科目の合計値を月次解析します。  法人確定申告書に添付する事業概況説明書の月毎の値はこの機能で計算出来ます。
6. Zaimシート　個別注記表、損益計算書、貸借対照表、社員資本等変動計算書をeTAXに取り込むためのデータを作ります。
7. Kamokシート　勘定科目内訳明細書をeTAXに取り込むためのデータを作ります。
8. Ex2eTAXシート　ZaimシートとKamokシートからエクスポートしたcsv形式のファイルをeTAXが定める形式に変換するバッチファイルです。
9. 説明シート　この会計帳簿の使い方を説明します。

* 仕訳シートに仕訳データを入力するだけで、その他の値は自動的に計算されて更新されます。
* 仕訳データの入力時に残高表示もされるので、預金通帳の残高と照合しながら仕訳出来ます。
* 在庫管理をする場合には在庫シートにも期首と期末の棚卸データを入力します。

### 行の追加方法  
* (仕訳シート)仕訳データの追加
* (在庫シート)商品の登録の追加
* (集計シート)勘定科目の追加
* (月次シート)科目数の増加  

必要な場所に行を挿入し、その行に淡黄色のセルを含む同一シート内の任意の行をコピーしてから白色のセルにデータを入力(コピー元の値を変更)します。
