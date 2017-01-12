# BigTable

BitTable论文学习。

1. Bigtable 不支持完整的关系数据模型；
- Bigtable 将存储的数据都视为字符串；
- Bigtable 是一个稀疏的、分布式的、持久化存储的多维度排序 Map
- Map 的索引是行关键字、列关键字以及时间戳； Map 中的每个 value 都是一个未经解析的 byte 数组。
- 表中的行关键字可以是任意的字符串