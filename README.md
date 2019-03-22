# java_interview

## 操作系统
## 算法
## java基础
### 语法
### 多线程

## 面向对象 
### SOLID原则
### 设计模式
## 关系型数据库
## 中间件（高级-资深开发）
## 大数据（大数据工程师）

Hashcode的作用，与 equal 有什么区别？

a.同样用于鉴定2个对象是否相等的，java集合中有 list 和 set 两类，其中 set不允许元素重复实现，那个这个不允许重复实现的方法，如果用 equal 去比较的话，如果存在1000个元素，你 new 一个新的元素出来，需要去调用1000次 equal 去逐个和他们比较是否是同一个对象，这样会大大降低效率。hashcode实际上是返回对象的存储地址，如果这个位置上没有元素，就把元素直接存储在上面，如果这个位置上已经存在元素，这个时候才去调用equal方法与新元素进行比较，相同的话就不存了，散列到其他地址上。

--------------------------------------------------------

concurrentmap的原理？为什么这么处理？


-------------------------------------------------------

spring aop -》 java代理

类加载器
1.装载：将Java二进制代码导入jvm中，生成Class文件。
2.连接：a）校验：检查载入Class文件数据的正确性 b）准备：给类的静态变量分配存储空间 c）解析：将符号引用转成直接引用
3：初始化：对类的静态变量，静态方法和静态代码块执行初始化工作。
双亲委派模型：类加载器收到类加载请求，首先将请求委派给父类加载器完成 用户自定义加载器->应用程序加载器->扩展类加载器->启动类加载器。

----------------------------------------------------

内存模型
Java虚拟机规范中将Java运行时数据分为六种。
1.程序计数器：是一个数据结构，用于保存当前正常执行的程序的内存地址。Java虚拟机的多线程就是通过线程轮流切换并分配处理器时间来实现的，为了线程切换后能恢复到正确的位置，每条线程都需要一个独立的程序计数器，互不影响，该区域为“线程私有”。
2.Java虚拟机栈：线程私有的，与线程生命周期相同，用于存储局部变量表，操作栈，方法返回值。局部变量表放着基本数据类型，还有对象的引用。
3.本地方法栈：跟虚拟机栈很像，不过它是为虚拟机使用到的Native方法服务。
4.Java堆：所有线程共享的一块内存区域，对象实例几乎都在这分配内存。
5.方法区：各个线程共享的区域，储存虚拟机加载的类信息，常量，静态变量，编译后的代码。
6.运行时常量池：代表运行时每个class文件中的常量表。包括几种常量：编译时的数字常量、方法或者域的引用。

---------------------------------------------------


ioc的理解 -》 spring中如何实现
Spring IOC （控制反转，依赖注入）
Spring支持三种依赖注入方式，分别是属性（Setter方法）注入，构造注入和接口注入。
在Spring中，那些组成应用的主体及由Spring IOC容器所管理的对象被称之为Bean。
Spring的IOC容器通过反射的机制实例化Bean并建立Bean之间的依赖关系。
简单地讲，Bean就是由Spring IOC容器初始化、装配及被管理的对象。
获取Bean对象的过程，首先通过Resource加载配置文件并启动IOC容器，然后通过getBean方法获取bean对象，就可以调用他的方法。
Spring Bean的作用域：
Singleton：Spring IOC容器中只有一个共享的Bean实例，一般都是Singleton作用域。
Prototype：每一个请求，会产生一个新的Bean实例。
Request：每一次http请求会产生一个新的Bean实例

-----------------------------------------------------

中间件的了解：缓存（一致性）、消息、zookeeper

微服务的理解

## 关系型数据库
索引：B+，B-,全文索引
Mysql的索引是一个数据结构，旨在使数据库高效的查找数据。
常用的数据结构是B+Tree，每个叶子节点不但存放了索引键的相关信息还增加了指向相邻叶子节点的指针，这样就形成了带有顺序访问指针的B+Tree，做这个优化的目的是提高不同区间访问的性能。
什么时候使用索引：

经常出现在group by,order by和distinc关键字后面的字段
经常与其他表进行连接的表，在连接字段上应该建立索引
经常出现在Where子句中的字段
经常出现用作查询选择的字段

--------------------------------

大数据：HBASE的好处和瓶颈，怎么样优化

遇到什么难题？

职业规划
