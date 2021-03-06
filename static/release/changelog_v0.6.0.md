# Changelog

本文档记录了Choerodon 0.6.0中**微服务开发框架**、**持续交付**和**敏捷管理**等功能的增强、变更等。

## Choerodon 微服务开发框架
### [0.6.0] - 2018-06-10
### 新增

#### 0.6.0显著新增特性

- 新增`Root`管理员，可以管理平台的设置以及平台中所有组织和项目。
- 新增用户修改头像、用户名和邮箱功能，用户`个人中心`页面优化。
- 新增微服务路由管理功能，用于可视化管理微服务的后端路由。
- `LDAP` 支持自定义用户属性，增加页面测试连接和同步用户功能，目前支持`OpenLdap` 和  `Microsoft Active Directory`两种目录类型。
- 页面增加删除确认提示，降低误删几率。
- 代码库增加`circle ci`的自动化脚本。
- `认证服务`添加`redis`作为存储登录session，用于保证`认证服务`开启多实例时的用户会话。

#### 控件0.3.1

- 新增 `Select` 组件`loading` 属性，获取异步数据时，可置为`loading`状态。
- 新增 `IconSelect` 组件，下拉分页展示所有 `icon` 图标。

#### boot0.6.0

- 新增端口配置，默认`9090`。
- 新增`403`页面，`Page`组件增加`service`属性，功能同`Permission`，无权限时显示`403`页面。

#### 框架的依赖0.5.1

- 新增`choerodon-websocket-helper` 依赖，该依赖由更新自`choerodon-socket-helper`，主要提供`Websocket`的消息路由转发，实现`devops-service`与`choerodon-agent`的命令交互。
- 新增`choerodon-gitlab4j-api` 依赖，该依赖主要修改了`gitlab api` java客户端，用于支撑`gitlab-service`与`gitlab`的交互。

### 修改

#### 0.6.0显著修改特性

- 平台权限校验逻辑完善。
- 注册中心支持指定`namespace`的服务注册。
- 菜单icon替换，文字间距调整。
- 页面图标间距统一，添加提示文案，按钮操作提示文案优化。

#### 控件0.3.1

- `Collapse`组件修改 `header`上的展开和收起图标样式。
- `Modal`组件调整 `footer` 的 `button` 样式，确定按钮`loading`状态时, 取消按钮禁用。
- `Table`组件调整，组件内部所有下拉框弹出容器改变.

#### boot0.6.0

- boot 组件化，迁移至npmjs。
- 部分组件样式调整。

#### 框架的依赖0.5.1

- `choerodon-starter-tool`初始化路由信息时设置`is_built_in`为`true`，表示内置服务。
- `choerodon-starter-core`的`CustomUserDetails`添加`is_admin`字段。

### 修复

#### 0.6.0显著修复特性

- 修复组织下创建项目时，`项目编码`不是组织内唯一，而是全局唯一的问题。
- 修复新增角色分配时，会将用户已有的角色的`标签`清除的问题。
- 修复`注册中心`发送事件异常，kafka消息不带有时间戳的问题。
- 修复`manager-service`有时候权限刷新不进去的问题。
- 修复火狐浏览器下菜单配置功能无法使用的问题。
- 修复角色分配中，无法按照角色查看成员的问题。
- 移除页面中不正确的权限编码，该bug会导致页面无法按照应有的权限。
- 修复菜单配置中，一个自设目录放在另一个自设目录下时，会导致两个目录消失的问题。

#### boot0.6.0

- 修复`Permission`和`Action`组件有时无法正常工作的问题。

#### 框架的依赖0.5.1

- `choerodon-starter-mybatis-mapper`修复`selectOne`查询条件匹配到多条数据时会出现的异常。

### 删除

#### 0.6.0显著删除特性

- 页面输入框不要移除右下角角字数限制。
- 页面输入框移除自动填充。

#### boot0.6.0

- 清理冗余代码

## 持续交付
### [0.6.0] - 2018-06-10
### 新增

- 增加`发布管理`，包括`应用发布`及`应用市场`。
- 在`网络/域名管理`中增加`网络/域名状态`和`操作类型`及`状态`以便跟踪`网络/域名`的运行情况。
- 增加`容器日`志以便追踪容器运行情况。
- 在`应用部署`中增加`review`功能以便用户确认操作。
- 在配置信息处增加注释，以便用户修改`values`文件时有更好的提示。
- 在`环境流水线`中增加升级提示。
- 在`分支管理`的标记列表中增加`commit`的超链接至`gitlab`。
- 增加页面高度及表格列宽自适应，提升界面友好程度。
- 在`环境客户端`上增加资源对象一致性机制。
- 在`环境客户端`上增加消息发送失败及超时确认机制。

### 修改

#### 0.6.0显著修改特性

- 重构`应用部署`页面，移除`实例查看`功能，增加`应用实例`页面。
- 在`网络管理中`区分`自身端口`和`目标端口`。
- 改进`应用部署`方式，从纵向步骤条到横向步骤条。
- 提升实例用户体验使得更简洁直观。
- 修改三个预定义应用模板使其能顺利生成版本及部署成功。
- 改善`values`的替换方式及`yaml`主题配色使得用户体验更佳。
- 基于更规范的命名规则修改一些`API`。
- 为了修改传值模式重构`gitlab-service`。
- 优化了首次用helm部署的实例扫回机制。

### 修复

#### 0.6.0显著修复特性

- 修复`分支管理`的版本判断逻辑错误及前台提示错误。
- 修复url出现双斜杠导致代码库无法拉取。
- 修复标记列表不能分页。
- 修复`devop`s和`agent`重启后各对象状态不一致。
- 修复组织管理员不在`gitlab template group`中。
- 修复一些其他小bug。

## 敏捷管理
### [0.6.0] - 2018-06-10
### 新增

- 问题管理：`列表管理`界面，用户可以以`类型`、`编号`、`概要`、`优先级`、`状态`等维度对问题进行查询、排序。
- 问题管理：`问题详情管理`界面，用户可以在详情的描述中直接粘贴图片、动图，并支持图片的大屏查看，同时可以在详情中上传问题的文档等附件。
- 问题管理：`时间预估控制`功能，用户可以以`故事点`、`剩余时间`对问题进度进行把控管理。
- 问题管理：`问题的多维度管理`功能，用户可以以`模块`、`修复版本`、`标签`、`史诗`、`冲刺`等方式的管理功能。
- 问题管理：`多类型维度的问题管理`，包含`epic`、`story`、`task`、`bug`、`sub-task`五大类别的问题管理。
- 问题管理：`问题评论`功能，用户可以在问题详情中进行评论，便于对问题的交流讨论。
- 问题管理：`记录工作日志`功能，用户可以动态的记录问题处理的处理进度，并根据日志记录的时间对问题的剩余时间进行扣减。
- 问题管理：问题的`子任务`功能，用户可以在问题详情中`创建`、`管理子任`务，通过对`任务`的拆分，可以更细的对问题进行管理。
- 问题管理：问题的`快速创建`功能，只需要选择对应的类型，填写问题简要信息即可创建问题。
- 待办事项：`冲刺管理`，用户可以`创建`、`开启`、`关闭`一个冲刺，可以定义冲刺的`起止时间`以及`名称`等信息；可以在冲刺详情中查看当前冲刺对应人员的问题分配情况以及对应的剩余时间等。
- 待办事项：`问题编排`，用户可以通过单选和多选的拖拽方式，将工作台中的问题拖拽到所需的`史诗`或者`版本`中，也可以拖拽入某个`冲刺`中，以位置排序的方式体现优先级，也可以在界面快速创建问题。
- 待办事项：`史诗管理`，用户可以在工作台快速创建`史诗`，可以通过拖拽编排问题的`史诗`，同时可以通过`史诗`对`问题`进行筛选。
- 待办事项：`版本管理`，用户可以在工作台快速创建`版本`，可以通过拖拽编排问题的`版本`，同时可以通过`版本`对`问题`进行筛选。
- 活跃冲刺：`多看板管理`，用户可以创建多个`看板`， 不同的`看板`可以定义不同的`泳道流程`，可以将项目管理根据不同的需求拆分成多个看板流程。
- 活跃冲刺：`看板配置`，用户可以根据自身需求定义`看板流程`，`泳道状态`等等。
- 活跃冲刺：`问题筛选`，目前支持**我的问题**、**用户故事**两个维度的问题筛选。
- 活跃冲刺：`时间追踪`，用户可以在`看板`界面跟踪当前问题的处理进度以及`冲刺`的`剩余时间`。
- 活跃冲刺：`问题管理`，用户可以在`看板`对`问题`进行拖拽移动，问题的`状态`会根据操作进行对应的流转；同时支持父子任务维度的`泳道`管理。
- 发布版本：`版本管理`列表界面，用户可以在以表格形式查看管理`版本`，并可在条目的操作选项中对版本进行`编辑`、`删除`、`发布`以及`撤销发布`操作。
- 发布版本：`版本详情`界面，用户可以在详情界面汇总查看该版本下的所有`问题`，并且能够将分类查看所有的关联`问题`。
- 发布版本：`版本发布`，用户可以对一个版本进行发布，同时可以选择将未完成的问题迁移到其他未发布的版本中。
- 模块管理：`模块管理`，用户可以`创建`、`编辑`、`删除`一个模块，支持列表界面的多字段排序、筛选功能。
- 模块管理：`问题管理`，用户可以通过模版定义`问题`的`经办人`默认策略。