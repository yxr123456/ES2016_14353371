<font face="微软雅黑">
## Lab4：死锁  
### 1. 程序死锁截图  
      
&emsp;&emsp;![](https://github.com/yxr123456/Resource/blob/master/deadlock.PNG)  
&emsp;&emsp;如图所示，在第3970次执行时，产生了死锁。  
  
### 2. 死锁产生的条件 
 
- 互斥：存在这样一个资源，该资源在某个时刻只能被唯一一个线程占有。
- 持有：当请求的资源已被占用从而导致线程阻塞时，资源占有者无需释放该资源，而且还可以继续请求更多资源。	
- 不可剥夺：线程占有的互斥资源不可被强行剥夺，只能由该线程主动释放。
- 循环等待：若干线程以不同次序获取互斥资源，从而形成循环等待的局面，每个线程都在等待占有互斥资源的其他线程释放资源。  
  
### 3. 程序产生死锁的解释  
    
	Deadlock()   
	{  
		Thread thread = new Thread(this);  
		thread.start();  
		int count = 20000;  
		while(count-- > 0);  
		a.methodA(b);  
	}  
	@Override  
	public void run()   
	{  
		b.methodB(a);  
	}  

&emsp;&emsp;如以上关键代码所示，在主线程执行Deadlock的构造函数时，创建了一个新的子线程，该子线程调用start方法后开始和主线程并发执行。该子线程会执行run方法。  
&emsp;&emsp;第一个假设是子线程先执行了b.methodB(a)方法，那么此时<font color="red">子线程占有b对象的锁</font>。在子线程执行a.last()方法之前，主线程执行a.methodA(b)方法，此时<font color="red">主线程占有a对象的锁</font>。那么**此时子线程执行不了a.last()方法，因为a对象的锁被主线程占有；而主线程也执行不了b.last()方法，因为b对象的锁被子线程占有。**所以导致的结果是主线程在等待子线程释放对象b的锁，而子线程在等待主线程释放对象a的锁，因此这就出现了死锁。  
&emsp;&emsp;另外一个假设是主线程先执行了a.methodA(b)方法，那么此时<font color="red">主线程占有a对象的锁</font>。在主线程执行b.last()方法之前，子线程执行b.methodB(a)方法，此时<font color="red">子线程占有b对象的锁</font>。那么**此时主线程执行不了b.last()方法，因为b对象的锁被子线程占有；而子线程也执行不了a.last()方法，因为a对象的锁被主线程占有。**所以导致的结果是主线程在等待子线程释放对象b的锁，而子线程在等待主线程释放对象a的锁，因此这就出现了死锁。
</font>