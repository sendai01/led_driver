# led_driver
RaspbianがのったRaspberry Pi 3BでLEDを光らせることができるデバイスドライバです。

2つのLEDの点滅で0から3の数字を2進数に表現します。

# 回路
一桁目を表現するLEDをGPIO24、二桁目をGPIO25にそれぞれ+を接続し、-をGNDに接続します。

# 使い方
リポジトリをクローンし、そのディレクトリでmakeします。
```
make
```
モジュールをインストールします。
```
sudo insmod myled.ko
```
出来上がった/dev/myled0のパーミッションを変更します。
```
sudo chmod 666 /dev/myled0
```
/dev/myled0に0から3のどれかを書き込みます。
```
echo 0 > /dev/myled0
```

