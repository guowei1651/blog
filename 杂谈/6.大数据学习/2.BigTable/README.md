# BigTable

BitTable论文学习。

1. Bigtable 不支持完整的关系数据模型；
- Bigtable 将存储的数据都视为字符串；
- Bigtable 是一个稀疏的、分布式的、持久化存储的多维度排序 Map
- Map 的索引是行关键字、列关键字以及时间戳； Map 中的每个 value 都是一个未经解析的 byte 数组。
- 表中的行关键字可以是任意的字符串。
- 对同一个行关键字的读或者写操作都是原子的（不管读或者写这一行里多少个不同列），这个设计决策能够使用户很容易的理解程序在对同一个行进行并发更新操作时的行为
- Bigtable 通过行关键字的字典顺序来组织数据。
- Bigtable 通过行关键字的字典顺序来组织数据。表中的每个行都可以动态分区。每个分区叫做一个"Tablet"，Tablet 是数据分布和负载均衡调整的最小单位。
- 列关键字组成的集合叫做"列族"，列族是访问控制的基本单位。
- 在 Bigtable 中，表的每一个数据项都可以包含同一份数据的不同版本；不同版本的数据通过时间戳来索引。
- Bigtable 通过两个参数可以对废弃版本的数据自动进行垃圾收集。每一个列族配有两个设置参数。
- 可以对 Bigtable 进行如下的操作：写入或者删除 Bigtable 中的值、从每个行中查找值、或者遍历表中的一个数据子集
- 