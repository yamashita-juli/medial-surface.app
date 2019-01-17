# medial-surface.app

## I. 名称：　medial-surface.app

## II. 内容　
 入力された STL file の medial surface （中立面）に、指定の厚みをつけた STL file を作成する。

## III. 中立面 medial surface とは

　中立面(medial surface, medial axis)は、形状表面から等距離にある点で構成される面または線である（図III-1参照）。中立面に厚みはなく、枝分かれがあるため多様体でもない。

図III-1 中立面（Medial Axis / Medial Surface）の例　

![上図](http://homepages.inf.ed.ac.uk/rbf/HIPR2/figs/bitanmed.gif)
![下図](http://www.riken.jp/brict/Yoshizawa/Research/Images/hand-half.jpg)

[上] 2次元形状（長方形）のmedial axis の例（出典： http://homepages.inf.ed.ac.uk/rbf/HIPR2/skeleton.htm ）

[下] より複雑な3次元形状の medial surface の例（出典： http://www.riken.jp/brict/Yoshizawa/Research/Skeleton.html ）

## IV. システム概要
1.	入力された3次元形状モデルSTL fileの中立面（medial surface）を抽出する
2.	1で抽出された中立面に対して厚みを付与し、STLファイルで保存する
3.	入力された3次元形状モデルが、2で生成された中立面形状モデルより薄い部分は入力形状のままで、厚い部分は中立面形状となるように形状同士の合成を行う
4.	入力ファイル及び出力ファイルのフォーマットはSTL（Stereo Lithography）のASCIIフォーマット、バイナリーフォーマットとする
5.	中心面抽出は外部プログラム：Powercrust Software ( http://web.cs.ucdavis.edu/~amenta/powercrust.html )を用いる（同包）
6.	3次元形状モデルの合成は外部プログラム：Cork Boolean Library (https://github.com/gilbo/cork )を用いる（同包）
7.	厚み形状生成、及びその他補助的な形状データ操作はMeshLab ( http://meshlab.sourceforge.net/ )のスクリプト実行機能を用いる（ver.1.3.3で動作確認、2016/12リリース版では動作しない模様）

・システム要件：

Apple Macintosh Computer

CPU: Intel 64bit CPU（Intel Core i5、i7推奨）

OS: macOS（OS X）10.10以上（10.13.6にて動作確認）

Memory: 4GB以上推奨



## V. システム使用方法

1.	インストール・アンインストール

(1) medial-surface.dmgをダブルクリックしてマウントする

マウントされたイメージ内にある「medial-surface.app」をアプリケーションフォルダに、「powercrust」及び「cork」を適当なディレクトリにコピーする

corkの実行にはGMP (https://gmplib.org/ ) が必要となる

macOSの場合はHomebrew (http://brew.sh/index_ja.html ) でのインストールが容易である

①	Homebrewをインストールする
以下を実行
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

※途中2回ほどパスワードを求められる

②	HomebrewでGMPをインストールする

brew install gmp

アンインストールを行う場合は上記3ファイルを削除する

(2) MeshLab 1.3.3 をインストールする


2.	起動

「medial-surface.app」をダブルクリックする


3.	設定・使い方

添付の medial-surface-app.pdf を参照

以上
