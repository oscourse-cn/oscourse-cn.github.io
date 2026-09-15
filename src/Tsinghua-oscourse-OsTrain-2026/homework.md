# 2026秋季学期操作系统课后练习
## 往年参考

+ [2025秋季学期操作系统课后练习](https://www.yuque.com/xyong-9fuoz/qczol5/href7zqnszuogr2s)
+ [2024秋季学期操作系统课后练习](https://www.yuque.com/xyong-9fuoz/qczol5/qcvlrq625vqfu4gt)
+ [2023秋季学期操作系统课后练习](https://www.yuque.com/xyong-9fuoz/qczol5/uzf18vbnscar3hzi)

<!--
### 第12次课后练习（第十一周周一）
#### 第1题
课堂教学中给出生产者-消费者问题的实现伪码，并且通过枚举方式分析了实现的正确性。请在Windows、Linux或MacOS上，利用操作系统提供的信号量支持，用C或Rust语言给出生产者-消费者问题的完整实现；然后写完整的测试用例验证自己的实现是正确的。同学们可以依据自己的兴趣和时间情况，选择以下两种方式中的一种来完成这个作业。

+ 看明白梁锡豪学长的实现，在你选择的环境中进行复现和完善，并分析其测试方法是否枚举完全。
+ 在你选择的环境中独立完成生产者-消费者问题的实现和测例。

##### 已有参考
+ 梁锡豪：[生产者一消费者问题的实现和正确性测试用例](https://piazza.com/class/i5j09fnsl7k5x0/post/391)（[piazza访问帮助](https://www.yuque.com/xyong-9fuoz/qczol5/gwv6926mfr9nnhc5#pbG6V)）

### 第11次课后练习（第十周周一）
#### 第1题
下面链接给出了几个用C和Rust等语言实现的用户态线程库。

+ [Multi-Threaded Programming With POSIX Threads](http://www.csc.villanova.edu/~mdamian/threads/posixthreads.html)
+ [两百行Rust代码解析绿色线程原理](https://zhuanlan.zhihu.com/p/100058478)
+ GitHub - niklabh/[RustGreenThreads: Implementation of lightweight green thread in rust](https://github.com/niklabh/RustGreenThreads)
+ [github中用户态线程代码仓库列表](https://github.com/topics/green-threads)

依据自己的兴趣和时间情况，选择完成如下部分或全部任务。

1. 请选择一种你有兴趣的语言，在Windows、Linux或MacOS上写其中一个线程库的测例，对比分析在不同并发进程或线程数量情况下，进程切换和线程切换的延时和延时抖动，内存开销。
2. 基于你对用户态线程工作原理的理解，对你选择的线程库实现代码进行分析，重点分析其线程控制块数据结构、线程状态转换流程、线程切换过程等。

#### 第2题
下面链接给出了几个用C++、Rust、Python、Kotlin等语言提供的无栈协程支持和示例。

+ [A stack-less Rust coroutine library under 100 LoC](https://blog.aloni.org/posts/a-stack-less-rust-coroutine-100-loc/)
+ [如何编写 C++ 20 协程(Coroutines)](https://zhuanlan.zhihu.com/p/355100152)
+ [Kotlin Coroutines guide](https://kotlinlang.org/docs/coroutines-guide.html)
+ [Python Coroutines and Tasks](https://docs.python.org/3/library/asyncio-task.html)

依据自己的兴趣和时间情况，选择一种你有兴趣的语言，在Windows、Linux或MacOS上写一个协程通信程序，完成如下功能。

+ 在同一进程内创建一个数组array[m]，每个数组元素为一个4字节无符号整数，m为程序的输入参数，取值为2^10、2^20、2^30和2^40等；
+ 再创建m个协程，构成一个环；在环中相邻协程间循环传递数据一百万圈，统计执行时间。每一次收发数据的过程如下：协程i（i的取值为0到m-1）先从协程i-1接收一个4字节整数，对整数加一后通过array[i]传给下一个协程。初始时，先由协程0发第一个数据。
+ 对比分析进程内不同并发协程数量情况下，协程切换的延时、延时抖动和内存开销特征。

### 第10次课后练习（第九周周四）
#### 第1题
在Windows、macOS、Linux、uCore或rCore操作系统中，用C或Rust语言分别用管道、消息队列、共享内存三种通信机制写进程间通信程序，在父子进程间循环收发数据一百万次，统计执行时间。每一次收发数据的过程如下：先接收一个4字节整数，对整数加一后发还给对方。初始时，先由子进程给父进程发第一个数据。

##### 李相霖的回答
在Linux下C语言编程测试三种IPC方式：管道、消息队列和共享内存，具体代码见：[AuFranklin85/os2024a-hw10](https://gitee.com/AuFranklin85/os2024a-hw10/tree/655681d8828ac57e35a797dbdc4803aa457e4a86/) 

+ 管道的运行时间：12.185559秒。 
+ 消息队列的运行时间：4.213369秒。 
+ 共享内存的运行时间：0.713429秒。

### 实验四（第九周周一）
+ 实验目标 
    - 硬链接
+ 实验任务描述 
    - [rCore](https://learningos.cn/rCore-Tutorial-Guide/chapter6/4exercise.html#id1)
    - [uCore](https://learningos.cn/uCore-Tutorial-Guide/chapter6/5exercise.html#id3)
+ 实验提交要求 
    - 2025年11月19日；

### 第9次课后练习（第八周周四）
#### 第1题
“[vsfs.py](https://github.com/remzi-arpacidusseau/ostep-homework/blob/master/file-implementation/vsfs.py)”是用python脚本实现的一个简单的文件系统模拟器，可以模拟用户在进行文件操作过程中磁盘上文件系统的存储结构和内容的变化情况；“[README.md](https://github.com/remzi-arpacidusseau/ostep-homework/blob/master/file-implementation/README.md#overview)”是该文件系统模拟器的简要介绍。请通过阅读“[README.md](https://github.com/remzi-arpacidusseau/ostep-homework/blob/master/file-implementation/README.md#overview)”，并分析和执行“[vsfs.py](https://github.com/remzi-arpacidusseau/ostep-homework/blob/master/file-implementation/vsfs.py)”，然后依据自己的兴趣和时间情况，选择完成如下部分或全部任务。

1. 描述该文件系统的存储结构；
2. 基于模拟器的执行过程跟踪分析，描述该文件系统中“读取指定文件最后10字节数据”时要访问的磁盘数据和访问顺序；
3. 基于模拟器的执行过程跟踪分析，描述该文件系统中“创建指定路径文件，并写入10字节数据”时要访问的磁盘数据和访问顺序；
4. 请改进该文件系统的存储结构和实现，成为一个支持崩溃一致性的文件系统。

### 实验三（第七周周一）
+ 实验目标 
    - spawn 系统调用
    - stride 调度算法
+ 实验任务描述 
    - [rCore](https://learningos.github.io/rCore-Tutorial-Guide/chapter5/4exercise.html)
    - [uCore](https://learningos.github.io/uCore-Tutorial-Guide/chapter5/4exercise.html)
+ 实验提交要求 
    - 布置实验任务后的第13天（11月9日24点）；

### 第8次课后练习（第六周周一）
#### 第1题
“[wakeuptime.py](https://github.com/iovisor/bcc/blob/master/tools/wakeuptime.py)”是一个eBPF应用，可以动态进程执行过程中的进入等待和等待事件出现等相关信息。“[wakeuptime_example.txt](https://github.com/iovisor/bcc/blob/master/tools/wakeuptime_example.txt)”这是这个小工具的使用说明和示例。请依据自己的兴趣和时间情况，选择完成如下部分或全部任务。

1. 安装eBPF工具链，并确信使用说明中的示例是工作；描述安装过程中遇到的问题和解决方法。
2. 在MacOS或Linux平台上运行课程中的“[循环创建进程示例](http://learningos.cn/os-lectures/lec7/p1-process-overview.html#39)”，用“[wakeuptime.py](https://github.com/iovisor/bcc/blob/master/tools/wakeuptime.py)”跟踪示例运行过程；解释跟踪等待事件对应的示例代码。
3. “[example](https://github.com/zoidbergwill/awesome-ebpf#examples)”目录中有多种基于eBPF的动态跟踪小工具，选一个有兴趣的工具，并跟踪相关的内核事件。

### 实验二（第五周周四）
+ 实验目标
    - 重写获取系统时间和进程控制块信息的内核函数 
    - 实现申请和取消虚存映射的系统调用
+ 实验任务描述
    - [uCore](http://learningos.cn/uCore-Tutorial-Guide/chapter4/7exercise.html#id1)
    - [rCore](http://learningos.cn/rCore-Tutorial-Guide/chapter4/7exercise.html#chapter4)
+ 实验提交要求 
    - 在自己的已创建实验仓库中提交完整的代码和文档；
    - 在荷塘雨课中提交实验一报告链接和commit ID；
    - 实验截止时间：布置实验任务后的第13天（2025年10月28日24点）；

### 第7次课后练习（第五周周一）
#### 第1题
有一台假想的计算机，页大小（page size）为32 Bytes，支持32KB的虚拟地址空间（virtual address space）,有4KB的物理内存空间（physical memory），采用二级页表，一个页目录项（page directory entry ，PDE）大小为1 Byte,一个页表项（page-table entries  
PTEs）大小为1 Byte，1个页目录表大小为32 Bytes，1个页表大小为32 Bytes。页目录基址寄存器（page directory base register，PDBR）保存了页目录表的物理地址（按页对齐）。

PTE格式（8 bit）:

```plain
  VALID | PFN6 ... PFN0
```

PDE格式（8 bit）:

```plain
  VALID | PT6 ... PT0
```

其中

```plain
VALID==1表示，表示映射存在；VALID==0表示，表示映射不存在。
PFN6..0:页帧号
PT6..0:页表的物理基址>>5
```

（1）在[物理内存模拟数据文件](https://github.com/chyyuu/os_course_exercises/blob/2018spring/all/03-2-spoc-testdata.md)中，给出了4KB物理内存空间的值，请回答下列虚地址是否有合法对应的物理内存，请给出对应的pde index, pde contents, pte index, pte contents。

```plain
1) Virtual Address 6c74
   Virtual Address 6b22
2) Virtual Address 03df
   Virtual Address 69dc
3) Virtual Address 317a
   Virtual Address 4546
4) Virtual Address 2c03
   Virtual Address 7fd7
5) Virtual Address 390e
   Virtual Address 748b
```

比如答案可以如下表示： (注意：下面的结果是错的，你需要关注的是如何表示)

```plain
Virtual Address 7570:
  -> pde index:0x1d  pde contents:(valid 1, pfn 0x33)
    -> pte index:0xb  pte contents:(valid 0, pfn 0x7f)
      -> Fault (page table entry not valid)

Virtual Address 21e1:
  -> pde index:0x8  pde contents:(valid 0, pfn 0x7f)
      -> Fault (page directory entry not valid)

Virtual Address 7268:
  -> pde index:0x1c  pde contents:(valid 1, pfn 0x5e)
    -> pte index:0x13  pte contents:(valid 1, pfn 0x65)
      -> Translates to Physical Address 0xca8 -> Value: 16
```

已有参考：

[链接](https://piazza.com/class/i5j09fnsl7k5x0/post/1161)处有参考答案。请比较你的结果与参考答案是否一致。如果不一致，请说明原因。

（2）请基于你对原理课二级页表的理解，并参考Lab2建页表的过程，设计一个应用程序（可基于C、Rust、python、ruby、C++、LISP、JavaScript等）模拟实现题目中描述的抽象OS，正确完成二级页表转换。

已有参考：

[链接](https://piazza.com/class/i5j09fnsl7k5x0/post/1161)处有参考答案。请比较你的结果与参考答案是否一致。如果不一致，提交你的实现，并说明区别。

### 第6次课后练习（第四周周四）
#### 第1题
用C或Rust语言实现如下的改进伙伴系统。

修改伙伴系统分配操作：

1. 由小到大在空闲块中找最小可用块；
2. 如空闲块大于申请块的二倍，对可用空闲块进行二等分，直到得到合适可用空闲块；
3. 如空闲块大于申请块的4/3，对可用空闲块进行四等分，直到得到合适可用空闲块

分析“改进伙伴系统”的存储利用率和分配释放开销。

##### 已有参考
+ 闭浩扬：[改进伙伴系统实现](https://github.com/scPointer/advanced_buddy_system)
+ [buddy_system_allocator](https://lib.rs/crates/buddy_system_allocator)：陈嘉杰同学用Rust写的伙伴系统算法
+ [buddy-system-in-ucore](https://github.com/ucore-test/buddy-system-in-ucore-test#buddy-system-in-ucore-test)：黄旺同学用C写的伙伴系统算法

##### 往年的优秀问答
+ [2023秋季的优秀回答](https://www.yuque.com/xyong-9fuoz/qczol5/uzf18vbnscar3hzi#wzira)

### 实验一（第三周周一）
+ 实验任务：增加一个系统调用`sys_task_info()` 
    - [uCore实验一任务描述](https://learningos.github.io/uCore-Tutorial-Guide/chapter3/5exercise.html#id1)
    - [rCore实验一任务描述](https://learningos.github.io/rCore-Tutorial-Guide/chapter3/5exercise.html#chapter3)
+ 实验提交要求 
    - 在课程注册时自动创建实验仓库中提交完整的代码和文档；
    - 在荷塘雨课中提交实验一报告链接和commit ID；
    - 实验截止时间：布置实验任务后的第13天（10月12日24点）；

#### 参考资料
Github上实验仓库：

+ rCore
    - 指导书：[https://learningos.cn/rCore-Tutorial-Guide/index.html](https://learningos.cn/rCore-Tutorial-Guide/index.html)
    - 内核代码：[https://github.com/LearningOS/rCore-Tutorial-Code](https://github.com/LearningOS/rCore-Tutorial-Code)
    - 内核测试用例：[https://github.com/LearningOS/rcore-tutorial-test](https://github.com/LearningOS/rcore-tutorial-test)
+ uCore
    - 指导书：[https://learningos.cn/uCore-Tutorial-Guide/index.html](https://learningos.cn/uCore-Tutorial-Guide/index.html)
    - 内核代码：[https://github.com/LearningOS/uCore-Tutorial-Code](https://github.com/LearningOS/uCore-Tutorial-Code)
    - 内核测试用例：[https://github.com/LearningOS/ucore-tutorial-test](https://github.com/LearningOS/ucore-tutorial-test)

### 第5次课后练习（第二周周日）
#### 第1题
参考：[理解X86的内存管理](https://blog.51cto.com/u_15127506/4352910)

假设在x86-32 CPU的计算机系统中，物理内存大小了4GB，每个页表项占4B；如下图所示，可以采用一级页表，也可以采用二级页表。

32位地址和4MB页大小的线性地址转换

![](https://cdn.nlark.com/yuque/0/2025/png/32415872/1759049481874-2a2f6a40-2714-4d1a-98d3-816e3a3f5583.png)

32位地址和4KB页大小的线性地址转换

![](https://cdn.nlark.com/yuque/0/2025/png/32415872/1759049496680-52232b59-e19e-474f-92a3-16ca988b7eb4.png)

请回答如下问题：

1. 选择一种你感兴趣的页表结构，给出一种可能的页表定义，完整实现4GB虚拟地址空间到物理地址空间的映射关系，使得每个内在单元的虚拟地址和物理地址都是相同的。
2. 你自己定义的这个页表结构中，页表占多大内在空间？页表起始单元的虚拟地址和物理地址分别是多少？整个页表空间对应哪些页表项？要求给出相关页表项的虚拟地址和物理地址。

#### 第2题
依据自己的实验选择，分析uCore或rCore中下面执行过程，并形成文档。

1. 批处理操作系统中应用程序管理数据结构的组成；
2. 应用程序管理数据结构的初始化过程；
3. trapframe数据结构的组成；
4. 在系统调用过程中的trapframe数据结构的保存过程；
5. 在系统调用返回过程中的从trapframe数据结构恢复应用程序执行上下文的过程；
6. 系统调用执行过程中的参数和返回值传递过程；

##### 往年的优秀问答
+ [uCore的系统调用执行过程分析](https://www.yuque.com/songxixuan/ho6p8f/sc144ah8vl1ggy02)

### 第4次课后练习（第二周周四）
#### 第1题
计算机系的gitlab环境已准备好，所有选课同学访问“[课程实验入口页面](https://lab.cs.tsinghua.edu.cn/unilab/home)”，并确认自己的实验选择（uCore或rCore）。然后清华gitlab平台会依据实验选择自动创建每位同学的实验仓库，并复制实验基准代码。请同学们在完成仓库创建后，回复仓库链接和采用的编程语言。

#### 第2题
基于在用户态执行特权指令的[小例子](https://github.com/chyyuu/os_kernel_lab/blob/v4-illegal-priv-code-csr-in-u-mode-app-v2/os/src/main.rs#L306)，进行修改实现如下的功能。把“sret”的行为修改成我们定义的新指令“uinst”；它的行为是，在内核态向串口输出一个字符串“sret -> ebreak”，然后返回继续执行下一条指令。

##### 结果提交方式
+ 文档和代码提交到公开的git仓库中，提交文档链接和commit id；

##### 参考资料
+ [为K210芯片实现RISC‐V 1.12版特权级标准](https://github.com/rustsbi/rustsbi-k210/wiki/%E4%B8%BAK210%E8%8A%AF%E7%89%87%E5%AE%9E%E7%8E%B0RISC%E2%80%90V-1.12%E7%89%88%E7%89%B9%E6%9D%83%E7%BA%A7%E6%A0%87%E5%87%86)：这是华中科大蒋周奇和车春池两位同学在RustSBI中做的一个工作，在RISC-V 1.9.1版本特权级标准的CPU（K210）中基于异常处理机制实现了对RISC-V 1.12版特权级标准的支持。

### 第3次课后练习（第二周周一）
#### 第1题
依据操作系统课实验的选择，搭建所需要的实验环境。然后描述自己在搭建实验环境过程中问题和解决方法。

+ [uCore实验环境配置](https://learningos.github.io/uCore-Tutorial-Guide/chapter0/1setup-devel-env.html)
+ [rCore实验环境配置](https://learningos.github.io/rCore-Tutorial-Guide/0setup-devel-env.html)

##### 往年的优秀问答
+ [2023年优秀回答](https://www.yuque.com/xyong-9fuoz/qczol5/uzf18vbnscar3hzi#JBjvd)

#### 第2题
在你选择的开发和运行环境下，写一个函数print_stackframe()，用于获取当前位置的函数调用栈信息。实现如下一种或多种功能：函数入口地址、函数名信息、参数调用参数信息、返回值信息。

可能的环境选择：

+ 操作系统环境：Linux、uCore、rCore、MacOS、Windows...
+ 特权级：用户态、内核态
+ 编程语言：Rust、C...

已有参考：

+ [在ucore中写一个函数print_stackframe()](https://piazza.com/class/i5j09fnsl7k5x0/post/1273)：这里有多种可以在uCore和rCore上可以工作的print_stackframe()实现；（[piazza访问帮助](https://www.yuque.com/xyong-9fuoz/qczol5/gwv6926mfr9nnhc5#pbG6V)）
+ [在 print_stackframe() 中如何打印出被调用函数的参数列表和运行时的值](https://piazza.com/class/i5j09fnsl7k5x0/post/996#)：这是一个开放的还没有很好实现的题目；
+ [获取内核堆栈回溯信息的实用程序](https://github.com/os-module/tracer)：北京理工大学陈林峰同学给出比较完善的Rust语言的函数调用栈回溯工具。
+ [axbacktrace](https://github.com/kern-crates/axbacktrace)：郭伟康给出的ArceOS的函数调用栈回溯组件。

结果提交方式：（三选一）

1. 写成markdown、docx、PDF等格式的文档，提交文档和代码压缩包；
2. 文档和代码提交到公开的git仓库中，提交文档链接和commit id；
3. 写成博客一类的在线分享文档，提交在线访问链接；

##### 往年的优秀问答
+ [2023年优秀回答](https://www.yuque.com/xyong-9fuoz/qczol5/uzf18vbnscar3hzi#aad53)

### 第2次课后练习（第一周周四）
#### 第1题
熟练使用开发环境是顺利和高效完成操作系统课实验的必要条件。请从互联网搜索你需要的信息，以逐渐熟练使用qemu、shell、vim（也可以是其他你喜欢的代码编辑工具）和git等工具。然后回答如下问题。

1. 简要介绍一个模拟器工具，并查找相关的配置使用帮助；
2. 简要介绍一个命令行工具，并查找相关的配置使用帮助；
3. 简要介绍一个代码编辑工具，并查找相关的配置使用帮助；
4. 简要介绍一个代码版本维护工具，并查找相关的配置使用帮助；
+ 参考资料：
    - [Learn Git Branching](https://learngitbranching.js.org/?locale=zh_CN)
    - [计算机教育中缺失的一课](https://missing-semester-cn.github.io/)（MIT的开发工具使用的课堂）
    - B站视频：计算机教育中缺失的一课 [The Missing Semester of Your CS Education](https://www.bilibili.com/video/BV1rU4y1h7Qr)
    - 【中字】[The Missing Semester 第1讲 - 课程概览与 Shell - MIT 公开课(2020)](https://www.bilibili.com/video/BV1Eo4y1d7KZ)

##### 往年的优秀回答
+ [2023年优秀回答](https://www.yuque.com/xyong-9fuoz/qczol5/uzf18vbnscar3hzi#BO7wm)

#### 第2题
下面是一组使用系统调用服务的应用程序。请尝试运行和分析其中的一个你有兴趣小例子的执行过程，利用Linux系统中的[strace工具](https://zhuanlan.zhihu.com/p/69527356)来确定该应用程序在执行时调用了哪些系统调用。

+ [使用操作系统的系统调用服务的应用程序示例列表](https://pdos.csail.mit.edu/6.828/2021/lec/l-overview/)（出处：MIT的操作系统课）
    -  [copy.c](https://pdos.csail.mit.edu/6.828/2021/lec/l-overview/copy.c) 
    -  [echo.c](https://pdos.csail.mit.edu/6.828/2021/lec/l-overview/echo.c) 
    -  [exec.c](https://pdos.csail.mit.edu/6.828/2021/lec/l-overview/exec.c) 
    -  [fork.c](https://pdos.csail.mit.edu/6.828/2021/lec/l-overview/fork.c) 
    -  [forkexec.c](https://pdos.csail.mit.edu/6.828/2021/lec/l-overview/forkexec.c) 
    -  [list.c](https://pdos.csail.mit.edu/6.828/2021/lec/l-overview/list.c) 
    -  [open.c](https://pdos.csail.mit.edu/6.828/2021/lec/l-overview/open.c) 
    -  [pipe1.c](https://pdos.csail.mit.edu/6.828/2021/lec/l-overview/pipe1.c) 
    -  [pipe2.c](https://pdos.csail.mit.edu/6.828/2021/lec/l-overview/pipe2.c) 
    -  [redirect.c](https://pdos.csail.mit.edu/6.828/2021/lec/l-overview/redirect.c) 
-->



### 第1次课后练习（第一周周一）
#### 第1题
填写选课问卷，然后回答是否已提交。

+ [2026秋季操作系统课选课问卷](http://oscourse2019.mikecrm.com/j5wEw5T)（访问密码：`8e2JC8KFxq+Vere`）
