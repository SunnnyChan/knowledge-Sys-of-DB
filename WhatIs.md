# What Is DB

1990年代开始，关系型数据库（RDBMS）成为主流。

从实际应用的角度看，有两点最受关注：
		内部以关系模型存储数据，对外支持ANSI SQL接口
		支持事务管理ACID特性，尤其是强一致性
而后出现的各种“分布式数据库”，大多都是在这两点上做权衡以交换其他方面的能力。


## Classify

架构
	Distributed DB

数据逻辑结构
	RDBMS
		MySql
	NoSQL
			Redis
			HBase
			RocksDB
			Cassandra
		比较
			HBase Vs Redis
	NewSql

数据存储结构
	行式数据库
		
			行式存储比较适合随机查询
				并且RDBMS大多提供二级索引，在整行数据的读取上，要优于列式存储。
			行式存储不适合扫描
				这意味着要查询一个范围的数据，行式存储需要扫描整个表（因为这些记录不是顺序存储的）
				，在索引建立不当的情况下，查询大表（千万数据）简直是噩梦。
			维护大量的索引和物化视图无论是在时间(处理)还是空间(存储)方面成本都很高。
	列式数据库
	内存数据库
		实现
			Oracle
				DB12c In-Memory
				TimesTen

Storage Engine
	Hash
		基于(内存中)的Hash
			支持 随机 的增删查改，读写的时间复杂度O(1)；
			无法支持顺序读写
				注，这里指典型的hash，不是指如redis的基于跳表的zset的其他功能
		基本效果
			在不需要有序遍历时，最优
		NoSQL的Redis/Memcached
	磁盘查找树
		基于(磁盘的)顺序查找树，B树/B+树；
		基本效果
			支持有序遍历
			但数据量很大后，随机读写效率低
		MySQL
	LSM Tree
		实际落地存储的数据按key划分，形成有序的不同的文件
			结合其“先内存更新后合并落盘”的机制，尽量达到磁盘的写是顺序写，尽可能减少随机写
			对于读，需合并磁盘已有历史数据和当前未落盘的驻于内存的更新，较慢
		基本效果
			也可以支持有序增删查改；写速度大幅提高；读速度稍慢；
		实现
			LevelDB
				google实现的非常高效的kv数据库
					版本1.2能够支持billion级别的数据量
					Leveldb是单进程的服务，而且它只是一个 C/C++ 编程语言的库, 不包含网络服务封装
			RocksDB

## Utility

OLTP
OLAP
	参考大数据分析
OLPP
		在线预测处理（online predictive processing，OLPP）
		将OLTP、OLAP和机器学习集成到同一个平台上
		Splice Machine
			一个OLPP平台
	场景
		客户服务呼叫中心
			通过电话、网络或移动应用等渠道，呼叫中心代理在接到订单后几秒内就对客户的查询做出响应。
		个性化
			使用机器学习模型，可以预测客户即将采取何种行动。
		预测维护
			使用机器学习模型，预测现场设备何时可能出现停机故障。
