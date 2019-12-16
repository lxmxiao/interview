## Spring AOP 、IOC、ID

* IOC

  spring框架将service对象统一管理起来

  * IOC 是通过反射实现的
  * IOC 容器来管理对象的生命周期、依赖关系，可以解决一些代码耦合
  * 把对象生成放在 xml 定义里面

* ID

  依赖注入，spring将依赖注入的对象动态管理起来

  * setter 注入：我们可以增加一个setter函数来传入创建好的对象，避免了初始化对象
  * 构造器注入：创建一个构造器
  * 接口注入

* AOP

  * Before、after、afterReturning(发生异常不执行)、after Throwing、around(环绕)
  * 如果要用AOP注解，需要开启<aop:aspectj-autoproxy proxy-target-class="true"/>

## Spring MVC 的核心入口是什么

DispatchServlet

## Spring MVC 怎么样设定重定向和转发的

* 在返回值前面加”forward:”就可以让结果转发
* 在返回值前面加”redirect:”就可以让返回值重定向

## Spring MVC 执行流程

1. 创建 Spring 容器
2. 发送 http 请求到核心控制器
3. 通过映射器找到相信的业务控制器
4. 使用适配器找到相应的业务类
5. 执行完业务类后使用ModelAndView进行视图转发，数据放在model中，用map传递数据进行页面显示