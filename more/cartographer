# ROS中安装cartographer


##1. 安装cartographer
###(1)安装所有依赖项  

    sudo apt-get install -y google-mock libboost-all-dev  libeigen3-dev libgflags-dev libgoogle-glog-dev liblua5.2-dev libprotobuf-dev  libsuitesparse-dev libwebp-dev ninja-build protobuf-compiler python-sphinx  ros-indigo-tf2-eigen libatlas-base-dev libsuitesparse-dev liblapack-dev 

###(2)安装ceres solver 

	git clone https://github.com/hitcm/ceres-solver-1.11.0.git
	cd ceres-solver-1.11.0
	mkdir build
	cd build
	cmake ..
	make –j
	sudo make install

执行cmake指令的过程截图如下：  
  
![](https://github.com/yxr123456/Resource/raw/master/cmake.JPG)  

执行make指令的过程过程截图如下： 
 
![](https://github.com/yxr123456/Resource/raw/master/make.JPG)  

执行install指令的过程截图如下：  
  
![](https://github.com/yxr123456/Resource/raw/master/install.JPG)


###(3)安装cartographer

	git clone https://github.com/hitcm/cartographer.git
	cd cartographer
	mkdir build
	cd build
	cmake .. -G Ninja
	ninja
	ninja test
	sudo ninja install

执行cmake指令的过程截图如下：  
  
![](https://github.com/yxr123456/Resource/raw/master/cmakeNinja.JPG)

执行ninja指令的过程截图如下：  
  
![](https://github.com/yxr123456/Resource/raw/master/ninja.JPG)

执行ninja test指令的过程截图如下：  

![](https://github.com/yxr123456/Resource/raw/master/ninjaTest.JPG)

执行install指令的过程截图如下：  

![](https://github.com/yxr123456/Resource/raw/master/installNinja.JPG)


###(4)安装cartographer_ros

将cartographer_ros安装在catkin_ws的src文件夹中，并在catkin_ws文件夹下执行catkin_make命令：  
raw
	mkdir catkin_ws
	cd catkin_ws
	mkdir src
	cd src
	git clone https://github.com/hitcm/cartographer_ros.git
	cd ..
	catkin_make

执行clone指令的过程截图如下：  

![](https://github.com/yxr123456/Resource/raw/master/installCartographer_ros.JPG)

执行catkin_make指令的过程截图如下：  

![](https://github.com/yxr123456/Resource/raw/master/catkin_make.JPG)

###(5)数据下载测试

这里需要下载两个数据，2d数据和3d数据，下载链接依次为：
[2d数据](https://storage.googleapis.com/cartographer-public-data/bags/backpack_2d/cartographer_paper_deutsches_museum.bag)
[3d数据](https://storage.googleapis.com/cartographer-public-data/bags/backpack_3d/cartographer_3d_deutsches_museum.bag)  
(这里由于是在虚拟机中运行，无法存储大文件，所以只下载了2d的数据)

接着运行launch文件：
	
	roslaunch cartographer_ros demo_backpack_2d.launch bag_filename:=${HOME}/Downloads/cartographer_paper_deutsches_museum.bag
	roslaunch cartographer_ros demo_backpack_3d.launch bag_filename:=${HOME}/Downloads/cartographer_3d_deutsches_museum.bag

第一个命令跑的是2d数据，第二个命令跑的是3d数据。

运行结果如下图所示：  

![](https://github.com/yxr123456/Resource/raw/master/2d.JPG)

##2.实验感想
&emsp;&emsp;实验过程中遇到的问题是比较多的，安装的过程相对来说比较艰辛。一开始按照官网教程进行安装，但是无法安装成功，最后不得不按照网上的博客给出的教程进行安装，虽然中间还是遇到了一些问题，但还是安装成功了。  
&emsp;&emsp;实验中遇到的问题有很多，比如：在安装cartographer\_ros时提示cartographer\_ros目录已经存在，这是因为一开始是按照官网的教程安装的，所以在catkin\_ws的src文件夹已经有了该目录，因此将该目录删了然后重新安装cartographer\_ros便解决了上述问题。其他的问题如：在执行cmake .. 时遇到程序在执行过程中卡住的情况，最后才发现其实这种情况是安装过程中的正常情况，只要稍微等一下就可以成功执行命令了。  
&emsp;&emsp;这次安装虽然遇到了比较多的问题，但是最后能够绘出图还是令人喜悦的！ROS的功能真的强大，而且这个软件看起来也很有趣，期待在接下来的课程中能对它有更深的了解，能学到更多实用有趣的东西！
 
