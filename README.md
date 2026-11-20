# 共享工业边缘服务的停线证据与抵扣分摊

本目录保存工业园内的合成业务资料。停线事故台账、探针及产线记录、绕行、维护许可、计费条款与已发账单。分钟起点与计费时区由 terms 定义。evidence.replaces 指定更正的原记录，同一凭证号之外仍可有存在冲突的独立记录。权重在同一节点内计算。金额单位为分。

数据文件位于 `data/`，采用 UTF-8 JSON。表由对象数组组成，单份配置由对象表示。字段后缀 `min`、`day`、`hour`、`cents`、`kg` 和 `m` 标记单位。未提供的事实用 `null` 表示，绝对区间右端不包含在内。名称和编号为本目录内的资料标识。

运行环境为 Python 3.11，资料检查只使用标准库。

- 查看目录与样本数量：`python3 inspect_inputs.py`
- 运行资料测试：`python3 -m unittest discover -s tests -v`
- 编译检查：`python3 -m compileall -q inspect_inputs.py tests`
