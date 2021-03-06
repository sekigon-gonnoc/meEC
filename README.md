# meEC

|![](img/niz0.JPG) |![](img/niz1.JPG) |
|-|-|
|NIZスイッチLEDなし|NIZスイッチLEDあり|
|||
|![](img/bto0.JPG) |![](img/bto1.JPG) |
|BTOスイッチLEDなし|BTOスイッチLEDあり|

- [部品リスト](#部品リスト)
  - [キットに同梱されている部品](#キットに同梱されている部品)
  - [キット以外に必要な部品](#キット以外に必要な部品)
- [組み立て手順](#組み立て手順)
  - [EC microにType-Cコネクタをはんだ付けする](#ec-microにtype-cコネクタをはんだ付けする)
  - [(メイン基板にLEDをはんだ付けする)](#メイン基板にledをはんだ付けする)
  - [メイン基板にリセットスイッチをはんだ付けする](#メイン基板にリセットスイッチをはんだ付けする)
  - [メイン基板にEC microを取り付ける](#メイン基板にec-microを取り付ける)
  - [トッププレートにスペーサーをネジ止めする](#トッププレートにスペーサーをネジ止めする)
  - [トッププレートにスイッチを取り付ける](#トッププレートにスイッチを取り付ける)
  - [トッププレートとメイン基板をネジ止めする](#トッププレートとメイン基板をネジ止めする)
- [ファームウェア](#ファームウェア)

## 部品リスト
### キットに同梱されている部品
|部品|数|
|-|-|
|EC micro|1|
|USB Type-C コネクタ|1|
|メイン基板|1|
|トッププレート|1|
|タクトスイッチ|1|
|M2ネジ|8|
|M2x5スペーサー|4|
|ゴム足|4|


### キット以外に必要な部品

|部品|数|入手先|
|-|-|-|
|12ピンコンスルーまたはピンヘッダ|2|遊舎工房など|
||||
|**BTOスイッチ用**|
|ADELCPS 静電容量スイッチ4点セット|4キー分|https://yushakobo.jp/shop/a0500es-01-1/, https://btoshop.jp/2020/09/25/adelcps/mp
|ラバードーム|必要分|https://yushakobo.jp/shop/a0500er-01-1/, https://btoshop.jp/2020/09/25/adelcpru/|
||||
|**NIZ ECスイッチ用**|
|NIZ EC Switch |4|https://www.nizkeyboard.com/collections/ornaments/products/2019-new-niz-ec-switch|
|ラバードーム|必要分|https://www.nizkeyboard.com/collections/ornaments/products/ec-silicone-domes-35g-45g-55g, 上記ラバードームも可|
|コニックリング|4|NIZ用のバラ売りはないのでBTOのセットなどから流用する|
||||
|**LED対応版オプション**|||
|YS-SK6812MINI-E|4|遊舎工房など|

## 組み立て手順
### EC microにType-Cコネクタをはんだ付けする
- 出荷時に貼り付けてあるカプトンテープは剥がさないほうが他の部品とブリッジしづらい
![](img/img2.JPG)

### (メイン基板にLEDをはんだ付けする)
- 行によってLEDの向きが違うので注意
  - シルクに`/`マークがついている方にLEDの切り欠きを合わせる

### メイン基板にリセットスイッチをはんだ付けする
### メイン基板にEC microを取り付ける
- コンスルーを使う場合、EC micro側もメイン基板側もはんだ付けは不要
- コンスルーはスイッチ側に寄せる
![](img/img7.JPG)

### トッププレートにスペーサーをネジ止めする
### トッププレートにスイッチを取り付ける
- BTOのスイッチの場合は切り欠きが横向きになるように嵌めて、ラバーシートの切り欠きにスイッチの突起を通す
- ステムの向きに注意
![](img/img5.JPG)
![](img/img6.JPG)
### トッププレートとメイン基板をネジ止めする
- トッププレートの穴にコンスルーが通っている（コンスルーを押しつぶしていない）ことを確認

## ファームウェア
- リポジトリを取得
  - https://github.com/sekigon-gonnoc/qmk_firmware/tree/dev/sekigon
- atmel-dfu経由で書き込み
  - リセットすると自動でブートローダが起動する
  ```
  make meec:dfu
  ```
