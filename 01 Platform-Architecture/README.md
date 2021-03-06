### 概述

本文包含对 EAD 应用设计开发平台的技术架构设计的综合阐述。包括前后端技术架构说明，平台开发使用关键编程技术和思想介绍。阐明系统完全面向数据模型的设计理念，以数据定义软件，一切皆资源，面向微服务和 API 的设计思想。

### 术语定义

#### EAD
企业云应用设计器，EAD 应用设计开发平台的核心配置模块，存储和管理配置开发的流程和数据，对引擎运行生命周期中的中间件、参数、视图和动作通用驱动和自定义驱动的调度。

#### Base
基础抽象，主要代表 EAD 平台中内置的基础抽象类数据模型或 EAD 引擎程序代码中的基础抽象类程序。

#### Sys
通用系统功能，主要代表 EAD 平台中全局通用的业务功能模块，主要包括账户、日志、工作流、通知、消息、动态、日志等通用系统模块。

#### Restful
具象状态传输，REST 通常基于使用 HTTP，URI，和 JSON、XML 以及 HTML 这些现有的广泛流行的协议和标准。资源是由URI来指定。对资源的操作包括获取、创建、修改和删除资源，操作对应 HTTP 协议提供的 GET、POST、PUT 和 DELETE 方法。通过操作资源的表现形式来操作资源。资源的表现形式则是 JSON、XML 或者 HTML，取决于读者是机器还是人，是消费 Web 服务的客户软件还是 Web 浏览器。在目前 EAD 的架构体系中，资源的主要表现形式为 JSON 对象。

#### EAD 引擎（EAD Engine）
EAD 服务端 API 引擎，基于 J2EE 软件开发平台的 Spring Cloud 框架体系构建，以 AOP 架构思想对数据持久化、视图驱动、动作驱动以及应用及资源进行管理和调度，对外统一输出基于 Restful 风格的 API，供 Rainbow 或者其它客户端程序调用和渲染。


#### Rainbow
EAD 平台前端解析引擎，基于 HTML5、CSS3 和 JavaScript 对 EAD 服务引擎提供的 Rest Service API 进行解析和渲染，动态生成 Web 用户交互界面的前端应用程序框架。 