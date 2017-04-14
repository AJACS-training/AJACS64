## AJACS尾張
# 次世代シーケンサー（NGS）解析・基礎編：関連データベース、ツール

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
  - Next-generation Sequencing (NGS)
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
[![](http://togotv.dbcls.jp/pic/201105_GenomeSequencer_4.png)]()
    - Illumina MiSeq  
[![](http://togotv.dbcls.jp/pic/201310_genomesequencer7.png)]()
    - PacBio
    [![](http://togotv.dbcls.jp/pic/201507_genomesequencer8_2.png)]()
    - Ion Torrent

    - Togo picture gallery ( http://togotv.dbcls.jp/ja/pics.html ) より
[![](https://licensebuttons.net/l/by/2.1/jp/88x31.png)]()

&#169; 2011 DBCLS Licensed under CC 表示 2.1 日本
←クレジットをいれれば、転載・改変・再利用 OK

![developments-in-high-throughput-sequencing-july-2016-edition](https://raw.githubusercontent.com/AJACS-training/AJACS63/master/02_ohta/images/developments_in_high_throughput_sequencing.jpg)
2016年7月時点でのシーケンサー各社の公称スペックをプロットしたもの (引用: Developments in high throughput sequencing – July 2016 edition, https://flxlexblog.wordpress.com/2016/07/08/developments-in-high-throughput-sequencing-july-2016-edition/ )。

## NGSデータの規模
- 【実習】どのくらいのデータ量になるか考えてみましょう
  - ゲル板：750 (base/lane) × 48/4 lanes <span style="color: rgb(250, 250, 250)">= 9kbase</span>
  - キャピラリ：500 (base/lane) × 96 lane <span style="color: rgb(250, 250, 250)">= 48kbase</span>
  - 次世代： 36 (base/seq) × 300M seq/run <span style="color: rgb(250, 250, 250)">= 10.8Gbase = 10,800,000kbase</span>
  - ↑これらの数字は規模感をつかむだけなので、ざっくりな数字になっています（1 runにかかる時間は比較してないですし）
  - ↑これらの数字は「塩基数」であって、シーケンサの出力である「画像データ」のデータサイズでないことに注意！
  - そして、その画像データはSRAには登録されていない

## NGSの利用範囲
  - ゲノム、発現解析、メタゲノム解析、ChIP-Seq（転写因子解析）、SNP解析、...
    - 目的によって必要なデータ量も違う  [![](http://motdb.dbcls.jp/?plugin=ref&page=AJACS48%2Fnakazato&src=NGSreq.png)]()
    - 機器に合った利用を  [![](http://motdb.dbcls.jp/?plugin=ref&page=AJACS48%2Fnakazato&src=NGSinst.png)]()

配布物参照。あとでここにもたしておきます。

----

[AJACS尾張](http://events.biosciencedb.jp/training/ajacs64/) > 次世代シーケンサー（NGS）解析・基礎編：関連データベース、ツール

----
## Slides
![images/AJACS64_03_nakazato_001.jpg](images/AJACS64_03_nakazato_001.jpg)
---

![images/AJACS64_03_nakazato_002.jpg](images/AJACS64_03_nakazato_002.jpg)
---

![images/AJACS64_03_nakazato_003.jpg](images/AJACS64_03_nakazato_003.jpg)
---

![images/AJACS64_03_nakazato_004.jpg](images/AJACS64_03_nakazato_004.jpg)
---

![images/AJACS64_03_nakazato_005.jpg](images/AJACS64_03_nakazato_005.jpg)
---

![images/AJACS64_03_nakazato_006.jpg](images/AJACS64_03_nakazato_006.jpg)
---

![images/AJACS64_03_nakazato_007.jpg](images/AJACS64_03_nakazato_007.jpg)
---

![images/AJACS64_03_nakazato_008.jpg](images/AJACS64_03_nakazato_008.jpg)
---

![images/AJACS64_03_nakazato_009.jpg](images/AJACS64_03_nakazato_009.jpg)
---

![images/AJACS64_03_nakazato_010.jpg](images/AJACS64_03_nakazato_010.jpg)
---

![images/AJACS64_03_nakazato_011.jpg](images/AJACS64_03_nakazato_011.jpg)
---

![images/AJACS64_03_nakazato_012.jpg](images/AJACS64_03_nakazato_012.jpg)
---

![images/AJACS64_03_nakazato_013.jpg](images/AJACS64_03_nakazato_013.jpg)
---

![images/AJACS64_03_nakazato_014.jpg](images/AJACS64_03_nakazato_014.jpg)
---

![images/AJACS64_03_nakazato_015.jpg](images/AJACS64_03_nakazato_015.jpg)
---

![images/AJACS64_03_nakazato_016.jpg](images/AJACS64_03_nakazato_016.jpg)
---

![images/AJACS64_03_nakazato_017.jpg](images/AJACS64_03_nakazato_017.jpg)
---

![images/AJACS64_03_nakazato_018.jpg](images/AJACS64_03_nakazato_018.jpg)
---

![images/AJACS64_03_nakazato_019.jpg](images/AJACS64_03_nakazato_019.jpg)
---

![images/AJACS64_03_nakazato_020.jpg](images/AJACS64_03_nakazato_020.jpg)
---

![images/AJACS64_03_nakazato_021.jpg](images/AJACS64_03_nakazato_021.jpg)
---

![images/AJACS64_03_nakazato_022.jpg](images/AJACS64_03_nakazato_022.jpg)
---

![images/AJACS64_03_nakazato_023.jpg](images/AJACS64_03_nakazato_023.jpg)
---

![images/AJACS64_03_nakazato_024.jpg](images/AJACS64_03_nakazato_024.jpg)
---

![images/AJACS64_03_nakazato_025.jpg](images/AJACS64_03_nakazato_025.jpg)
---

![images/AJACS64_03_nakazato_026.jpg](images/AJACS64_03_nakazato_026.jpg)
---

![images/AJACS64_03_nakazato_027.jpg](images/AJACS64_03_nakazato_027.jpg)
---

![images/AJACS64_03_nakazato_028.jpg](images/AJACS64_03_nakazato_028.jpg)
---

![images/AJACS64_03_nakazato_029.jpg](images/AJACS64_03_nakazato_029.jpg)
---

![images/AJACS64_03_nakazato_030.jpg](images/AJACS64_03_nakazato_030.jpg)
---

![images/AJACS64_03_nakazato_031.jpg](images/AJACS64_03_nakazato_031.jpg)
---

![images/AJACS64_03_nakazato_032.jpg](images/AJACS64_03_nakazato_032.jpg)
---

![images/AJACS64_03_nakazato_033.jpg](images/AJACS64_03_nakazato_033.jpg)
---

![images/AJACS64_03_nakazato_034.jpg](images/AJACS64_03_nakazato_034.jpg)
---

![images/AJACS64_03_nakazato_035.jpg](images/AJACS64_03_nakazato_035.jpg)
---

![images/AJACS64_03_nakazato_036.jpg](images/AJACS64_03_nakazato_036.jpg)
---

![images/AJACS64_03_nakazato_037.jpg](images/AJACS64_03_nakazato_037.jpg)
---

![images/AJACS64_03_nakazato_038.jpg](images/AJACS64_03_nakazato_038.jpg)
---

![images/AJACS64_03_nakazato_039.jpg](images/AJACS64_03_nakazato_039.jpg)
---

![images/AJACS64_03_nakazato_040.jpg](images/AJACS64_03_nakazato_040.jpg)
---

![images/AJACS64_03_nakazato_041.jpg](images/AJACS64_03_nakazato_041.jpg)
---
