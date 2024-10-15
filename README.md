# TurtleBot3 Happy Mini 
## 概　要
次のturtlebot3リポジトリをコピーしてhappy miniのモデル(URDF, Mesh)を追加した。ロボット台車のパラメータはwaffle_piと同じである。  
- [ROBOTIS-GIT turtlebot3](https://github.com/ROBOTIS-GIT/turtlebot3.git)

## 環　境  
- ROS2 Humble

## インストール  
- GazeboをROSで使うためのパッケージのインストール
```
$ source ~/.bashrc
$ sudo apt install ros-humble-gazebo-*
$ sudo apt install ros-humble-gazebo-ros-pkgs
```
- Happy Mini関連パッケージのインストール
```
$ cd ~/airobot_ws/src
$ git clone https://github.com/AI-Robot-Book-Humble/turtlebot3_happy_mini
$ cd ~/colcon_ws
$ colcon build 
```


## 実行
1. Empty World  
![happy mini empty world](https://github.com/demulab/happy_mini_turtlebot3_sim/blob/main/happy_mini_empty_world.png "happy mini empty world")

```
$ export TURTLEBOT3_MODEL=happy_mini
$ ros2 launch turtlebot3_gazebo empty_world.launch.py
```

2. TurtleBot3 World  
![happy mini turtlebot3 world](https://github.com/demulab/happy_mini_turtlebot3_sim/blob/main/happy_mini_turtlebot3_world.png "happy mini turtlebot3 world")
```
$ export TURTLEBOT3_MODEL=happy_mini
$ ros2 launch turtlebot3_gazebo turtlebot3_world.launch.py
```

3. TurtleBot3 House
![happy mini turtlebot3 house](https://github.com/demulab/happy_mini_turtlebot3_sim/blob/main/happy_mini_house.png "happy mini turtlebot3 house")
```
$ export TURTLEBOT3_MODEL=happy_mini
$ ros2 launch turtlebot3_gazebo turtlebot3_house.launch.py
```
4. ロボットモデルの変更
- Waffle Piを使う場合
```
$ export TURTLEBOT3_MODEL=waffle_pi
```

5. ロボット初期位置の変更方法
```
$ ros2 launch turtlebot3_gazebo turtlebot3_house.launch.py　x_pose:=初期位置のx座標 y_pose:=初期位置のy座標
```

6. ロボット初期姿勢の変更方法  
turtlebot3_house.launch.pyで初期向きを設定できるように改良したturtlebot3_house2.launch.pyを使ってください．  

```
$ ros2 launch turtlebot3_gazebo turtlebot3_house2.launch.py　x_pose:=初期位置のx座標 y_pose:=初期位置のy座標 yaw_pose:=初期向きのYaw角
```

## 履歴
- 2024-10-13: 初期版

## ライセンス
Apache License 2.0 license found in the LICENSE file in the root directory of this project.


## 参考文献
- 今のところありません
