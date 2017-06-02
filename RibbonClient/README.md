Ribbon是一个基于HTTP和TCP客户端的负载均衡器。
Ribbon可以在通过客户端中配置的ribbonServerList服务端列表去轮询访问以达到均衡负载的作用。

第一种：
  1.RibbonServer一个服务端先启动
  application.yml配置文件最好放在这里，不要放在application.properties
  2.RibbonClient客户端启动
浏览器上执行：
$ curl http://localhost:8888/hi
Greetings, Artaban!

$ curl http://localhost:8888/hi?name=Orontes
Salutations, Orontes!

第二种：
  1.RibbonServer多个服务端先启动
  target目录下找到RibbonServer-0.0.1-SNAPSHOT.jar，在windows cmd窗口执行：
  java -jar RibbonServer-0.0.1-SNAPSHOT.jar   --server.port=8090
  java -jar RibbonServer-0.0.1-SNAPSHOT.jar   --server.port=9092
  java -jar RibbonServer-0.0.1-SNAPSHOT.jar   --server.port=9999
  2.新建UserApplication、SayHelloConfiguration
  3.RibbonClient客户端启动
浏览器上执行：
$ curl http://localhost:8888/hi
Greetings, Artaban!

$ curl http://localhost:8888/hi?name=Orontes
Salutations, Orontes!