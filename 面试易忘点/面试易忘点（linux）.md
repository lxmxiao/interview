## Linux 如何查看日志

* cat

* vim

  进入vim编辑模式

* tail

  -n  是显示行号；（查询n行日志）

  tail -n 10 test.log    （查询日志尾部最后10行的日志）

* head

  跟tail是相反的，tail是看后多少行日志，而head是查看日志文件的头多少行

## Nginx 和 Tomcat 的区别

* 应用方面

  tomcat 一般是做动态解析才会用得到，支持 jsp 的解析，需要配置 JDK 支持

  nginx，一般做静态，不具备动态解析能力

* 性能方面

  tomcat 支持并发并不高，100左右

  nginx 可以做到好几万



