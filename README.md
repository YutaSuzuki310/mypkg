# mypkg
* ロボットシステム学の課題2
* ROS2を利用して通信を行うためのリポジトリ

[![test](https://github.com/yutasuzuki310/mypkg/actions/workflows/test.yml/badge.svg)](https://github.com/yutasuzuki310/mypkg/actions/workflows/test.yml)

# Usage

* talker.py : 実行すると変数nが1ずつ増え、その都度トピック'countup'に実行結果がメッセージとして送られます。
* listener.py : 'countup'からメッセージを受信してターミナルに表示します。
* talk_listen.launch.py : 
* トピック'countup' :  talkerからのメッセージを格納しlistenerによって送り出されます。



* talker listener の使い方

２つのターミナルを使います。

```bash
端末1 $ ros2 run mypkg talker
端末2 $ ros2 run mypkg listener
```
と入力するとlistener側に以下の実行結果が出力されます。

```
[INFO] [1703995797.728886212] [listener]: Listen: 0
[INFO] [1703995798.223467319] [listener]: Listen: 1
[INFO] [1703995798.722672162] [listener]: Listen: 2
[INFO] [1703995799.223145271] [listener]: Listen: 3
[INFO] [1703995799.722684813] [listener]: Listen: 4
[INFO] [1703995800.224348441] [listener]: Listen: 5
[INFO] [1703995800.722441820] [listener]: Listen: 6
[INFO] [1703995801.224298555] [listener]: Listen: 7
```

無限ループなので止めたいときは `[ctrl] + C`で停止します。


* launch の使い方

1つの端末を利用します。launchファイルでtalkerとlistenerの両方を同時に立ち上げることができます。

```
$ ros2 launch mypkg talk_listen.launch.py
```

と入力すると以下のような実行結果が出力されます。

```
[listener-2] [INFO] [1703996107.150247877] [listener]: Listen: 0
[listener-2] [INFO] [1703996107.637744533] [listener]: Listen: 1
[listener-2] [INFO] [1703996108.137678070] [listener]: Listen: 2
[listener-2] [INFO] [1703996108.637292037] [listener]: Listen: 3
[listener-2] [INFO] [1703996109.137983946] [listener]: Listen: 4
[listener-2] [INFO] [1703996109.637790271] [listener]: Listen: 5
[listener-2] [INFO] [1703996110.137806737] [listener]: Listen: 6
[listener-2] [INFO] [1703996110.632019943] [listener]: Listen: 7
```

停止手順は同様です。


# Requirement
* Python
* ROS2(Foxy Fitzroy)

# Installation
* git clone https://github.com/YutaSuzuki310/mypkg.git

# Test environment
* Ubuntu 20.04

# Author
* Yuta Suzuki
* s22c1071za@s.chibakoudai.jp

# License
* このソフトウェアパッケージは，3条項BSDライセンスの下，再頒布および使用が許可されます．
* このパッケージのコードは，下記のリポジトリ（CC-BY-SA 4.0 by Ryuichi Ueda）のものを，本人の許可を得て自身の著作としたものです．
  - https://github.com/ryuichiueda/mypkg.git
* © 2023 Yuta Suzuki
