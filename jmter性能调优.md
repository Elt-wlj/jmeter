#### CPU的瓶颈分析
- 1、cpu是否正常工作（ top 看负载，vmstat 看cpu利用率）
  - 输入top 在输入1查看cpu内核数
  - 
- 2、cpu在做什么
  - vmstat命令 看 in 和 cs 是否过高，如果过高，说明中断和上下文切换频繁。（in：每秒产生的中断次数 ，cs：每秒产生的上下文切换次数 ）
  - vmstat 看 usr 和 sys 百分比。（us：用户进程消耗的CPU时间百分比，sy：内核进程消耗的CPU时间百分比）
    - ）如果 sy 百分比过高，说明内核消耗的CPU资源多；【注：us+sy 的利用率在 50 到 80 之间都算正常】
    - 如果 us 百分比过高，说明用户进程消耗的CPU时间多，但是如果长期超50%的使用，那么我们就该考虑优化程序算法。

  - vmstat 看运行队列。
    -  1）运行队列 r 值远超 cpu 数，说明 cpu 负载过高，系统现在运行比较慢,有多数的进程等待CPU；
    -  2）b 值过高，说明大量进程处于 IO 等待，IO 可能存在瓶颈。

- 3、cpu未正常工作
 -  pidstat -p【pid】-w 1 10 查看进程的主动和被动切换。
  -  1）如果主动切换（cswch/s）过高，说明可能 IO，内存资源可能不足
  -  2）如果被动切换（nvcswch/s）过高，说明进程过多，cpu 时间片不足
  -  
