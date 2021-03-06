### 服务注册中心
```
jugg-eureka-server(两台 提升高可用性)：

nohup java -Xms50m -Xmx100m -jar jugg-eureka-server-1.0.0.jar --spring.profiles.active=server1 >jugg-eureka-server1.out 2>&1 &

nohup java -Xms50m -Xmx100m -jar jugg-eureka-server-1.0.0.jar --spring.profiles.active=server2 >jugg-eureka-server2.out 2>&1 &
```

### 配置管理
```
jugg-config-server
enableEurekaClient + spring-cloud-conifg + spring-cloud-bus + kafka-binder
```

### 服务网关
```
jugg-gateway 
enableDiscoveryClient + restTemplate-ribbon + hystrix
```

### 服务提供者
```
jugg-payment 
enableDiscoveryClient
```
### Hystrix监控
```
jugg-hystrix-dashboard、jugg-hystrix-turbine
hystrix-dashboard + hystrix-turbine
```
### 服务链接跟踪
```
jugg-zipkin-server
sleuth + zikpin + mysql + kafka
```
