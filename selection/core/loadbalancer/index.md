# 负载均衡

## 定义和做法

负载均衡就是分发请求流量到不同的服务器,

## 实现方式

### 服务器端负载均衡

服务器端负载均衡是指在服务器端架设负载均衡服务器，用户请求到中间层的负载均衡服务器,由负载均衡服务器分发控制到真实提供服务的应用服务器.

![](images/style_server.png)

重点：

1. 对客户端透明的：客户端不知道服务器端的服务列表，甚至不知道自己发送请求的目标地址存在负载均衡器
2. 服务器端维护负载均衡服务器，控制负载均衡策略和算法

目前常见的服务器端实现有:

* 软件

	- ngnix
	- apache
	- HA Proxy

* 硬件

	- F5
	- NSX
    - BigIP

### 客户端负载均衡

客户端负载均衡是指负载均衡器作为客户端软件的一部分,客户端得到可用的服务器列表然后按照特定的负载均衡策略,分发请求到不同的服务器端.

![](images/style_client.png)

重点：

1. 对客户端不透明的：客户端需要知道服务器端的服务列表，需要自行决定请求要发送的目标地址
2. 客户端维护负载均衡服务器，控制负载均衡策略和算法

目前常见的实现有:

- Netflix Ribbon
