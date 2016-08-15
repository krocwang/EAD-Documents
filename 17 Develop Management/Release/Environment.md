## 各环境发布范围建议

### 开发环境

开发者直接使用开发环境的开发者中心进行配置开发，正常情况下无需在开发环境进行 EAD 配置数据和系统及应用数据的发布。

开发者通过本地 IDE 开发完成的 Java 代码通过 Maven 打包开发环境版本的 ```war``` 文件包在开发环境替换后重启 Tomcat 进行发布。

### 测试（UAT）环境

测试环境初始化完成后一般情况下通过脚本（SQL）导出相关主题域下的 EAD 配置数据，进行配置数据全量替换发布。

测试环境初始化完成后系统或应用数据模型实体（数据库表）发生新增时，只选择新增的模型实体导出后在测试环境进行导入。如果系统或应用数据模型实体发生变更时，需要手动在测试环境对相关的数据库表字段进行更新。

开发者通过本地 IDE 开发完成的 Java 代码通过 Maven 打包测试环境版本的 ```war``` 文件包在测试环境替换后重启 Tomcat 进行发布。

测试环境用户和组织机构数据与开发环境不一致时需要在完成发布后在测试环境开发者中心进行相关角色资源分配和用户角色授权。测试环境的开发者中心建议只开通发布负责人的相关权限，除了资源分配和用户角色授权外，不建议在测试环境开发者中心直接进行配置开发。

### 生产环境

生产环境的发布范围与测试环境基本一致。

如果生产环境的用户和组织机构数据与测试环境能够保持完全一致，建议无需在生产环境发布和开启开发者中心应用，禁止开发者在生产环境进行任何形式的配置开发，可以尽可能保障所有功能变更都在开发环境或测试环境进行，最大程度保证开发和测试流程。
