# 三维点云转二维占据栅格地图
## 运行方法

首先需要在pcd_to_gridmap.cpp中更改三维地图路径。

### 终端一

运行节点，使之接收pcd文件并降采样、转栅格。
```bash
colcon build --packages-select t11_10
source install/setup.bash
ros2 run t11_10 pcd_to_gridmap_node
```
### 终端二

保存地图
```bash
ros2 run nav2_map_server map_saver_cli -f ~/ros2_ws/src/t11_10/maps/occupgrid_map
```
运行成功后，maps文件夹下会自动生成两个文件。

## 完成截图
<img width="2564" height="1804" alt="pcd point" src="https://github.com/user-attachments/assets/e77cbbf5-9e17-4fa4-b42c-57d0727d8a84" />
采用了point_lio算法，空旷处漂移很严重...在运行之前手动裁减掉了一些。
<img width="1714" height="260" alt="点云降采样" src="https://github.com/user-attachments/assets/08f03b86-bb79-4b43-9290-4f0a50607e30" />
结果展示
<img width="2426" height="1586" alt="10_11_2" src="https://github.com/user-attachments/assets/3a432cc6-21f1-4565-bbe9-6358351caf07" />

