spring.application.name=compute-service<br/>
server.port=2222<br/>
eureka.client.serviceUrl.defaultZone=http://localhost:1111/eureka/<br/>

通过spring.application.name属性，我们可以指定微服务的名称后续在调用的时候只需要使用该名称就可以进行服务的访问。<br/>

eureka.client.serviceUrl.defaultZone属性对应服务注册中心的配置内容，指定服务注册中心的位置。<br/>
使用server.port属性设置不同的端口。<br/>

注意：先启动服务端<br/>
启动该工程后，再次访问：http://localhost:1111/<br/>

--application.properties  解决:开发spring cloud的时候遇到问题，就是服务向spring eureka中注册实例的时候使用的是机器名<br/>
eureka.instance.preferIpAddress=true<br/>
eureka.instance.instance-id=${spring.cloud.client.ipAddress}:${server.port}<br/>

参考：<br/>
http://blog.didispace.com/springcloud1/<br/>
http://blog.csdn.net/minicto/article/details/53392649<br/>
https://spring.io/guides/gs/service-registration-and-discovery/<br/>
