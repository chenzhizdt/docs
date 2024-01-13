# 工作流

## 介绍

工作流插件是一个编排和配置自动化流程的强大工具，业界通常称为业务流程管理（BPM）工具。常用于基于数据模型的业务流程设计与编排，通过触发条件与执行流程节点编排实现业务流程的自动化流转。

在 NocoBase 应用中，工作流插件针对无代码场景设计，使用该插件可以在 UI 界面上完成大部分常见业务的编排与数据处理，以动态地实现系统中的业务流程变更。

每个工作流通过一个触发器与若干节点编排而成，通过每个节点的特定功能，描述系统中对应事件产生后需要处理的业务逻辑。一个典型的工作流如下图所示：

![工作流示例](./7e17ffc2-8ce2-416a-9798-0d39475d8211.png)

以上工作流的功能是：当用户提交一个订单表单后，系统自动检查订单中的商品库存，如果库存充足，则扣减库存，否则订单更新为无效。

从更通用的角度，工作流在 NocoBase 应用中可以解决几大场景的问题：

- 数据自动化处理：比如在数据表中新增一条数据后，自动按预定流程处理数据，如计算触发数据后更新关联数据等。
- 人工介入的业务流程：当业务流程不能完全自动化决策时，可以通过人工类型的节点，将部分决策权交给人工处理，比如审批、复核等。人工处理的结果提交以后，再继续执行后续流程。
- 与外部系统连接：可以通过请求节点（或扩展各类调用第三方功能的节点）调用外部系统的 API 接口，实现和外部系统的数据交互。

## 安装

工作流是 NocoBase 的内置插件，无需额外安装。

## 深入了解

- [使用手册](../manual/index/index.md)
- [开发指南](../development/index/index.md)