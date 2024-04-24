# 子表格

## 介绍

子表格适用于处理对多的关系字段，支持批量新建数据关联或从已有数据选择关联，以表格形式展示多条关联数据，提高了关联数据的管理效率。
## 使用说明

![20240410151306](https://nocobase-docs.oss-cn-beijing.aliyuncs.com/20240410151306.png)

子表格中不同类型的字段显示不同字段组件，大字段（富文本，Json,多行文本等字段）则通过悬浮弹窗编辑。

![20240410154316](https://nocobase-docs.oss-cn-beijing.aliyuncs.com/20240410154316.png)

子表格中的关系字段。

订单 （一对多）> 商品（一对多） > 库存。

![20240410152232](https://nocobase-docs.oss-cn-beijing.aliyuncs.com/20240410152232.png)

关系字段组件默认是下拉选择器（支持数据选择器/子表单（弹窗））。

![20240410152847](https://nocobase-docs.oss-cn-beijing.aliyuncs.com/20240410152847.png)

支持拖拽排序。

![20240422215629](https://nocobase-docs.oss-cn-beijing.aliyuncs.com/20240422215629.gif)
## 字段配置项

### 允许选择已有数据（默认不开启）

支持从已有数据选择关联。

![20240410160432](https://nocobase-docs.oss-cn-beijing.aliyuncs.com/20240410160432.png)

![20240410160714](https://nocobase-docs.oss-cn-beijing.aliyuncs.com/20240410160714.png)