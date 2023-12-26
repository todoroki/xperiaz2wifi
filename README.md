# はじめに
Xperia z2 tabletを中古で買ったが、Android 5 までしか対応していなかったために、カスタムロムをいれた。
色々会って手こずったが、インストールする方法までを防備録として記す。

# 必要なもの

最低限、必要なソフトウェアは以下の２つとなる。

・TWRP
本Git hubにあげているtwrp_3.2.1-castor_windy.imgを利用した。
(md5sum: f99c6a3c0307326ea4308344af5b0d65 )

・AndroidのOSのイメージ( CARBON-ROM )
https://get.carbonrom.org/device-castor_windy.html
今回はCARBON-CR-6.1-NOCT-RELEASE-castor_windy-20200524-2252.zipを利用した。

Android OSは少し古くて8.1となる。

## インストール方法

$ sudo fastboot flash:raw boot twrp_3.2.1-castor_windy.img
$ sudo fastboot reboot
電源ボタンと音量＋ボタンを押すとtwrp に入ることが出来る。

### ハマりポイント
インストール時に使っていたOSはubuntu 18.04だが、そのOSで、sudo fastboot flash boot twrp_3.2.1-castor_windy.imgとrawを付け忘れてはいけない。
sudo fastboot flash boot としているサイトがあって、ubuntuのバージョンによるのかわからないが、FAILED (remote: dtb not found) fastbootというエラーが出たり、bootを当てられるのに起動しなかったり、原因が不明すぎて大変だった。


# その他ハマった所や注意事項
## LineageOS
調べていくと解るが、現時点でLineageOS というものが出ていて、v18ではAndroid11相当でsony xperai z2 tabletに対応しているというのが海外のブログで散見する。いろいろ試したが、なんともならなかった。理由としては、全くブートしないなどの問題が発生する。
## twrp
本gitにあげたバージョンじゃないとtwrpが起動しない。これ以外のバージョンを試したが、Sony xperiaのロゴは全く出てこなかった。文鎮化したと思って焦った。
## xperia のバージョン
Xperiaのコードネームは、z, z2, z2 wifi, z2 LGE, z3 ... などで名前が別れており、たしか xperia z はyugaだったと思うが、もちろん機種ごとに色々と癖が異なるようだ。z2 wifiは、castor_windyといわれる。それをしらずに、yugaのカスタムロムで頑張ったりしていてよくわからない自称にぶち当たった。
