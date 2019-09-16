# Hello Norikra
Norikra を動かしてみるサンプルです。

# 動かし方
**順序依存性があります。**

* Norikra のサーバーを動かす前に fluentd を稼働させると、多くのエラーを出力し非常に頻繁なリトライを行います。
* データを入力する前にクエリを入力してしまうと、エラーになるかもしれません。
* 以下が問題なく動かせると思われる手順です。

```
cd norikra
make start-server
cd ../fluentd
make fluentd
make log
# ここで、Norikra にターゲットが現れます。
cd ../norikra
make submit-query
```

一度データを Norikra に流したあとであれば、Web UI や CUI からクエリを
自由に登録できます。
