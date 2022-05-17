# MyBatis初识

## MyBatis 各种各种资源地址

1. [MyBatis中文社区](https://mybatis.net.cn)
2. [Github地址](https://github.com/mybatis/mybatis-3)

## 安装

如果使用 Maven 来构建项目，则需将下面的依赖代码置于 pom.xml 文件中：

```xml
<dependency>
  <groupId>org.mybatis</groupId>
  <artifactId>mybatis</artifactId>
  <version>3.4.7-SNAPSHOT</version>
</dependency>

<dependency>
  <groupId>mysql</groupId>
  <artifactId>mysql-connector-java</artifactId>
  <version>8.0.19</version>
</dependency>
```



```java
public class Main {
    public static void main(String[] args) throws Exception {
        String resource = "mybatis-config.xml";
        InputStream inputStream = Resources.getResourceAsStream(resource);
        SqlSessionFactory sqlSessionFactory = new SqlSessionFactoryBuilder().build(inputStream);
        try (SqlSession session = sqlSessionFactory.openSession()) {
            // 你的应用逻辑代码
            BlogMapper mapper = session.getMapper(BlogMapper.class);
            mapper.selectBlog(1);
        }
    }
}
```
