## 目的
今後**n things that you should know about Linux**という資料を作る予定なので、その資料に盛り込む内容のメモ兼学習記録としてこのファイルにLinux関連本の内容を記す。

## MEMO
- vimはCtrl + $で文頭へ、Ctrl + ^で文末へ移動できる。
- catした内容が長すぎて画面から見切れるとき、less -r <file name>かcat | moreで1行ずつや1ページずつを効率的に本のように見れる。

### 圧縮
- **圧縮**は**Lossy Compression（可逆圧縮）**と**Lossless Comperssion（非可逆圧縮）**に大別される。可逆圧縮は効率的にデータを圧縮できるが、解凍前と後でデータは同じものではなくなる。.jpgや.mp3等は多少データが元と異なっていてもピクセルが違う等誰も気づかないのでLossy Compressionが使われる。  
- ファイル結合には**tar**コマンド。ちなみにtarはtape archive（テープアーカイブ）の略。昔はシステムがテープを使ってデータを保存していたことからテープアーカイブと呼ぶらしい。つくられたファイルはtarファイルだったり、tarballと呼ばれたりする。  
```
tar -cvf hoge.tar hoge1 hoge2 hoge3
```
- ただし、tarはただのファイル結合コマンド。tar -cvfをしても、作成されたtarballはファイルサイズが小さくならない。
- よく圧縮に使われるのは以下のコマンド。gzip > bzip2 > compressといった具合の使用頻度。
```
gzip
bzip2
comperss
```
- **dd**コマンドを使うと、削除されたファイルも含めてシステムドライブ全体のファイルをコピーできる。cpでは削除されたファイルはコピーできない。ただし動作は遅いのでフォレンジックの時に使うのが良い。
- 