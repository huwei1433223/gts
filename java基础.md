## java基础---------------------



#### java基本数据类型

（1）基本数据类型，分为boolean(1)、byte(1)、short(2)、char(2)、int(4)、float(4)、long(8)、double(8)；
（2）引用数据类型 ，分为数组、类、接口。

#### Int与Integer

为了编程的方便引入了基本数据类型，能够将这些基本数据类型当成对象操作，Java为每 一个基本数据类型都引入了对应的包装类型，int的包装类就是Integer，有自动装箱/拆箱机制，使得二者可以相互转换。

**int与Integer的基本使用对比**

- Integer是int的包装类；int是基本数据类型；
- Integer变量必须实例化后才能使用；int变量不需要；
- Integer实际是对象的引用，指向此new的Integer对象；int是直接存储数据值 ；
- Integer的默认值是null；int的默认值是0。

**Integer常用方法**

**compareTo方法**：在数字上比较两个 `Integer` 对象。

**intValue方法**：以 `int` 类型返回该 `Integer` 的值。

**toString方法**：返回一个表示该 `Integer` 值的 `String` 对象。



#### java容器

List：ArrayList：有序，数组实现，默认长度为10，扩容1.5倍 查询快，增删慢，线程不安全

​		   LinkerdList：双向链表实现，查询慢，增删快 线程不安全

​		   Vector ：底层数据结构是数组，查询快，增删慢。线程安全。 速度慢

Set：HashSet：保证元素的唯一性，用来去重，无序

​		  TreeSet：与hashset比是有有序的

Map：HashMap ：以键值对的方式存储数据，使用数组和双向链表或者红黑树实现，默认长度为16，当数组的长度达到64，并且双向链表的长度到达8，就会转为红黑树 ，负载因子默认是0.75，到达这个值时，会以2的整数倍数进行扩容

​		   LinkedHashMap：类似于HashMap，但是他是有序的

​		    TreeMap  ：它的特点在于，所得到的结果是经过排序的

​            ConcurrentHashMap ：一种线程安全的Map。 

#### equals和==有什么区别？

- 对于基本数据类型，==比较的是他们的值。基本数据类型没有equal方法；
- 对于复合数据类型，==比较的是它们的存放地址(是否是同一个对象)。`equals()`默认比较地址值，重写的话按照重写逻辑去比较。

#### throw和throws的区别？

- **throw**：用于抛出一个具体的异常对象。
- **throws**：用在方法签名中，用于声明该方法可能抛出的异常。子类方法抛出的异常范围更加小，或者根本不抛异常。

#### 类实例化的顺序

1. 静态属性，静态代码块。
2. 普通属性，普通代码块。
3. 构造方法。

#### **接口与抽象类的区别**

​	**抽象类**：

​	1、抽象类不能被实例化只能被继承；他的抽象方法的修饰符只能为public或者protected，默认为public，他可以包含属性、方法、构造方法，但是构造方法不能用于实例化，主要用途是被子类调用。

​	**接口**：

​	1、接口可以包含变量、方法；变量被隐士指定为public static final，方法被隐士指定为public abstract；接口可以间接的解决Java中类的单继承问题，就是一个接口可以extends（继承）多个接口

​	2、一个类也可以实现多个接口；

​	**相同点**

（1）都不能被实例化 （2）他们都只有实现了接口或抽象类中的方法后才能实例化。

​	**不同点**

（1）接口只有定义，不能有方法的实现，  而抽象类可以有定义与实现，方法可在抽象类中实现。

（2）实现接口的关键字为implements，继承抽象类的关键字为extends。一个类可以实现多个接口，但一个类只能继承一个抽象类。

（3）接口成员变量默认为public static final，必须赋初值，不能被修改；其所有的成员方法都是public、abstract的。                                  抽象类中成员变量可在子类中被重新定义，也可被重新赋值；抽象方法被abstract修饰，不能被private、static修饰

#### 方法重载和重写的区别？

**重载：**

同个类中的多个方法可以有相同的方法名称，但是有不同的参数列表。就是参数的类型、个数、顺序，只要有一个不同就叫做参数列表不同。

**重写：**

**重写的话，说的是是父类和子类之间的关系。当父类的功能无法满足子类的需求，可以在子类对方法进行重写**。方法重写的时侯， 方法名与形参列表必须相同。





#### 	**String常用方法**

​	<img src="C:\Users\23168\AppData\Roaming\Typora\typora-user-images\image-20230905204253467.png" alt="image-20230905204253467" style="zoom: 80%;" />

<img src="C:\Users\23168\AppData\Roaming\Typora\typora-user-images\image-20230905204311678.png" alt="image-20230905204311678" style="zoom:80%;" align="left" />

<img src="C:\Users\23168\AppData\Roaming\Typora\typora-user-images\image-20230905204327103.png" alt="image-20230905204327103" align="left" style="zoom:80%;" />

<img src="C:\Users\23168\AppData\Roaming\Typora\typora-user-images\image-20230905204540126.png" alt="image-20230905204540126" align="left" style="zoom:80%;" />

<img src="C:\Users\23168\AppData\Roaming\Typora\typora-user-images\image-20230905204629532.png" alt="image-20230905204629532" align="left" style="zoom:80%;" />



#### String, StringBuffer 和 StringBuilder区别

​	**1. 可变性**

- String 不可变
- StringBuffer 和 StringBuilder 可变

**2. 线程安全**

- String 不可变，因此是线程安全的
- StringBuilder 不是线程安全的
- StringBuffer 是线程安全的，内部使用 synchronized 进行同步



#### 创建线程有哪几种方式？

创建线程有三种方式：

- 继承 Thread 重写 run 方法；
- 实现 Runnable 接口；
- 实现 Callable 接口。

#### 说一下 runnable 和 callable 有什么区别？

runnable 没有返回值，callable 可以拿到有返回值，callable 可以看作是 runnable 的补充。

####  线程有哪些状态？

- NEW 尚未启动
- RUNNABLE 正在执行中
- BLOCKED 阻塞的（被同步锁或者IO锁阻塞）
- WAITING 永久等待状态
- TIMED_WAITING 等待指定的时间重新被唤醒的状态
- TERMINATED 执行完成



#### sleep() 和 wait() 有什么区别？

- 类的不同：sleep() 来自 Thread，wait() 来自 Object。
- 释放锁：sleep() 不释放锁；wait() 释放锁。
- 用法不同：sleep() 时间到会自动恢复；wait() 可以使用 notify()/notifyAll()直接唤醒。

#### 在 Java 程序中怎么保证多线程的运行安全？

- 方法一：使用安全类，比如 Java. util. concurrent 下的类。
- 方法二：使用自动锁 synchronized。
- 方法三：使用手动锁 Lock。

#### 线程池都有哪些状态？

- RUNNING：这是最正常的状态，接受新的任务，处理等待队列中的任务。
- SHUTDOWN：不接受新的任务提交，但是会继续处理等待队列中的任务。
- STOP：不接受新的任务提交，不再处理等待队列中的任务，中断正在执行任务的线程。
- TIDYING：所有的任务都销毁了，workCount 为 0，线程池的状态在转换为 TIDYING 状态时，会执行钩子方法 terminated()。
- TERMINATED：terminated()方法结束后，线程池的状态就会变成这个。

##  sql----------------------------

#### 索引

**1.什么是索引**
索引指数据库的目录，比如：字典上面的字母目录 (适用于大数据量)

**2.建立索引的优缺点**
优点:查询速度快
缺点：增删改慢，因为数据库要同步去维护索引文件，所以速度慢

**3.索引有哪些**
普通 主键 唯一 组合

**4. 索引检索为什么快**
索引结构：B+Tree

**5.一般你们会在什么情况下加索引**
（1）主键自动建立唯一索引
（2）频繁作为查询条件的字段应该创建索引
（3）查询中与其他表关联的字段，外键关系建立索引
（4）单键/组合索引的选择问题，组合索引的性价比更高
（5）查询中排序的字段，排序字段若通过索引去访问将大大提高排序速度
（6）查询中统计或者分组字段。
（7）过滤条件好的字段选择一段选择加索引

**6.怎么知道索引用没用上**
通过explain查询sql执行计划，主要看key使用的是哪个索引

**7.用过组合索引吗，是有序的吗**
用过， 有序

#### **使索引失效？**

（1）like查询是以%开头，例如like “%三%，前面不能+%
（2）如果列类型是字符串，那在查询条件中需要将数据用引号引用起来，否则不走索引
（3）使用 关键字 in ，or ，null，!=

​	(4)索引列上参与计算会导致索引失效 

​	(5)违背最左匹配原则 age索引是和建立再(name,age)组合索引的基础上，当查询条件中没有第一个组合索引的字段(name)会导致索引失效

​	(6)如果mysql估计全表扫描要比使用索引要快，会不适用索引

#### sql优化

一.首先开启数据库慢查询日志，(修改my.cnf文件，把slow_query_log = 1和slow_query_log_file = /var/lib/mysql/25f5fb0c6ff0-slow.log配置进配置文件，永久开启慢查询日志),定位到查询效率比较低的sql , 找出对应的sql语句并进行分析
1.表设计是否规范，是否符合三范式的标准
（1）第一范式：保证原子性（不可拆分）
（2）第二范式：每张表都有主键
（3）第三范式（每一列都有主键相关)
2.查看数据表中是否存在大量的冗余字段，字段数据类型是否合理
3.尽可能的使用varchar代替char 建表数据类型，能用数值的绝对不用字符存储
4.尽量避免null值，使用默认值替代空值，数值型可以使用0，字符型可以使用空字符串

二.查看sql语句是否规范
（1）避免使用关键字：or ，in，not in ，!=，<>，避免使用select *
（2）尽量避免子查询，大部分子查询都可以连接查询
（3）用到or的地方可以使用union去代替实现
（4）用到in的地方可以使用exists去代替

三.分析sql的索引是否可以用上
（1) explain查询sql的执行计划,重点关注的几个列就是，type是不是全表扫描
（2）看一下索引是否能够用的上,主要看key使用的是哪个索引
（3）看一下rows扫描行数是不是很大

#### **join**

左连接：left [outer] join,左连接从左表(t1)取出所有记录,与右表(t2)匹配。如果没有匹配，以null值代表右边表的列。

右连接：right [outer] join，右连接从右表(t2)取出所有记录，与左表(t1)匹配。如果没有匹配，以null值代表左边表的列。

内连接，也叫等值连接， inner join得出同时存在t1表和t2表的数据集，通俗一点说就是求两个表的交集。

sql优化



## spring-------------------------

**springboot是什么**

SpringBoot来简化Spring应用开发，约定大于配置，去繁化简，嵌入的tomcat无需部署war文件，可以自动配置，Spring有对应的功能starter

#### SpringBoot的核心注解是什么？由那些注解组成？

- @**SpringBootConfiguration**：
  组合了 @Configuration 注解，实现配置文件的功能。
- @**EnableAutoConfiguration**：
  打开自动配置的功能，也可以关闭某个自动配置的选项，如关闭数据源自动配置功能： @SpringBootApplication(exclude = { DataSourceAutoConfiguration.class })。
- @**ComponentScan**：
  Spring组件扫描。



**常用注解：**controller service commpoment config SpringbootAplication Transaction before after around  requestMapping  getMapping postMapping deleteMaopping putMapping

#### **IOC是什么**

IOC就是控制反转，把原来代码里的对象创建和和依赖反转给容器来帮忙处理，一般使用xml文件或者注解定义对象间的关系。

他的实现方式是依赖注入（DI），是指对象被动地接受依赖类而不用自己主动去找，对象不是从容器中查找它依赖的类，而是在容器实例化对象时主动将它依赖的类注入给它。假设一个 Car类需要一个Engine的对象，那么一般需要需要手动new一个 Engine，利用loC就只需要定义一个私有的Engine类型的成员变量，容器会在运行时自动创建一个 Engine 的实例对象并将引用自动注入给成员变量。



#### **AOP是什么？**

AOP 即面向切面编程，简单地说就是将代码中重复的部分抽取出来，在需要执行的时候使用动态代理技术，在不修改源码的基础上对方法进行增强。与OOP相比，传统的OOP开发中，代码逻辑在处理一些大量类需要使用的公用的方法时会出现问题，比如日志，权限认证等，会导致主业务逻辑关系被这些公用代码逻辑打乱，散落在代码的各个地方，造成难以维护，AOP的编程思想就是把业务逻辑和公用横切进行分离，从而达到解耦的目的，使代码的重用性和开发效率高（目的是重用代码，把公共的代码抽取出来）

**AOP的应用场景有哪些呢？**

1、日志记录

2、权限验证

3、效率检查（个人在代码上，喜欢用注解+切面，实现校验，redis分布式锁等功能）

4、事务管理（[spring](https://cloud.tencent.com/developer/tools/blog-entry?target=https%3A%2F%2Fjavajgs.com%2Farchives%2Ftag%2Fspring) 的事务就是用AOP实现的）

**springAop的底层是怎样实现的？**

动态代理：1、JDK动态代理      2、CGLIB代理

**spring AOP 默认使用jdk动态代理还是cglib？**

要看条件，如果实现了接口的类，是使用jdk。如果没实现接口，默认使用cglib。

#### AOP 的相关注解有哪些？

@Aspect:声明被注解的类是一个切面Bean。
@Before:前置通知,指在某个连接点之前执行的通知。
@After:后置通知，指某个连接点退出时执行的通知(不论正常返回还是异常退出)。
@AfterReturning:返回后通知，指某连接点正常完成之后执行的通知,返回值使用returning属性接收。
@AfterThrowing:异常通知，指方法抛出异常导致退出时执行的通知，和@AfterReturning只会有一个执行，异常使用throwing属性接收。

#### 事务管理

**什么是事务？**   

- 在[数据库](https://cloud.tencent.com/solution/database?from_column=20065&from=20065)开发中，一组业务逻辑操作，要么全部成功，要么全部失败。

**事务有什么特定？ACID**    

- 原子性：整体，原子不可分割的。整个操作被看成一个整体，要么成功，要么失败。
- 一致性：数据，事务操作的前后数据一致。
- 隔离性：并发，两个事务之间并发访问情况。
- 持久性：结果，事务一旦提交，不能回滚。

**隔离有什么问题？**

- 脏读：一个事务读到了另一个事务没有提交的数据。
- 不可重复读：一个事务读到了另一个事务已有提交的数据（update）。
- 幻读：一个事务读到了另一个事务已有提交的数据（insert）。

**隔离级别有那些？**    

- 读未提交：存在3个问题（脏读、不可重复读、幻读）
- 读已提交：解决1个问题（脏读），存在2个问题（不可重复读、幻读）
- 可重复读：解决2个问题（脏读、不可重复读）、存在1个问题（幻读）
- 串行化：解决3个问题（脏读、不可重复读、幻读）–单事务



## redis

Redis支持五种数据类型：string（字符串），hash（哈希），list（列表），set（集合）及zset(sorted set：有序集合)。
