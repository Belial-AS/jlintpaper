# jlintpaper

LaTeXで書かれた日本語の論文やレポートをチェックし，正しくない可能性がある箇所を指摘します．
間違った指摘があることに注意して下さい．

主に卒論や修論のチェックに使うことを想定しています．

## 使い方
コマンドラインから以下のように実行して下さい．
ruby 2.0.0 以降が必要です．

> ruby jlintpaper.rb sample.tex

\input は解釈しません．
単一の.texファイルに格納されている必要があります．

# チェック結果の例
```code:text
=====================================================
 間違った指摘をする可能性が十分あるので注意すること!
 checked by jlintpaper.rb 0.1.0
=====================================================

===全角数字は使わない===
3: 2章では関連研究について述べ、>>>３<<<章で提案手法について述べる。

===文末に句点やピリオドがない(?)===
7..8: ときどき，全角文字の間に 空白が紛れ込んでいることがありません?>>> <<<

===章や節，図表番号を直接指定している?(\refを使うべき)===
3: >>>2章<<<では関連研究について述べ、３章で提案手法について述べる。

===「です・ます」調は使わない．「だ・である」調を使う（謝辞の中は良い）．===
9: 完璧なチェックは出来ないけど，少しは役には立つと思い>>>ます。<<<

===口語表現「けど」→「が」===
9: 完璧なチェックは出来ない>>>けど<<<，少しは役には立つと思います。

===挙げられるの間違い(?)===
13: 以下のような問題点が>>>上げられる<<<．

===$log$のように書いた場合，l*o*gという意味．関数ならば\log，イタリックならば\textit{abc}を使うこと===
11: >>>イタリックの代わりに数式モードで $xyz$<<< とか書いてないだろうか．

===句読点（。、）と全角のコンマやピリオド（．，）を混ぜて使わないこと===
  # 全角ピリオドあるいはカンマを含む行数: 5
  # 句読点を含む行数: 2

  ===句読点が使われている行===
3: 2章では関連研究について述べ、３章で提案手法について述べる。
9: 完璧なチェックは出来ないけど，少しは役には立つと思います。
```

## 注意
* \input は認識しません
* 必要な指摘をしないことがあります
* 不要な指摘をすることがあります

## License
GPLv3

- - -
Copyright (C) Kota Abe
