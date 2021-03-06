#  What Is Connection Pool

```md
背景
	传统JDBC的缺点
		用户每次请求都需要向数据库获得链接
			而数据库创建连接通常需要消耗相对较大的资源，创建时间也较长。
		假设网站一天10万访问量
			数据库服务器就需要创建10万次连接
				大的浪费数据库的资源，并且极易造成数据库服务器内存溢出、拓机。
	在JDBC规范中
		应用通过驱动接口（Driver Interface）直接方法数据库的资源
		为了有效、合理地管理资源
			在应用与JDBC Driver之间，增加了连接池
优势
	资源重用
	更快的系统响应速度
	新的资源分配手段
	统一的连接管理，避免数据库连接泄漏
连接池原理
	在服务器端一次性创建多个连接
		将多个连接保存在一个连接池对象中
	当应用程序的请求需要操作数据库时，不会为请求创建新的连接
		而是直接从连接池中获得一个连接
	操作数据库结束之后，并不需要真正关闭连接，而是将连接放回到连接池中。
JDBC连接池
	在标准JDBC对应用的接口中，并没有提供资源的管理方法
		所以，缺省的资源管理由应用自己负责
	虽然在JDBC规范中，多次提及资源的关闭/回收及其他的合理运用
		但最稳妥的方式，还是为应用提供有效的管理手段。
		所以，JDBC为第三方应用服务器（Application Server）提供了一个由数据库厂家实现的管理标准接口
		连接缓冲(connection pooling)
	引入了连接池( Connection Pool )的概念 ，也就是以缓冲池的机制管理数据库的资源
```