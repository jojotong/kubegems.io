---
title: 标准格式
hide_title: true
sidebar_position: 4
---

## 格式标准

---

本页面介绍了KubeGems文档的格式标准。KubeGems 使用Markdown写作内容，并使用Vuetify构建网站。为确保文档风格一致性，我们应遵循下面这些标准。

### 不要用大写字母表示强

直接引用代码或配置文件中的值时，使用原始大小写字母，并使用反引号 `` 包裹该值。例如，应使用 `TenantResources`，而不是`Tenant Resource`或`tenant resrouce`。

如果您不是直接引用值或代码，请使用普通的写法。

### 使用尖括号作占位符

对于命令或代码示例，使用尖括号作占位符。并告诉读者占位符代表的什是么。例如：


1. 显示 pod 相关的信息：

```
kubectl describe pod <pod-name>

其中 `<pod-name>` 是您一个 Pod 的名称。
```


### 使用 加粗 强调内容

|正确做法	| 错误做法 |
| --- | ---|
|点击 **Fork**。|	点击 “Fork”。|
|选择 **Other**。|	选择 ‘Other’。|

### 使用斜体强调新术语

|正确做法	|错误做法|
|--- | --- |
|*cluster* 指的是节点的集合……	|“cluster” 指的是节点的集合……|
|这些组件构成了 *控制平面。*|	这些组件构成了 **控制平面**。|

将新术语添加至术语表，并使用`gloss`短代码。

### 使用反引号包裹文件名、目录和路径

|正确做法|	错误做法|
| --- | --- |
|打开 `foo.yaml` 文件。|	打开 foo.yaml 文件。|
|移动到 `/content/en/docs/tasks` 目录。	|移动到 /content/en/docs/tasks 目录。|
|打开 `/data/install.yaml` 文件。|	打开 /data/install.yaml 文件。|

### 使用反引号包裹行内代码和命令

|正确做法	|错误做法|
| --- | --- |
|`foo run` 命令创建了 `Deployment`。|	“foo run” 命令创建了 `Deployment`。|
|对于声明式管理，请使用 `foo apply`。|	对于声明式管理，请使用 “foo apply”。|

您希望读者执行的命令，应放到代码块中。行内代码和命令仅用于提及特定的标签、标志、值、函数、对象、变量、模块或命令。

### 使用反引号包裹对象字段名称

|正确做法	|错误做法|
| --- | --- |
|设置配置文件中 `ports` 字段的值。	|设置配置文件中 “ports” 字段的值。|
|`rule` 字段的值是一个 `Rule` 类型的对象。|	“rule” 字段的值是一个 `Rule` 类型的对象。|
