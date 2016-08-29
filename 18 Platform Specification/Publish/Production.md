## 生产环境发布

生产环境只能进行真实业务场景的业务运行，为了确保生产环境的安全和稳定，生产环境应该指定专门的平台管理员进行生产环境发布。

生产环境发布的版本必须在测试环境进行充分测试后才可以申请进行生产环境发布,生产环境发布时 EAD 配置开发数据以测试环境经过测试的版本为准，生产环境发布的程序也必须是测试环境通过测试的版本所对应的生产环境程序包。

### 发布申请

开发负责人提前 6 个工作日向 EAD 平台管理员提交应用发布申请，应该包括发布方式，是否启停服务，计划开始发布时间，计划结束发布时间，发布功能列表、发布注意事项等内容。

一般建议发布时间选定为生产环境较少被访问的时间段（例如：20：00 至次日 5：00），建议发布计划时长不少于 3 个小时。

平台管理员根据平台应用使用情况确认最终发布计划后，提前 5 个工作日提交发布公告申请。

开发负责人在发起前一个工作日按照安装发布手册将生产环境程序包、EAD 配置数据导入脚本、数据表表结构更新脚本、数据更新脚本、本次发布操作流程说明等发布内容提交平台管理员。

### 发布流程

#### 整体发布流程

0. EAD 应用在开发环境开发完成后，首先发布测试环境进行充分测试并通过后进行生产环境基线版本打包；
- 按照发布申请计划开始发布时间停止 EAD 服务;
- 分别备份生产环境程序包和 EAD 配置数据库，如果有业务数据表结构需要更新还需要备份需要更新的数据表结构及数据;
- 执行 EAD 配置数据导入脚本，如果有业务数据表结构需要更新执行相关脚本;
- 部署 EAD 应用程序包;
- 启动 Tomcat 服务，检查服务启动是否成功；
- 访问生产环境系统基本功能及新发布功能是否正常，如果发布正常通知相关用户；
- 系统功能或新发布功能不可用且无法在计划发布结束时间内修复，恢复已备份程序和数据后运行服务，通知相关用户发布失败并取消本次发布；

#### 增量程序发布流程

0. 按照发布申请计划开始发布时间停止 EAD 服务;
- 分别备份生产环境程序包，如果有业务数据表结构需要更新还需要备份需要更新的数据表结构及数据;
- 部署 EAD 应用程序包;
- 启动 Tomcat 服务，检查服务启动是否成功；
- 访问生产环境系统基本功能及新发布功能是否正常，如果发布正常通知相关用户；
- 系统功能或新发布功能不可用且无法在计划发布结束时间内修复，恢复已备份程序和数据后运行服务，通知相关用户发布失败并取消本次发布；


#### 配置数据发布流程

0. 按照发布申请计划开始发布时间停止 EAD 服务;
- 分别备份EAD 配置数据库，如果有业务数据表结构需要更新还需要备份需要更新的数据表结构及数据;
- 执行 EAD 配置数据导入脚本，如果有业务数据表结构需要更新执行相关脚本;
- 启动 Tomcat 服务，检查服务启动是否成功；
- 访问生产环境系统基本功能及新发布功能是否正常，如果发布正常通知相关用户；
- 系统功能或新发布功能不可用且无法在计划发布结束时间内修复，恢复已备份程序和数据后运行服务，通知相关用户发布失败并取消本次发布；