# ls-leafs
階層構造の末端のディレクトリ名の一覧を抽出するLinux用スクリプト。

Linux上でのファイル整頓で使用する際に作ったもの。
ディレクトリの階層構造の末端（その下にディレクトリが存在しないディレクトリ）のパスを列挙する。

- target-dir/
  - l1-dir1/
    - l2-dir1/
      - file1
      - file2
  - l1-dir2/
    - l2-dir2/
      - l3-dir1/
        - file1
      - l3-dir2/
        - l4-dir1/
          - file1



```
target-dir/l1-dir1/l2-dir1/
target-dir/l1-dir2/l2-dir2/l3-dir1/
target-dir/l1-dir2/l2-dir2/l3-dir2/l4-dir1/
```

# 使い方
1. spriptの中にあるls-leafsを/usr/local/bin/等PATHの通っている場所にコピーする（または、任意の場所に置いてPATHを追加する）。
2. ls-leafs {target directory} を実行すると、target directoryで指定したフォルダの配下にある末端のディレクトリパスが出力される。

あとは下記のようにパイプでmv等に渡せば、末端のディレクトリだけを直下に集めるといったことができる。

```
ls-leafs from_dir | xargs -I{} mv {} to_dir/
```
