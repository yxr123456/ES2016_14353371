# DOL开发环境配置
### 1. Description
　　DOL是一个进行并行程序编程的软件开发框架。初次接触DOL,对DOL的了解还不够深，接下来一定会越来越了解。
### 2. How to install  
  * DOL安装笔记:  
	* 安装Ant,jdk,unzip等工具，配置一些必要的环境。 需要在终端输入   
    `$ sudo apt-get install ant`    
    `$ sudo apt-get install`  
    `$ openjdk-7-jdk`  
	`$ sudo apt-get install unzip`
	* 下载systemc和DOL。需要在终端输入  
	`$ sudo wget http://www.accellera.org/images/downloads/standards/systemc/systemc-2.3.1.tgz`  
	`$ sudo wget http://www.tik.ee.ethz.ch/~shapes/downloads/dol_ethz.zip`  
	* 新建dol文件夹，将dolethz.zip解压到dol文件夹中,直接将systemc解压。需要在终端输入  
	`$ mkdir dol`  
	`$ unzip dol_ethz.zip -d dol`  
	`$ tar -zxvf systemc-2.3.1.tgz`  
	* 编译systemc。需要在终端输入  
	`$ cd systemc-2.3.1`    
	`$ mkdir objdir`    
	`$ cd objdir`    
	`$ ../configure CXX=g++ --disable-async-updates`    
	`$ sudo make install`  
	`$ pwd`  
**(PS:输入pwd后记得要将结果记录下来)**
	* 打开dol文件夹中的build_zip.xml,将`<property name="systemc.inc" value="YYY/include"/><property name="systemc.lib" value="YYY/lib-linux/libsystemc.a"/>`中的YYY替代为上一步中pwd得到的结果。  
**(PS:对于64位系统的机器，lib-linux要改成lib-linux64)**
	* 编译DOL,然后进入bulid/bin/main,运行第一个例子。需要在终端输入  
	`$ ant -f build_zip.xml all`    
	`$ cd build/bin/main`  
	`$ ant -f runexample.xml -Dnumber=1`  

### 3. Experimental experience

　　这次实验就是完成DOL开发环境的配置，过程还是比较简单的，只要跟着PPT一步一步做就可以了。在配置的过程遇到了两个问题，第一个是配置g++编译器的时候出现问题，仔细看错误后知道是由于没安装g++，所以在终端输入sudo apt-get install g++安装g++就解决了问题。第二个问题是最后运行第一个例子的时候出现Build Failed，通过阅读TA们给的Q&A文档后知道了必须要将一部分代码注释掉 ，于是照着步骤做就解决了问题。

　　总的来说，这次实验相对简单，通过这次实验，对DOL有了一定的了解，知道了它是一个进行并行程序编程的框架。相信随着课程的学习，对DOL会有更深的了解。