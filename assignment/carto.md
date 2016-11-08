# 实验报告
**14353104**   **黄新元**

**2016/11/1**

##内容描述
* ROS（Robot operation system）是一套框架，底层提供硬件驱动，软件层支持通用文件格式。 ROS本质上属于分布式计算系统，核心是节点。多个节点之间互相传递信息，并可以独立控制启动或终止。实验中主要利用了ROS仿真激光雷达扫描的功能。

* Cartographer是谷歌开源的一个SLAM算法，基于激光雷达以及IMU（惯性处理单元）。该技术利用同步定位与制图技术（SLAM）绘制室内建筑平面图，能同时用于二维与三维空间的移动映射。

##安装笔记
整个安装过程分为两部分：ROS和Cartographer。

###一、ROS
这部分参考了 http://wiki.ros.org/jade/Installation/Ubuntu 的教程。
关键部分的命令如下：

* Desktop-Full Install：
> sudo apt-get install ros-jade-desktop-full

* Environment setup：
> echo "source /opt/ros/jade/setup.bash" >> ~/.bashrc
> source ~/.bashrc

###二、Cartographer
这部分参考了 http://www.cnblogs.com/hitcm/p/5939507.html 的教程。
关键部分的命令如下：

* 安装Cartographer：
> git clone https://github.com/hitcm/cartographer.git
> cd cartographer/build
> cmake .. -G Ninja
> ninja
> ninja test
> sudo ninja install

* catkin_ws配置：
> source ~/catkin_ws/devel/setup.bash
> rospack profile

###三、效果截图
* ros：
  ![ros](https://github.com/portal20/ES2016_14353104/blob/master/Pictures/rosinstall.png)

* 2d：
  ![2d](https://github.com/portal20/ES2016_14353104/blob/master/Pictures/2d.png)

* 3d：
  ![3d](https://github.com/portal20/ES2016_14353104/blob/master/Pictures/3d.png)

##实验感想

这次实验内容比较高级，最后模拟2d和3d扫描建图的效果非常科幻。还是非常感谢谷歌能够提供这样一个开源的框架，让一般人能够有机会接触到这么多新奇的东西。整个框架的安装按照教程的步骤也比较顺利，容易出现的问题是最后catkin_ws需要重新配置，否则不能成功运行。
