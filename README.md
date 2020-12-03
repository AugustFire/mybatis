# 1.源码阅读
## 1.1日志
- log
- jdbcLogger(proxy)
```text
    ConnectionLogger(Connection.prepareStatement(..)) //打印sql
    ↓   (执行查询前 ->产生代理对象)
    PreparedStatementLogger(PreparedStatement.executeQuery(..))  //prepareStatement执行前 打印sql参数
    PreparedStatementLogger(getResultSet.getResultSet(..))
    ↓   (获取结果前产生代理对象)
    ResultSetLogger(next++)
    ResultSetLogger(total)  //打印参数total
    
```    
## 1.2 缓存
    2.1 一级缓存 SqlSession
    2.2 二级缓存 SqlSessionFactory/NameSpace
## 1.3 插件
## 1.4 数据源

# 2.设计模式
## 2.1 工厂模式  
- LogFactory
## 2.2 门面模式
- SqlSession
## 2.3 代理模式
- xxxLogger(statementLoger,ResultSetLoger...)
- methodProxy
- plugin
## 2.4 包装模式
- cacheWrapper
## 2.5 适配器模式
- log