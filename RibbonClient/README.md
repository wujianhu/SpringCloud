Ribbon是一个基于HTTP和TCP客户端的负载均衡器。<br/>
Ribbon可以在通过客户端中配置的ribbonServerList服务端列表去轮询访问以达到均衡负载的作用。<br/>

第一种：<br/>
  1.RibbonServer一个服务端先启动<br/>
  application.yml配置文件最好放在这里，不要放在application.properties<br/>
  2.RibbonClient客户端启动<br/>
浏览器上执行：<br/>
$ curl http://localhost:8888/hi<br/>
Greetings, Artaban!<br/>

$ curl http://localhost:8888/hi?name=Orontes<br/>
Salutations, Orontes!<br/>

第二种：<br/>
  1.RibbonServer多个服务端先启动<br/>
  target目录下找到RibbonServer-0.0.1-SNAPSHOT.jar，在windows cmd窗口执行：<br/>
  java -jar RibbonServer-0.0.1-SNAPSHOT.jar   --server.port=8090<br/>
  java -jar RibbonServer-0.0.1-SNAPSHOT.jar   --server.port=9092<br/>
  java -jar RibbonServer-0.0.1-SNAPSHOT.jar   --server.port=9999<br/>
  2.新建UserApplication、SayHelloConfiguration<br/>
  3.RibbonClient客户端启动<br/>
浏览器上执行：<br/>
$ curl http://localhost:8888/hi<br/>
Greetings, Artaban!<br/>

$ curl http://localhost:8888/hi?name=Orontes<br/>
Salutations, Orontes!<br/>

参考：<br/>
https://spring.io/guides/gs/client-side-load-balancing/<br/>
