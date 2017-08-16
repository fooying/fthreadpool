# fthreadpool
线程池模块，增加超时监控，自动Kill
by Fooying 2017/06/16


* 基于http://chrisarndt.de/projects/threadpool/线程池模块修改

#### 修改功能：
1. 多线程增加可kill方法
2. 增加线程池任务超时监控

#### 缺陷：
1. 多线程kill方法采用threading.settrace来实现，会降低threading整体执行效率
2. 任务超时监控本质采用重载的线程控制，无法监控到被监控线程中的使用了线程/子进程等复杂情况


针对以上两点缺陷，增加了开关控制，允许不使用新增特性和方法，避免以上缺陷
如果task_timeout设置为0，不开启任务超时监控，则不影响整体执行效率
