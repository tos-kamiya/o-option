o-option
========

任意のコマンドに-oオプション（ファイルに保存する）を付けます。

## 何でこんなものを？

コマンドを起動するコマンドとリダイレクトが微妙に干渉してこまったことはありませんか？

例えば、次のコマンドラインは、

```sh
ls *.txt | xargs -I {} head -n 3 {} > {}-head.out
```

実行すると、`*.txt`ファイルのそれぞれに`*-head.out`ファイルを生成しません。
すべての`head`コマンドの実行の結果を含む一つの`{}-head.out`を生成します。

このような場合に`o-o`を使ってください。

次のように実行できます。

```sh
ls *.txt | xargs -I {} o-o -o {}-head.out head -3 {}
```

## 使い方

```
コマンドラインを実行して出力をファイルに保存する。

利用法:
  o-o [オプション] [--eo|-e ERRFILE] コマンドライン...

オプション:
  -o OUTFILE   標準出力を書き出すファイル。
  -e ERRFILE   標準エラーを書き出すファイル。
  --eo         標準エラーを標準出力にリダイレクトする。
  -i INFILE    標準入力として読み込むファイル。  
  --dry-run    等価なコマンドラインをPOSIXシェルの構文で表示する。

例:
  o-o -o result.txt ls
```

## インストール

インストールするには、ファイル`o-o`をPATHが通ったディレクトリ（例えば`~/bin`）に置いてください。

アンインストールするには、ファイル`o-o`を削除してください。

## ライセンス

Unlicense (Public Domain).

