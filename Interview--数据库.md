# Interview--数据库

精心收录整理互联网笔试面试题，以及自己发布的文章，欢迎各位star！或者关注微信公众号【1024笔记】，免费获取海量学习资源

. 作者：江夏、

. 简书：https://www.jianshu.com/u/b3263fc54bce

. 知乎：https://www.zhihu.com/people/qing-ni-chi-you-zi-96

. GitHub：https://github.com/JiangXia-1024?tab=repositories

. 博客地址：https://blog.csdn.net/qq_41153943

## 一、数据库
# 笔试面试题集锦

### 1、**数据库的三大范式**

**1 、第一范式（1NF）**

在任何一个关系数据库中，第一范式（1NF）是对关系模式的基本要求，不满足第一范式（1NF）的数据库就不是关系数据库。 

所谓第一范式（1NF）是指数据库表的每一列都是不可分割的基本数据项，同一列中不能有多个值，即实体中的某个属性不能有多个值或者不能有重复的属性。如果出现重复的属性，就可能需要定义一个新的实体，新的实体由重复的属性构成，新实体与原实体之间为一对多关系。

在第一范式（1NF）中表的每一行只包含一个实例的信息。简而言之，第一范式要求数据表中的每一列（每个字段）必须是不可拆分的最小单元。

**2、 第二范式（2NF）**

第二范式（2NF）是在第一范式（1NF）的基础上建立起来的，即满足第二范式（2NF）必须先满足第一范式（1NF）。第二范式（2NF）要求数据库表中的每个实例或行必须可以被惟一地区分。为实现区分通常需要为表加上一个列，以存储各个实例的惟一标识。

第二范式（2NF）要求实体的属性完全依赖于主关键字。所谓完全依赖是指不能存在仅依赖主关键字一部分的属性，如果存在，那么这个属性和主关键字的这一部分应该分离出来形成一个新的实体，新实体与原实体之间是一对多的关系。为实现区分通常需要为表加上一个列，以存储各个实例的惟一标识。简而言之，第二范式要求表中的所有列，都必须依赖于主键，而不能有任何一列与主键没有关系。

**3 、第三范式（3NF）** 

满足第三范式（3NF）必须先满足第二范式（2NF）。第三范式（3NF）要求一个数据库表中不包含其它表中已包含的非主关键字信息。简而言之，第三范式要求表中的每一列只与主键直接相关而不是间接相关，表中的每一列只能依赖于主键。

### 2、**msyql优化方式**

1、对查询进行优化，应尽量避免全表扫描，首先应考虑在 where 及 order by 涉及的列上建立索引。

2、应尽量避免在 where 子句中使用!=或<>操作符，否则引擎将放弃使用索引而进行全表扫描。

3、尽量使用数字型字段，若只含数值信息的字段尽量不要设计为字符型，这会降低查询和连接的性能，并会增加存储开销。这是因为引擎在处理查询和连接时会逐个比较字符串中每一个字符，而对于数字型而言只需要比较一次就够了。

4、任何地方都不要使用 select * from t ，用具体的字段列表代替“*”，不要返回用不到的任何字段。

5、避免频繁创建和删除临时表，以减少系统表资源的消耗。

