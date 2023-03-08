# jenkins in test environment

用于备份Jenkins配置

## 还原方式

Jenkins从备份恢复：
1. 映射JDK8和JDK11
2. 安装原环境的插件：
  - Git Parameter Plug-in
  - Maven Integration
  - Publish Over SSH
  - Fail the Build
  - NodeJS
  - Pipeline
  - Pipeline Stage view
  - Pipeline Utility Steps
3. docker-compose down, 注释掉settings.xml映射，然后docker-compose up -d
4. 执行一个job以install Maven 3.6.1
5. docker-compose down, 恢复settings.xml映射，然后docker-compose up -d

已知问题：
No Git repository configured in SCM configuration or plugin is configured wrong
解决办法：配置Default value, 跑一次就可以了。我跑一次就去掉了Default value
