## 基本命令

* 模糊查询

  通配符 \* 可替代任何，可使用在最前面也可以在最后面

* 判断 key 是否存在

  EXISTS

## redis 存储策略

#### RDB

默认存储方式 ，保存内存快照，fork一个子进程去存储，每隔一段时间把所有东西保存在文件中

优点：

- 数据全
- 数据存放整齐

缺点：

- 占用性能

#### AOF

文件追加，保存变化

以日志形式记录Server处理的每一个增删改

## redis 序列化

JdkSerializationRedisSerializer

* **Jackson2JsonRedisSerializer**

  若待序列化对象没有实现Serializable接口，但有无参构造器，要用Jackson2JsonRedisSerializer

* JdkSerializationRedisSerializer

  使用JdkSerializationRedisSerializer序列化的Bean必须实现**Serializable**接口

* GenericJackson2JsonRedisSerializer

  LocalDate这是java8新增的类，GenericJackson2JsonRedisSerializer序列化方式无法识别

* **StringRedisSerializer**

  不能序列化Bean，只能序列化字符串类型的数据

* GenericFastJsonRedisSerializer

  目前没有发现问题，很好用