---
title: 快速开始
hide_title: true
sidebar_position: 1
description: 本文用于指导用户在KubeGems快速使用，并对Kubernetes相关的资源进行操作
keywords: [kubegems,KubeGems,kubernetes]
---

## 快速开始

---

### 导入集群

- 使用 `admin` 账号登录KubeGems管理后台，点击右下角 【工具箱】 图标，进入 【系统管理】

<img src="/img/docs/admin-first-login.jpg" width="100%" />

- 点击 【创建集群】，将集群的 `kubeconfig` 文件粘贴至文本框。

<img src="/img/docs/admin-first-cluster.jpg" width="100%" />

输入`集群名称`和集群容器运行时类型，勾选上 `控制集群`。

<img src="/img/docs/admin-first-import-cluster.jpg" width="100%" />

:::info 信息
控制集群不会注入 `gem-insatller-manager` 服务。
:::

- 集群导入成功，并且状态正常后，点击 【详情】进入集群信息管理页面

<img src="/img/docs/admin-first-cluster-list.jpg" width="100%" />

<img src="/img/docs/admin-first-cluster-info.jpg" width="100%" />

集群详情页包含了集群的`基本状态`、`证书信息`、`监控指标`、`物理资源`、`资源类型`以及`使用统计`等信息。

### 租户管理

- 使用 `admin` 账号登录KubeGems管理后台，点击左上角【集群资源】卡片，进入【平台管理】

<img src="/img/docs/admin-first-tenant-list.jpg" width="100%" />

- 点击租户列表右上角的 `创建租户` 按钮，创建一个名为 **demo** 的租户

<img src="/img/docs/admin-first-tenant-create.jpg" width="100%" />

- 点击 **demo**，进入租户详情页，里面可以`管理租户成员`以及`集群的资源配额管理`

<img src="/img/docs/admin-first-tenant-info.jpg" width="100%" />

- 点击 **添加集群资源**，选择`cluster-demo`集群，为 **demo** 租户分配 8Core 16G 内存和 100G 硬盘

<img src="/img/docs/admin-first-tenant-quota.jpg" width="100%" />

### 租户空间

- 点击 KubeGems 顶部栏中的【工作台】进入租户空间，并点击【用户头像】可以自由切换租户空间

<img src="/img/docs/admin-first-demo-dash.jpg" width="100%" />

- 点击 【创建项目】 为租户创建一个名为 **demo** 项目空间，并选择可以按照角色添加成员至该项目空间

<img src="/img/docs/admin-first-demo-project.jpg" width="100%" />

- 进入 **demo** 项目空间，点击右上角的【创建环境】创建一个名为 **demo-env** 的环境空间

<img src="/img/docs/admin-first-demo-env.jpg" width="100%" />

:::warning 注意
注意：环境空间的删除策略为 `仅删除关联` 和 `删除整个命名空间`，它们之间的主要区别控制删除环境时，控制器的行为。
:::

为 **demo-env** 环境创建资源配合，此处为 Kubernetes 原生的 `ResourceQuota` 资源

<img src="/img/docs/admin-first-demo-env-quota.jpg" width="100%" />

- 点击 demo-env 进入到环境空间详情页，Kubernetes 相关的资源控制均在环境空间内完成

<img src="/img/docs/admin-first-demo-env-info.jpg" width="100%" />

### 创建工作负载

#### 创建 Deployment

- 进入环境空间，点击左部侧边栏，选择【运行时】 - 【工作负载】，进入工作负载管理页面

<img src="/img/docs/admin-first-demo-env-workload.jpg" width="100%" />

- 点击右上角 【创建工作负载】，根据页面引导创建 deployment 资源

<img src="/img/docs/admin-first-demo-env-deploy-1.jpg" width="100%" />
<img src="/img/docs/admin-first-demo-env-deploy-2.jpg" width="100%" />
<img src="/img/docs/admin-first-demo-env-deploy-3.jpg" width="100%" />
<img src="/img/docs/admin-first-demo-env-deploy-4.jpg" width="100%" />
<img src="/img/docs/admin-first-demo-env-deploy-5.jpg" width="100%" />

当 `deployment` 资源创建成功后可以【工作负载】和【容器组】页面内查看创建的容器资源信息。您也可以点击相关资源进入详情页浏览资源细节。

<img src="/img/docs/admin-first-demo-env-deploy-success.jpg" width="100%" />

详情页提供的资源包含不限于：

- 工作负载基本信息
- 元数据
- 容器状态
- 事件
- 监控

更多配置请参考【运行时管理】
//TODO

#### 创建 Service

- 进入环境空间，点击左部侧边栏，选择【运行时】 - 【服务】，进入服务管理页面，根据页面引导创建 Serivce

<img src="/img/docs/admin-first-demo-env-service-1.jpg" width="100%" />
<img src="/img/docs/admin-first-demo-env-service-2.jpg" width="100%" />

更多配置请参考【运行时管理】
//TODO

#### 创建 Ingress

- 进入环境空间，点击左部侧边栏，选择【运行时】 - 【路由】，进入服务路由管理界面，根据页面引导创建 `Ingress`

<img src="/img/docs/admin-first-demo-env-ingress-1.jpg" width="100%" />

- 创建完成后点击 **demo-http** ,进入 ingress 详情页，在路由【路由规则】处，点击【访问】可以直接访问服务Web 页面

<img src="/img/docs/admin-first-demo-env-ingress-info.jpg" width="100%" />

更多设置请参考 [服务路由](/docs/tasks/user-operation/gateways/ingress)
