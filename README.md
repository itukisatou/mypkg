# mypkg
* このリポジトリはROS 2のパッケージであり、talkerというパブリッシャを持つノードが0.5秒間隔で１づつカウントアップしたメッセージをトピック/countupを通じて送信し、listenerというサブスクライバを持つノードがcountupトピックからメッセージを受信して、ターミナル上に表示します。

[![test](https://github.com/itukisatou/mypkg/actions/workflows/test.yml/badge.svg)](https://github.com/itukisatou/mypkg/actions/workflows/test.yml)

# ノード解説
## talker
* このノードはパブリッシャを持つノードです。0.5秒間隔で0から1づつカウントアップし、countupトピックを通じてデータを送信します。また、送信するメッセージの型は16ビット符号付き整数です。

## listener
* このノードはサブスクライバを持つノードです。countupトピックからメッセージを受信してターミナル上に表示します。

# 実行例
## talkerの起動
* 次のようにして実行します。また、実行するとターミナル上には何も表示されませんが、メッセージの送信は行われています。
```
$ros2 run mypkg talker

```

## listenerの起動
* 次のように実行します。talkerが起動していない状態で実行するとターミナル上には何も表示されません。
```
$ros2 run mypkg listener
```

* talkerが起動していた場合の実行結果は以下の通りです。
```
$ros2 run mypkg listener
[INFO] [1703955171.021575495] [listener]: Listen: 0
[INFO] [1703955171.520357381] [listener]: Listen: 1
[INFO] [1703955172.020900309] [listener]: Listen: 2
[INFO] [1703955172.521169394] [listener]: Listen: 3
[INFO] [1703955173.021307701] [listener]: Listen: 4
[INFO] [1703955173.520894892] [listener]: Listen: 5
```

## talkerとlistenerの同時起動
* ローンチファイルを利用して同時にかつ同一ターミナル上に表示することができます。
```
$ros2 launch mypkg talk_listen.launch.py
[INFO] [launch]: All log files can be found below /home/ituki/.ros/log/2023-12-31-01-57-13-962511-サバの水槽-20194
[INFO] [launch]: Default logging verbosity is set to INFO
[INFO] [talker-1]: process started with pid [20196]
[INFO] [listener-2]: process started with pid [20198]
[listener-2] [INFO] [1703955434.730006564] [listener]: Listen: 0
[listener-2] [INFO] [1703955435.222838592] [listener]: Listen: 1
[listener-2] [INFO] [1703955435.722894212] [listener]: Listen: 2
[listener-2] [INFO] [1703955436.222858727] [listener]: Listen: 3
[listener-2] [INFO] [1703955436.723486123] [listener]: Listen: 4
[listener-2] [INFO] [1703955437.223217766] [listener]: Listen: 5
```

# インストール方法
* ROS 2をインストールしていない場合は、インストールしてください。
* ROS 2のインストールがお済みの場合はこのリポジトリを自身のROS 2のワークスペースにクローンしてください。
```
$git clone git@github.com:itukisatou/mypkg.git
```

# 必要なソフトウェア
* Python
* ROS 2

# テスト環境
* Ubuntu 20.04
* ROS 2 foxy

# ライセンス関連
* このソフトウェアパッケージは、３条項BSDライセンスの下、再頒布および使用が許可されます.
* このパッケージは、Ryuichi Ueda由来のコード(© 2023 Ryuichi Ueda)を利用しています.
* このパッケージのコードは、下記のスライド(CC-BY-SA 4.0 by Ryuichi Ueda)のものを、本人の許可を得て自身の著作としたものです.
    * [ryuichiueda/my_slides robosys_2022/lesson8.html#/22](https://ryuichiueda.github.io/my_slides/robosys_2022/lesson8.html#/22)
    * [ryuichiueda/my_slides robosys_2022/lesson9.html#/4](https://ryuichiueda.github.io/my_slides/robosys_2022/lesson9.html#/4)
    * [ryuichiueda/my_slides robosys_2022/lesson10.html#/4](https://ryuichiueda.github.io/my_slides/robosys_2022/lesson10.html#/4)
    * [ryuichiueda/my_slides robosys_2022/lesson11.html#/6](https://ryuichiueda.github.io/my_slides/robosys_2022/lesson11.html#/6)
* © 2023 Ituki Satou
