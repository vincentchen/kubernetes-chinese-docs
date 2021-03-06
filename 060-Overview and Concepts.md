# Kubenetes集群管理员手册
`译者：李昂` `校对：无`


管理员手册适合于创建了或者正在管理Kubernetes集群的人。阅读管理员手册最好已经熟悉[用户手册](http://kubernetes.io/v1.0/docs/user-guide/README.html)中的一些概念。

## 规划一个集群

如何部署创建一个Kubernetes集群有很多不同的例子可以参考。很多例子都在这个[列表](http://kubernetes.io/v1.0/docs/getting-started-guides/README.html)中列出了。我们称在列表中每个组合为一个发行版。

在选择需要的手册之前，有些事情需要提前考虑：

* 你只是想在你的笔记本上试一下Kubernetes还是创建一个多节点的高可用集群？这两种模式都是支持的，但是有些发行版只适合一种情况或其他情况。
* 你是否会使用主机模式的Kubernetes集群，像是[GKE](https://cloud.google.com/container-engine)这种或是你自己启动的。
* 你的集群在机房中或者云服务器上（IaaS）吗？Kubernetes不直接支持混合集群。我们推荐建立多个集群而不是跨越遥远的地点。
* 你要在现实主机或者虚拟机上运行Kubernetes吗？Kubernetes都是支持的，请看不同的发行版。
* 你只是想要运行一个集群还是想要为Kubernetes项目做开发？如果是后者，最好选择一个其他开发者都使用的发行版。某些发行版只有二进制可执行文件但却提供了多种选择。
* 不是所有的发行版都被很好的维护着。最近版本的Kubernetes列出的一些只是为了测试。
* 如果你在机房配置Kubernetes，你需要考虑最适合的[网络模型](http://kubernetes.io/v1.0/docs/admin/networking.html)。
* 如果你正在设计高可用集群，你可以看看[运行在多个地点的集群](http://kubernetes.io/v1.0/docs/admin/multi-cluster.html)。
* 你可以运行多种[组件](http://kubernetes.io/v1.0/docs/admin/cluster-components.html)构成的集群来使你自己变成更加熟练。

## 创建一个集群

从[列表](http://kubernetes.io/v1.0/docs/getting-started-guides/README.html)中挑选一个入门手册然后按它指导。如果没有入门指南适合你，你也可以参考入门手册中的一部分指导。

一种可选的网络模型就是*OpenVSwitch GRE/VxLAN* 网络（[ovs-networking.md](http://kubernetes.io/v1.0/docs/admin/ovs-networking.html)），使用OpenVSwitch设置的网络可以使Kubernetes不同节点之间的pod通信。

如果你正在使用Salt修改已经存在指南，这篇文档会告诉你[Salt如何应用于Kubernetes项目](http://kubernetes.io/v1.0/docs/admin/salt.html)。

## 管理一个集群以及升级

[管理集群](http://kubernetes.io/v1.0/docs/admin/cluster-management.html)

## 管理节点

[管理节点](http://kubernetes.io/v1.0/docs/admin/cluster-management.html)

## 可选的集群服务

使用SkyDNS（[dns.md](http://kubernetes.io/v1.0/docs/admin/dns.html)）整合DNS：为Kubernetes服务解析DNS名字。
使用[Kibana](http://kubernetes.io/v1.0/docs/user-guide/logging.html)记录日志。

## 多租户支持

资源配额（[resource-quota.md](http://kubernetes.io/v1.0/docs/admin/resource-quota.html)）

## 安全

Kubernetes容器环境（[docs/user-guide/container-environment.md](http://kubernetes.io/v1.0/docs/user-guide/container-environment.html)）:阐述了Kubelet在管理Kubernetes节点上的容器时的环境。

安全访问API Server：[访问api](http://kubernetes.io/v1.0/docs/admin/accessing-the-api.html)

认证：[authentication](http://kubernetes.io/v1.0/docs/admin/authentication.html)

授权：[authorization](http://kubernetes.io/v1.0/docs/admin/authorization.html)

接纳控制：[admission_controllers](http://kubernetes.io/v1.0/docs/admin/admission-controllers.html)

