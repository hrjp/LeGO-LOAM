[![Melodic build](https://github.com/hrjp/LeGO-LOAM/actions/workflows/melodic_build_test.yml/badge.svg)](https://github.com/hrjp/LeGO-LOAM/actions/workflows/melodic_build_test.yml)
[![Noetic build](https://github.com/hrjp/LeGO-LOAM/actions/workflows/noetic_build_test.yml/badge.svg)](https://github.com/hrjp/LeGO-LOAM/actions/workflows/noetic_build_test.yml)
# KCCT LeGO-LOAM
LiDARのみのデータから3次元点群地図を作るパッケージ

# Setup
```bash
cd catkin_ws/src
git clone https://github.com/hrjp/LeGO-LOAM.git
sudo apt update
rosdep install -i -y --from-paths .
cd ..
catkin build
source devel/setup.bash
```

# Run
```bash
roslaunch lego_loam rosbag_play.launch
```
実行後roslaunchを終了するとLeGO-LOAM/LeGO-LOAM/pcdに点群地図が保存される

---
rosbag_play.launch内で以下のパラメータを適宜書き換える
```xml
<!-- 地図作成に使用するrosbagのファイルパスを指定 -->
<arg name="bag_file" default="/home/share/rosbag/nakanoshima211023_mapping.bag" />
<!-- rosbagの再生速度 -->
<arg name="playback_speed" default="5.0" />
<!-- 入力する点群のトピック名 -->
<arg name="pointcloud_topic" default="/velodyne_points" />
```