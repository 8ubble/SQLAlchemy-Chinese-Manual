原文传送门：[Overview-SQLAlchemy 1.1 Documentation](http://docs.sqlalchemy.org/en/latest/intro.html)

## 综述

SQLAlchemy SQL工具包和对象关系映射器是一套用于处理数据库和Python的综合工具。 它具有几个不同的功能区域，可以单独使用或组合使用。 其主要组件依赖层如下所示：
![sqla_arch_small](http://docs.sqlalchemy.org/en/latest/_images/sqla_arch_small.png)

综上所述，SQLAlchemy的两个最值得注意的前置部分是**对象关系映射器**和**SQL表达式语言**。 SQL表达式可以独立于ORM使用。 当使用ORM时，SQL Expression语言仍然是面向公众的API的一部分，因为它在对象关系配置和查询中使用。

### 文档综述

本篇分为三个部分：[SQLAlchemy ORM](http://docs.sqlalchemy.org/en/latest/orm/index.html)、[SQLAlchemy Core](http://docs.sqlalchemy.org/en/latest/core/index.html)和[Dialects](http://docs.sqlalchemy.org/en/latest/dialects/index.html)。

在[SQLAlchemy ORM](http://docs.sqlalchemy.org/en/latest/orm/index.html)中，引入了[对象关系映射器](http://docs.sqlalchemy.org/en/latest/orm/tutorial.html)并给了详细的描述。新用户应该从[对象关系教程](http://docs.sqlalchemy.org/en/latest/orm/tutorial.html)开始。如果要使用自动构建的高级SQL，以及管理Python对象，请继续阅读本教程。

在[SQLAlchemy Core](http://docs.sqlalchemy.org/en/latest/core/index.html)中，提供了SQLAlchemy的表达式语言和数据库整合集成服务的文档。 它的表达式语言是一个独立于ORM包的工具包，可用于构造可操作的SQL语句，可以通过编程来构造，修改和执行并返回指定的结果集。与ORM的以域为中心的模式相反，SQL表达式提供了以架构为中心的使用思想。这儿有一份面向新手的[构建教程](http://docs.sqlalchemy.org/en/latest/core/tutorial.html)。 SQLAlchemy引擎，连接和整合服务也在这份[SQLAlchemy Core](http://docs.sqlalchemy.org/en/latest/core/index.html)中进行了描述。

在[Dialects](http://docs.sqlalchemy.org/en/latest/dialects/index.html)中，准备了所有支持的数据库和DBAPI后端的参考文档。

### 代码示例

SQLAlchemy的分布中包括了工作代码示例（主要涉及ORM）中。 所有包括的示例应用程序的描述在[ORM示例](http://docs.sqlalchemy.org/en/latest/orm/examples.html)中。

SQLAlchemy核心结构和ORM的wiki的详细版，请移步[Theatrum Chemicum](http://www.sqlalchemy.org/trac/wiki/UsageRecipes)。

### 安装向导

#### 支持平台

SQLAlchemy已针对以下平台进行测试：

 - cPython since version 2.6, 其他2.xx series也可以
 - cPython version 3, 包括所有的3系列
 - Pypy 2.1以及更高版本

*v0.9提示*：请在Python 2.6以及更高版本使用SQLAlchemy

当前不支持的平台包括Jython和IronPython。 在过去已经对Jpython提供支持，并且在将来的版本中也会加入版本支持，（至于是啥时候）这取决于Jython（的开发）。

#### 支持的安装姿势

SQLAlchemy可通过基于[setuptools](https://pypi.python.org/pypi/setuptools/)的标准Python方法安装，通过直接引用setup.py或通过使用pip或其他与setuptools兼容的方法。

*v1.1提示*：setuptools现在所需的设置.py文件，不再支持通过distutils安装。

#### pip安装

可以用pip的时候，从Pypi下载并一步安装

> pip install SQLAlchemy

此命令将从[Python Cheese Shop](http://pypi.python.org/pypi/SQLAlchemy)下载SQLAlchemy最新*发布*版本，并将其安装到系统中。

如果要安装最新的预发布版本，例如`1.1.0b1`，pip要求使用`--pre`：

>pip install --pre SQLAlchemy

这条命令会给你安装预览版本，而不是最新的稳定版。

#### setup.py安装

除了上面那个，你也可以用setup脚本：

>python setup.py install

#### 安装C扩展

SQLAlchemy包括C扩展，为处理结果集提供额外的速度提升。 扩展在2.xx和3.xx系列的cPython上都受支持。

如果检测到适当的平台，setup.py将自动构建扩展。 如果C扩展的构建由于缺少编译器或其他问题而失败，则设置过程将输出警告消息，并在完成时重新运行不带C扩展的构建，报告最终状态。

要运行构建/安装，甚至不尝试编译C扩展，可以指定DISABLE_SQLALCHEMY_CEXT环境变量。 这种情况是用于特殊的测试环境，或者在通常的“重建”机制不能克服的兼容性/构建问题的罕见情况下：

>export DISABLE_SQLALCHEMY_CEXT=1; python setup.py install

*v1.1提示*：因为以前的--without-cextensions选项在依赖于setuptools的某些功能已经过时，所以--without-cextensions选项现在已从安装程序中删除。

#### Python3安装

SQLAlchemy直接在Python 2或Python 3上运行，无需任何调整或转换代码就可以在任何环境中安装。

#### 数据库API安装

SQLAlchemy被设计为与为特定数据库构建的[DBAPI](http://docs.sqlalchemy.org/en/latest/glossary.html#term-dbapi)实现实时操作，并且包括对最流行的数据库的支持。 [Dialects](http://docs.sqlalchemy.org/en/latest/dialects/index.html)中的各个数据库部分提供了每个数据库的可用DBAPI，包括外部链接。

#### 检查已安装的SQLAlchemy版本

本文档涵盖SQLAlchemy版本1.1。 如果你在一个已经安装了SQLAlchemy的系统上工作，请从Python提示符中检查版本，如下所示：

```
>>> import sqlalchemy
>>> sqlalchemy.__version__ # doctest: +SKIP
1.1.0
```

### v1.0迁移到v1.1

从1.0到1.1的变化之处，可以在[SQLAlchemy 1.1的新特性](http://docs.sqlalchemy.org/en/latest/changelog/migration_11.html)中找到。