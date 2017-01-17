# AJACS尾張 次世代シーケンサー（NGS）解析・基礎編：関連データベース、ツール

情報・システム研究機構（ROIS）  
データサイエンス共同利用基盤施設
ライフサイエンス統合データベースセンター（DBCLS）  
[仲里 猛留](http://data.dbcls.jp/~nakazato/)  
nakazato@dbcls.rois.ac.jp  
twitter: @chalkless

2017年2月1日 AJACS尾張@藤田保健衛生大学

----

[AJACS尾張](http://events.biosciencedb.jp/training/ajacs64/) > 次世代シーケンサー（NGS）解析・基礎編：関連データベース、ツール

----

## 次世代シーケンサ（とそのデータ）基礎知識
- 言葉
  - 次世代シーケンサ
  - 次世代シーケンサー
  - 新型シーケンサ
  - New-generation Sequencing (NGS)
  - Next-generation Sequiencing (NGS)
  - 他にmassively parallel DNA sequencing とか...
  - 最近は、 High-throughput DNA sequencing (technology) をよく使う印象（略語はNGS）


## 何が新型／次世代なのか?
- 90年代
  - ゲル板
  - ポリアクリルアミドゲル電気泳動 + 蛍光標識ダイデオキシヌクレオチド

[![](http://upload.wikimedia.org/wikipedia/commons/c/cb/Sequencing.jpg)](http://ja.wikipedia.org/wiki/DNA%E3%82%B7%E3%83%BC%E3%82%AF%E3%82%A8%E3%83%B3%E3%82%B7%E3%83%B3%E3%82%B0#.E6.A4.9C.E5.87.BA)
  - [DNAシークエンシング - Wikipedia -- 検出](http://ja.wikipedia.org/wiki/DNA%E3%82%B7%E3%83%BC%E3%82%AF%E3%82%A8%E3%83%B3%E3%82%B7%E3%83%B3%E3%82%B0#.E6.A4.9C.E5.87.BA)も参照

- 00年代
  - キャピラリ
[![](http://motdb.dbcls.jp/?plugin=ref&page=AJACS48%2Fnakazato&src=capillary.jpg)](http://motdb.dbcls.jp/?plugin=ref&page=AJACS48%2Fnakazato&src=capillary.jpg)
ABI PRISM&#174; 3100-Avant Genetic Analyzerより
- 10年代
  - NGSの登場
  - Sanger法（dideoxy法）→ パイロシーケンシング
  - （参考）[[原理の動画 (Illumina)](http://www.youtube.com/watch?v=l99aKKHcxC4)](http://www.youtube.com/watch?v=l99aKKHcxC4)
[![](http://www.hssnet.co.jp/images/2/2_3_10_3_sample05.gif)]()
[次世代シーケンス解析サービス：概要・原理 | 北海道システム・サイエンス株式会社](http://www.hssnet.co.jp/2/2_3_10_1.html)より
  - ようするに顕微鏡＋インターバル撮影／タイムラプス撮影
    -インターバル撮影／タイムラプス撮影： http://www.youtube.com/watch?v=1Az1YX3GgDw
  - 超並列
  - どんなの?
    - Illumina HiSeq  
[![](http://g86.dbcls.jp/~togoriv/wp-content/uploads/2011/05/genomesequencer4_sm.png)]()
    - Illumina MiSeq  
[![](http://g86.dbcls.jp/~togoriv/wp-content/uploads/2013/10/MiSeq-345x345.png)]()
    - PacBio
    [![](http://g86.dbcls.jp/~togoriv/wp-content/uploads/2015/02/pacbio_400.png)]()
    - Togo picture gallery ( http://g86.dbcls.jp/~togoriv/ ) より
[![](https://licensebuttons.net/l/by/2.1/jp/88x31.png)]()
- Ion Torrent

&#169; 2011 DBCLS Licensed under CC 表示 2.1 日本
←クレジットをいれれば、転載・改変・再利用 OK

![developments-in-high-throughput-sequencing-july-2016-edition](https://raw.githubusercontent.com/AJACS-training/AJACS63/master/02_ohta/images/developments_in_high_throughput_sequencing.jpg)
2016年7月時点でのシーケンサー各社の公称スペックをプロットしたものです (引用: Developments in high throughput sequencing – July 2016 edition, https://flxlexblog.wordpress.com/2016/07/08/developments-in-high-throughput-sequencing-july-2016-edition/ )。



----

[AJACS尾張](http://events.biosciencedb.jp/training/ajacs64/) > 次世代シーケンサー（NGS）解析・基礎編：関連データベース、ツール

----
