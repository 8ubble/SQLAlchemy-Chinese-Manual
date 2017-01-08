#常见问题 / Frequently Asked Questions

这儿回答了一些大家会经常碰到的问题。

* 连接和引擎（Connections / Engines）
* 元数据和模式（MetaData / Schema）
* SQL表达式（SQL Expressions）
* ORM配置（ORM Configuration）
* 性能（Performance）
* 会话和查询（Sessions / Queries）

##连接和引擎（Connections / Engines）

- 如何配置日志记录？（How do I configure logging?
）
- 我怎样池化数据库连接？我的数据库连接池化了吗？（How do I pool database connections? Are my connections pooled?
）
- 如何将自定义连接参数传递到我的数据库API？（How do I pass custom connect arguments to my database API?
）
- 一个关于MySQL的BUG（“MySQL Server has gone away”
）
- 为什么SQLAlchemy发出这么多ROLLBACK？（Why does SQLAlchemy issue so many ROLLBACKs?
）
 - I’m on MyISAM - how do I turn it off?
 - I’m on SQL Server - how do I turn those ROLLBACKs into COMMITs?
- 我在SQLite数据库使用多个连接（通常用于测试SQL事务操作），我的测试程序不工作！（I am using multiple connections with a SQLite database (typically to test transaction operation), and my test program is not working!
）
- 我要如何在使用引擎是连接到原DBAPI连接？（How do I get at the raw DBAPI connection when using an Engine?
）
- 如何在Python多线程并发或者是os.fork()里使用引擎/连接/会话？（How do I use engines / connections / sessions with Python multiprocessing, or os.fork()?）