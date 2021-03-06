# Effective SQL : 编写高质量SQL语句的61个有效方法
> Effective SQL : 61 Specific Ways to Write Better SQL
> 2018-11-28 By SunnyChan

* Chapter 1  [数据模型设计]
> * [1 确保所有的表都有主键]
> * [2 避免存储冗余数据]
> * [3 消除重复数据组]
> * [4 每列只存储一个属性]
> * [5 为什么存储计算列通常有害无益]
> * [6 定义外键以确保引用完整性]
> * [7 确保表间关系的合理性]
> * [8 当第三范式不够时，使用跟多范式]
> * [9 非规范化数据仓库]

* Chapter 2  [可编程性 与 索引设计]
> * [10 创建索引时空值的影响]
> * [11 最小化索引和数据扫描]
> * [12 索引不只是过滤]
> * [13 不过度使用触发器]
> * [14 使用过滤索引包含或排除数据子集]
> * [15 使用声明式约束代替编码校验]
> * [16 了解SQL方言]
> * [17 何时在索引中使用计算结果]

* Chapter 3  [当不能改变设计时]
> * [18 使用视图来简化不能更改的内容]
> * [19 使用ETL将非关系数据转换为有用的信息]
> * [20 创建汇总表并维护]
> * [21 使用 UNION 语句将非规范化数据列传行]

* Chapter 4  [过滤和查找数据]
> * [22 关系代数及其在SQL中的实现]
> * [23 查找不匹配或缺失的记录]
> * [24 何时使用CASE解决问题]
> * [25 解决多条件查询]
> * [26 如需完美匹配，先对数据进行除操作]
> * [27 按时间范围正确地过滤日期和时间的列]
> * [28 书写可参数化搜索的查询以确保引擎使用索引]
> * [29 正确地定义“左”连接的“右”侧]

* Chapter 5  [聚合]
> * [30 理解 GROUP BY 工作原理]
> * [31 简化 GROUP BY 子句]
> * [32 利用 GROUP BY 或 HAVING 解决复杂问题]
> * [33 避免使用 GROUP BY 查找最大最小值]
> * [34 使用 OUTER JOIN 时避免获取错误COUNT()]
> * [35 测试HAVING COUNT(x) < 某数时包含零值记录]
> * [36 使用 DISTINCT 获取不重复的计数]
> * [37 窗口函数]
> * [38 创建行号和排名]
> * [39 创建可移动聚合函数]

* Chapter 6  [子查询]
> * [40 何处使用子查询]
> * [41 关联和非关联子查询]
> * [42 尽可能使用公共表达式而不是子查询]
> * [43 使用连接而非子查询]

* Chapter 7  [获取与分析元数据]
> * [44 使用查询分析器](chapter/chapter-7_get_and_analysis_metadata.md)
> * [45 获取数据库元数据](chapter/chapter-7_get_and_analysis_metadata.md)
> * [46 执行计划的工作原理](chapter/chapter-7_get_and_analysis_metadata.md)

* Chapter 8  [笛卡尔积]
> * [47 生成两张表所有行的合并标示一张表中间接关联另一张表的列]
> * [48 如何以等分量排名]
> * [49 如何对表中的行匹配]
> * [50 如何列出类别与前三偏好]

* Chapter 9  [计数表]
> * [51 根据计数表内的参数生成空行]
> * [52 使用计数表和窗口函数生成序列]
> * [53 根据计数表内定义的范围生成行]
> * [54 根据计数表定义的值范围转换某个表中的值]
> * [55 使用日期表简化日期计算]
> * [56 创建某个范围内所有日期的日程表]
> * [57 使用计数表行转列]

* Chapter 10 [层次数据建模]
> * [58 邻接列表模型]
> * [59 对不常用更新的数据使用嵌套集以提升查询效率]
> * [60 使用存储路径简化设置和搜索]
> * [61 使用祖先遍历闭包做复杂搜索]

* 附录
