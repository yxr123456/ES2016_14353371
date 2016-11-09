# Lab5 ROS的安装与配置  
  
## 1.安装过程  
  
在这次安装过程中，由于我的Ubuntu是14.04版本，所以我选择安装的是ROS jade。以下介绍安装的全过程，祝好运！

- ### Configure your Ubuntu repositories    
安装ROS前需要配置Ubuntu的软件源，需要配置Ubuntu要求允许接收restricted、universe和multiverse的软件源。  
配置的过程如下:    

   - 打开Ubuntu软件中心  
   - 选择Edit菜单  
   - 选择软件源  
   - 在打开的界面中，勾选restricted、universe、multiverse选项  
   - 点击关闭即可  
   
&emsp;&emsp;配置最后的结果如下图所示：    
 
&emsp;&emsp;![配置Ubuntu软件源](https://github.com/yxr123456/Resource/blob/master/softwareSource.JPG)

- ### Setup your sources.list
这一步做的是添加软件源到sources.list。
执行的终端命令如下：
  
    sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

&emsp;&emsp;执行的部分结果如下图所示：  

&emsp;&emsp;![](https://github.com/yxr123456/Resource/blob/master/SetupSourceList.JPG)  

- ### Set up your keys
这一步做的是设置密钥。执行的终端命令如下：

	sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 0xB01FA116

&emsp;&emsp;执行的部分结果如下图所示： 

&emsp;&emsp;![](https://github.com/yxr123456/Resource/blob/master/SetupKeys.JPG)


- ### Installation
这一步做的是安装ROS。  
首先要做的是确保Debian的软件包索引是最新的。可以通过一下命令来更新到最新版：

	sudo apt-get update

&emsp;&emsp;接着就是安装ROS，建议是完全安装。通过执行以下命令可以进行安装：
  
&emsp;&emsp;sudo apt-get install ros-jade-desktop-full

&emsp;&emsp;安装过程如下图所示：  

&emsp;&emsp;![](https://github.com/yxr123456/Resource/blob/master/Install.JPG)

- ### Initialize rosdep
这一步做的是初始化rosdep。执行以下命令可以进行初始化：  

	sudo rosdep init
	rosdep update

- ### Environment setup
这一步做的是设置环境。添加ROS的环境变量，这样，当你打开你新的shell时，你的bash会话中会自动添加环境变量。通过以下命令进行配置：

	echo "source /opt/ros/indigo/setup.bash" >> ~/.bashrc
	source ~/.bashrc

- ### Getting rosinstall
这一步做的是安装rosinstall。rosinstall命令是一个使用的非常频繁的命令，使用这个命令可以轻松地下载许多ROS软件包。通过以下命令进行安装：

	sudo apt-get install python-rosinstall

&emsp;&emsp;配置环境和安装rosinstall的过程如下图所示：

&emsp;&emsp;![](https://github.com/yxr123456/Resource/blob/master/EnvironmentSetupAndInstall.JPG)
## 2.例子演示

&emsp;&emsp;安装了ROS后，在网上找了一个小例子来玩一玩ROS，既能验证ROS安装成功，同时也体验一下ROS这个软件的乐趣。  

&emsp;&emsp;例子如下图所示：  
  
![](https://github.com/yxr123456/Resource/blob/master/sample.JPG)  
  
&emsp;&emsp;按照图中的命令进行操作，可以控制小乌龟的运动，得到下图：  
    
![](https://github.com/yxr123456/Resource/blob/master/turtle.JPG)
  
&emsp;&emsp;这里附上例子的链接：[例子](http://www.cnblogs.com/cv-pr/p/4829015.html)

## 3.实验感想

&emsp;&emsp;首先想说的是很庆幸这次安装ROS没遇到什么比较奇怪的问题，根据教程一步一步做，最终成功安装了ROS这个很有趣的软件。看到群上其他同学在安装过程中遇到了很多问题，不免觉得自己还是很幸运的！  
&emsp;&emsp;ROS为我们提供了强大的功能，其中文名称为机器人操作系统，通过ROS，我们可以做许多有趣的事情，比如我们可以用它模拟一个机器人的运动等等。当然还有许多有趣的事情可以做，相信接下来会有机会接触到！  
&emsp;&emsp;通过这次实验，我已经成功安装了ROS这个很有趣的软件，虽然现在对它还不是很熟悉，但是随着课程的逐渐深入，相信会对ROS更加熟悉，同时也能很好地掌握ROS的使用，用它做出一些有趣实用的东西！


