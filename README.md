OpenRule1um
=====

## これは何

* NDA（秘密保持契約）が不要の1um設計ルール(3層メタル)と、それに関連するファイルです。
* フェニテックセミコンダクタ(PTS)のCMOS 0.6umプロセスで製造可能とする予定です。
* グリッド単位を0.5umとし、その整数倍で設計ルールを定めています。
（そのためにPTSで製造可能な設計ルールぎりぎりよりは、多少大きくなりますが、その代わり、NDAが不要となります）
* コンタクトとVIAは、接続対象のML1等のレイヤの図形を含む以下のような指定したセルのみを使用可能です。単体でコンタクトやVIAの図形を描画するのは不可です。なおOpenRule1um.xlsxでは、それぞれのサイズが0.5umの整数倍ではないため、0.5umの整数倍となるように少し拡大しています。また各セル内に描画してあるコンタクトやVIAのサイズは実寸ではなく製造時には変更されます（なのでこのセルの中身をいじったいｒ、単独でコンタクトやVIAを描画してはいけません）。またDRC（や回路抽出）は、これらのセルの外形を示すダミーレイヤを用いて行われます。

** CELL_dcont : 拡散(Pdiff/Ndiff)とML1とのコンタクト
** CELL_pcont : ポリ(ゲート)とML1とのコンタクト
** CELL_nsubcont : NwellとML1とのコンタクト
** CELL_psubcont : PsubとML1とのコンタクト
** CELL_via1 : ML1とML2のビア
** CELL_via2 : ML2とML3のビア

* Glade用の↑のセルは、ディレクトリOpenRule1umの中にあります。Gladeでライブラリとしてこのディレクトリを開くことで使用できます。

## 設計ルール

* OpenRule1um.tch : Glade用のテクノロジファイル
* OpenRule1um-drc.py : Glade用のDRCルールファイル
* OpenRule1um_summary.pdf : 設計ルールの要約
* OpenRule1um.xlsx : 設計ルールとレイヤ定義 (A.LSI山田様作のものをベース）

## 近未来的ToDo

* DRCルールファイルの検証
* 回路抽出スクリプト(OpenRule1um-ext.py)
* ロジックなどのスタンダードセル、IP
* 他のEDAツール(wgex等)の設定ファイル

## Author

Junichi Akita (@akita11, akita@ifdl.jp)
