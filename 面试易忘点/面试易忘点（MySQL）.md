## MySQL 批量插入

* mapping 中 foreach 语句
* 代码 for 循环
* SqlSession （mybatis 底层实现）

## 插入后返回主键

* mybatis 中

  LAST_INSERT_ID（因为LAST_INSERT_ID是基于Connection的，只对当前用户的连接有效）所以是线程安全的

* mybatis-plus 中

  insert 的返回值就是插入的主键

* mapper.xml 中

  selectKey 标签

## MySQL 三大范式

* 第一范式（1NF）：是指数据库表的每一列都是不可分割的基本数据项，同一列中不能有多个值，即实体中的某个属性不能有多个值或者不能有重复的属性。
* 第二范式（2NF）：2NF在1NF的基础之上，消除了非主属性对于码的部分函数依赖（必须要有一个键与这列数据相关）
* 第三范式（3NF）：3NF在2NF的基础之上，消除了非主属性对于码的传递函数依赖（必须与主键直接相关，不能间接相关）

## 四种事务的特性

* 原子性
* 一致性
* 持久性
* 隔离性

## 四种事务隔离级别

* 可串行化（Serializable）:sql中最高的隔离性级别，能够避免脏读，幻读，不可重复读。代价也相对沉重，会大大影响数据库的性能。
* 可重复读（Repeatable read）:只允许读取已提交的数据，而且在一个事务两次读取一个数据项期间，其他事务不得更新该数据。这种状态**不能避免幻读**。
* 已提交读（Read committed）：只允许读取已提交数据，但不要求可重复读。这种状态只能避免**脏读**。
* 未提交读（Read uncommitted）：允许读取未提交的数据。这是最低的隔离级别，脏读，幻读，不可重复读都无法避免。

## 有RPC，为什么要用 Dubbo

* 负载均衡
* 解决服务之间的调用问题
* 基于访问压力实时管理集群容量，提高集群访问率
* 服务降级，某服务挂掉之后调用备用服务

## SQL 命令

将两个 select 结果合并显示

* UNION

  对结果去重且排序

* UNION ALL（性能比较好）

  直接返回合并结果，不去重也不排序

## 数据库关键字顺序

from > where > group by > having > select > rownum > order by

## 读写分离

把数据库分为读库和写库

读库只负责读

写库只负责写

## 乐观锁和悲观锁

* 乐观锁

  总是假设最好的情况，每次去拿数据的时候都认为别人不会修改，所以不会上锁，但是在更新的时候会判断一下在此期间别人有没有去更新这个数据，可以使用版本号机制和CAS算法实现。**乐观锁适用于多读的应用类型，这样可以提高吞吐量**

* 悲观锁

  总是假设最坏的情况，每次去拿数据的时候都认为别人会修改，所以每次在拿数据的时候都会上锁，这样别人想拿这个数据就会阻塞直到它拿到锁（**共享资源每次只给一个线程使用，其它线程阻塞，用完后再把资源转让给其它线程**）

