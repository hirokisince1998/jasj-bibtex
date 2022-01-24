# 日本音響学会誌 BiBTeX スタイルファイル

jasj.bst (以下，このスタイルファイルと呼ぶ)は，日本音響学会誌, Acoustical Science and Technology 投稿規定 XI 和文誌の原稿(本文)執筆要項 2.本文 〈引用文献記載法と記載例〉に比較的近い形で参考文献リストを生成するためのものです。

## Disclaimer

このスタイルファイルは，電力中央研究所の松井正一氏が製作した jbtxbst.doc をもとに，森 大毅 (宇都宮大学) が改変したものから生成されたものです。

このスタイルファイルの制作・配布等には，日本音響学会は関与していません。また，日本音響学会はこのスタイルファイルについて一切の責任を負っていません。

このスタイルファイルが正常に動作することは保証されていません。このスタイルファイルの使用に伴う責任は，使用する側にあります。

## 符号化方式

このスタイルファイルは UTF-8 で符号化されています。お使いのTeX環境によっては文字エンコーディングの変換が必要になります。

## 配布

このスタイルファイルの1次配布元は
https://github.com/hirokisince1998/jasj-bibtex
です。

再配布は，この README.md の内容とともに行う必要があります。

## 改変，バグ報告

改変は自由ですが，改良したら GitHub のプルリクエストで変更提案をしていただけるとありがたいです。

バグ報告は歓迎します。しかしながら，バグに対応することはお約束できません。


# 使用法

## スタイルファイルの指定

LaTeX ソースファイルと同じディレクトリに jasj.bst を置いてください。

LaTeX ソースファイルに
```
\bibliographystyle{jasj}
\bibliography{○○○}
```
と記述し，BiBTeXで処理してください。○○○.bib は BiBTeX 形式の文献データベースです。

## 音響学会誌, AST誌の引用

学術雑誌に掲載されている論文には Article を使ってください。

例
```
@Article{Ishihara1998,
  author = 	 {石原 豊彦 and 佐山 周次 and 宮川 幸雄 and 筒井 英人},
  title = 	 {海底反射音場に関する一様漸近解},
  journal = 	 {音響学会誌},
  year = 	 {1998},
  volume = 	 {54},
  number = 	 {6},
  pages = 	 {434-442},
}

@Article{Hasegawa2001,
  author = 	 {Jun Hasegawa and Kenji Kobayashi},
  title = 	 {Blood flow noise transducer for detecting intracranial vascular deformations},
  journal = 	 {Acoust. Sci. \& Tech.},
  year = 	 {2001},
  volume = 	 {22},
  number = 	 {1},
  pages = 	 {5-11},
}
```

投稿規定では，日本音響学会誌は "音響学会誌", Acoustical Science and Technology誌は "Acoust Sci. & Tech." と表記することになっています。既存の文献リストをいちいち書き換えなくて済むように，それぞれマクロ jasj, ast を使うこともできます。

例
@Article{Ishihara1998,
  author = 	 {石原 豊彦 and 佐山 周次 and 宮川 幸雄 and 筒井 英人},
  title = 	 {海底反射音場に関する一様漸近解},
  journal = 	 jasj,
  year = 	 {1998},
  volume = 	 {54},
  number = 	 {6},
  pages = 	 {434-442},
}

@Article{Hasegawa2001,
  author = 	 {Jun Hasegawa and Kenji Kobayashi},
  title = 	 {Blood flow noise transducer for detecting intracranial vascular deformations},
  journal = 	 ast,
  year = 	 {2001},
  volume = 	 {22},
  number = 	 {1},
  pages = 	 {5-11},
}
```

## 音響学会講演論文集の引用

音響学会講演論文集の文献には InProceedings を使ってください。

例
```
@InProceedings{terao1980,
  author = 	 {寺尾 道仁 and 関根 秀久},
  title = 	 {インテンシティ測定におけるペアマイクロホン自体の散乱の影響につ
いて},
  booktitle = 	 {音講論集},
  year = 	 {1980},
  month =        {10},
  pages = 	 {479-480},
}
```

投稿規定では，"音講論集" と表記することになっています。既存の文献リストをいちいち書き換えなくて済むように，マクロ asjmeeting を使うこともできます。

例
```
@InProceedings{terao1980,
  author = 	 {寺尾 道仁 and 関根 秀久},
  title = 	 {インテンシティ測定におけるペアマイクロホン自体の散乱の影響につ
いて},
  booktitle = 	 asjmeeting,
  year = 	 {1980},
  month =        {10},
  pages = 	 {479-480},
}
```

booktitle が "音講論集" であった場合に限り，(年)でなく(年.月)と表示されます。

## URLの引用

URLは以下のようにしてください。

例
```
@Misc{ewatermark,
  author =       {日本音楽著作権協会},  
  title = 	 {音楽電子透かし4社を技術認定し，ネット上の違法利用の発生防止に活用},
  howpublished = {\url{http://www.jasrac.or.jp/release/01/10_2.html}},
  year = 	 {参照 2022-01-24},
}
```

## プレプリントの引用

arXiv などのプレプリントサーバでしかアクセスできない論文は，以下のようにしてください。

例
```
@misc{1609.03499,
Author = {Aaron van den Oord and Sander Dieleman and Heiga Zen and Karen Simonyan and Oriol Vinyals and Alex Graves and Nal Kalchbrenner and Andrew Senior and Koray Kavukcuoglu},
Title = {WaveNet: A Generative Model for Raw Audio},
Year = {2016},
Eprint = {arXiv:1609.03499},
}
```

arXiv から文献リストを作るためには [arxiv2bibtex.org](https://arxiv2bibtex.org) というサイトが便利です。
