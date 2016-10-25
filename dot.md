<font face="微软雅黑">
## Lab2: DOL实例分析&编程
### 1. dot截图  

 - example2.dot:  
 
 ![](https://github.com/yxr123456/Resource/blob/master/lab2example2dot.png)  
  
 - example1.dot:  
 
 ![](https://github.com/yxr123456/Resource/blob/master/lab2example1dot.png)  

### 2. 修改思路    
  
   - 任务一：修改example2，让3个square模块变成2个  

&emsp;&emsp;理解example2.xml中的代码可以知道，原来的代码是通过iterator将三个square模块连接起来，再将生产者进程模块连接在第一个square模块的头部，将消费者进程模块连接在最后一个square模块的尾部，从而实现将生产者进程的输入进行8次方计算然后作为消费者进程的输出。  
&emsp;&emsp;所以，要实现实验的要求，将iterater的次数设置为2，即通过iterater将两个square模块连接起来即可。  

   - 任务二：修改example1，使其输出3次方数  
 
&emsp;&emsp;理解square.c中的代码可以知道，该程序中的square_fire函数是先从输入端读入生产者进程产生的值，然后通过i=i * i进行平方，然后再将结果写到输出端，这样就实现了平方运算。   
&emsp;&emsp;所以要实现3次方，只需将i = i * i 改为i = i * i * i 即可，这样就实现了三次方运算。    

### 3. 实验感想  

&emsp;&emsp;这次的实验相对来说比较简单，但是涉及了一些之前没遇到过的新东西。比如功能模块的连接组合，通过c程序实现模块的功能，然后在xml文件创建中进程模块、通道和连接，利用connection（即连接）将各个模块连接起来，从而实现将这些功能模块逻辑地连接在一起，实现一个系统，该系统对输入进行处理，然后得到输出。个人感觉这个实现过程是比较有趣、有意思的。  
&emsp;&emsp;另外，在这次实验中，也体会到了程序的并发运行。生产者进程和消费者进程并发运行，生产者进程产生数值作为输入，经过系统的处理后由消费者进程打印输出。  
&emsp;&emsp;总之，这次实验简单又有趣，期待接下来能学到更多有趣的东西！
</font>

