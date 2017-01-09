原文传送门：[Object Relational Tutorial-SQLAlchemy 1.1 Documentation](http://docs.sqlalchemy.org/en/rel_1_1/orm/tutorial.html)

## 版本检查

快速检查当前的SQLAlchemy的使用版本是不是v1.1：

```
>>> import sqlalchemy
>>> sqlalchemy.__version__ 
1.1.0
```

## 数据库连接

（教程里使用了SQLite），这儿要用[`create_engine()`](http://docs.sqlalchemy.org/en/rel_1_1/core/engines.html#sqlalchemy.create_engine)
```
>>> from sqlalchemy import create_engine
>>> engine = create_engine('sqlite:///:memory:', echo=True)
```
`echo`是用来设置SQLAlchemy日志记录的选项，它通过Python的标准日志记录模块来实现。启动之后会输出当前操作中所有用到的SQL语句，如果你觉得它很**烦**，就把它设为`False`吧。

注：本教程在官方文档上只需点击“SQL”链接（官方说为了方便初学者的学习所以就把一部分内容折叠了）即可查看正在生成的内容。

表示数据库的核心接口的[`create_engine()`](http://docs.sqlalchemy.org/en/rel_1_1/core/engines.html#sqlalchemy.create_engine)，的返回值是[`Engine`](http://docs.sqlalchemy.org/en/rel_1_1/core/connections.html#sqlalchemy.engine.Engine)的一个实例，它，通过处理正在使用的数据库和DBAPI的详细信息的方言进行调整。 在这种情况下，SQLite方言将解释Python内置`sqlite3`模块的指令。

第一次调用类似Engine.execute（）或Engine.connect（）的方法时，Engine会建立与数据库的真正的DBAPI连接，然后用于发出SQL。 当使用ORM时，我们通常不会直接使用引擎创建; 相反，它在后台由ORM使用，我们将很快看到。

## 声明一个映射
当使用ORM，配置过程开始通过描绘我们将要处理的数据库表，然后通过我们自己的将被映射到这些表的类来定义。

In modern SQLAlchemy, these two tasks are usually performed together, using a system known as Declarative, which allows us to create classes that include directives to describe the actual database table they will be mapped to.

在现代SQLAlchemy中，这两个任务通常是一起执行，使用被称为声明一个系统，它允许我们创建类，包括指令来描述它们将被映射到实际的数据库表。
## 创建模式

## 创建映射类的实例

## 创建会话

## 添加和更新对象

## 回滚

## 查询

### 常用过滤器操作符

### 返回列表和变量

### 使用文本SQL

### 统计

## 建立原型

## 使用相关对象

## 使用连接查询

### 使用其他名字

### 使用子查询

### 从子查询中选择实体数据

### 使用EXISTS

### 共同关系运算符

## 急加载

### 子查询加载

### 连接查询

### 显式加载 + 急加载

## 删除

### 删除配置 / 删除孤立级联

## 建立多对多模型

## 更多