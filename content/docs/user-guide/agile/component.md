﻿+++
title = "模块管理"
description = "根据项目需求，可以分拆为多个模块，每个模块可以进行负责人划分，配置后可以将项目中的问题归类到对应的模块中。例如“后端任务”，“基础架构”等等"
weight = 5
+++

# 模块管理

模块是项目的一部分，通过模块可以将项目的问题分成比史诗更小的一部分，但是模块是独立于史诗存在的，可以跨域多个版本和史诗，每一个模块都可以划分对应的负责人，在配置后，可以将项目中的问题归类到对应的模块中，比如将一个开发项目分为前端模块和后端模块。

- **菜单层次**：项目层
- **菜单路径**：敏捷管理>模块管理
- **默认角色**：项目成员

## 创建模块

![enter description here](/docs/user-guide/agile/imge/image32.png)

1.点击页面上方`创建模块`按钮，右侧会滑出创建模块的页面，输入模块名称（必输）、负责人（必输）、模块描述（可选）、默认经办人（必输），点击`确定`即可创建一个新的模块。

2.可以看到项目下所有的模块展示列表，用户可在右上角自行配置勾选列表所要显示的字段，列表展示字段如下：

- `模块`：模块名称

- `问题`： 当前模块所关联的问题数量

- `负责人`： 默认负责人工号+姓名

- `模块描述`： 模块的描述  

- `默认经办人`： 系统默认初始化一个经办人——即模块负责人

3.快速搜索，单击标识右侧可输入关键字对模块进行检索。

## 编辑模块
 在模块右边点击![enter description here](/docs/user-guide/agile/imge/image4.png "image4")的标识可对模块详细信息进行编辑

## 删除模块 
模块右边点击![enter description here](/docs/user-guide/agile/imge/image5.png "image5")标识可删除模块，删除模块会考虑两种情况：

- 如果模块未关联任何问题，则可以选择直接删除
- 如果模块关联了某个问题，可以选择将该问题关联到其他模块中，或者直接删除与问题的关联关系


## 更多操作

- [问题处理](../issue/manage-issue)
- [配置看板](../sprint/manage-kanban)
- [发布版本](../release)
