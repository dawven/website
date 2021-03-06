﻿+++
title = "容器管理"
description = "便于您查看和管理系统中的容器化实例，可以实时查看相关 pod 的状态以确定应用是否正常运行，同时可以查看对应的 pod日志进行错误定位和状态监控"
weight = 7
+++


# 容器管理

容器的含义为每个容器中都运行一个应用并为该应用提供完整的运行环境。

**容器管理**便于您查看和管理系统中的容器化实例，可以实时查看相关 Pod 的状态以确定应用是否正常运行，同时可以查看对应的 Pod 日志进行错误定位和状态监控。

  - **菜单层次**：项目层
  - **菜单路径**：部署流水线 > 容器
  - **默认角色**：项目所有者、项目成员、部署管理员

## 查看容器管理详情

 1. 进入容器界面，通过列表信息观察应用状态、可用情况、创建时间；

 1. 点击`容器日志`→ ![容器日志按钮](/docs/user-guide/deployment-pipeline/image/container_log_button.png) 查看容器日志。

列表信息

 - 状态：容器的状态分为以下五种，分别为 Pending、Running、Succeeded、Failed 和 Unknown。

    1）Pending：Kubernetes 已经开始创建容器，但是容器中的一个或多个容器还没有被启动。比如容器正处在应该被分配到哪个节点上这个调度过程中，或者 Kubernetes 还在从镜像仓库中下载容器中容器镜像这个下载过程中。

    2）Running：Kubernetes 已经将容器分配到节点上，并且容器中的所有容器都启动了。还包括容器中至少有一个容器仍然在运行状态，或者正在重新启动状态。

    3）Succeeded：容器中的所有容器都处在终止状态，并且这些容器是自主正常退出到终止状态的，也就是退出代码为0，而且 Kubernetes 也没有重启任何容器。

    4）Failed：容器中的所有容器都处在终止状态，并且至少有一个容器不是正常终止的，也就是退出代码不为0，或者是由于系统强行终止的。

    5）Unknown：由于一些特殊情况无法获取容器状态，比如由于网络原因无法同容器所在的主机通讯。

 - 容器名称：容器的名称。
 - 应用：容器中的应用。
 - 容器地址：容器的地址。
 - 已创建：容器创建的时间。