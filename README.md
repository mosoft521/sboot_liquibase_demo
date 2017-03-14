# sboot_liquibase_demo
Spring Boot demo with embedded liquibase

liquibase的使用方式 要有dbchangelog文件 加入了liquibase的依赖后 默认就会开启sql初始化执行了。

如果启动项目的时候不需要初始化数据库脚本则添加以下配置到yml关闭即可：
```yaml
liquibase:
 enabled: true
```
由上可知 false是即可关闭，true为打开
更新脚本的master.yaml的格式是下面这样的：
```yaml
databaseChangeLog:
  - include:
      file: "db/changelog/demo/v1.0-blue.yaml"
  - include:
     file: "db/changelog/demo/v1.1-green.yaml"
```
如果需要执行初始化，则将文件配置在里面即可，不需要就把include注释掉