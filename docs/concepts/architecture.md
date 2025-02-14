---
title: 产品架构
hide_title: true
sidebar_position: 3
---

## 产品架构

---

KubeGems采用前后端分离的架构设计，后端的各组件通过Rest Api的方式对外部系统提供支持，同时在内部完成对基础设施层资源的封装。通过kubernetes 原生控制器的，可以实现底层对接不同基础设施的资源管理，包括私有云、公有云、裸金属、虚拟机和存储、网络等服务、设备。

[KubeGems API请访问](https://api.cloud.iamidata.com/)。

依托Kubernetes架构，KubeGems无底层基础设施依赖，它可以在任何遵循带有Kubernetes一致性认证的平台上运行，其中包括但不限于，原生Kubernetes、私有云平台、公有云。

:::caution 注意
为保持最佳的使用体验，KubeGems推荐在**Kubernetes 1.18以上**的版本运行。
:::

<img src="/img/docs/architecture.jpg" width="90%" align="center" />

### 组件列表


| 组件名称                | 组件说明                                                     |
| ----------------------- | ------------------------------------------------------------ |
| gems-dashbaord          | KubeGems平台的管理入口，用户管理界面，用户在上面可以完成平台支持的所有功能操作 |
| gems-service            | 后端服务，负责管理API 接口和集群内部各个模块之间通信的枢纽，以及集群安全、审计控制 |
| gems-msgbus             | 后端服务，负责处理前端对Kubernetes实时性较强的业务逻辑       |
| gems-worker             | 后端服务，负责执行系统的后台异步任务                         |
| gems-agent              | 后端服务，负责处理平台业务逻辑，直接Kubernetes API通信，并向service上报集群信息 |
| gems-controller-manager | Kubernetes控制器，负责完成Kubernetes的CRD与Webhook的处理     |
| gems-installer-manager  | Kubernetes控制器，负责完成KubeGems产品的部署与Kubernetes初始化 |
| nginx-ingress-operator  | Kubernetes控制器，负责提供KubeGems产品多租户独立网关的能力   |
| cert-manager            | Kubernetes证书管理工具，负责处理平台内TLS证书的自动管理      |
| prometheus              | 一套开源的系统监控报警框架，为KubeGems提供主机、容器、微服务等监控告警数据 |
| grafana                 | 一套开源的监控指标展示平台，，为KubeGems提供指标展示的扩展   |
| fluentd                 | 日志采集客户端，具备丰富灵活的插件配置，为KubeGems提供主机、容器的日志采集 |
| loki                    | 云原生日志分析服务，为KubeGems提供日志存储、查询和分析服务   |
| helm                    | 一种应用容器打包和部署标准，为KubeGems提供应用商店接入的能力 |
| kustomize               | 一种应用容器编排的方法，为KubeGems提供用户应用编排的能力     |
| argocd                  | 一套开源实现ci/cd流程的系统，为KubeGems提供用户CD的部署能力  |
| istio                   | 服务网格，为KubeGems提供微服务治理和流量管控的能力           |
| jaeger                  | 应用分布式链路跟踪服务，为Sidecar和应用提供数据接受的服务    |
| calico                  | Kubernetes容器组网服务，负责容器间通信和网络隔离策略管理     |
