v1.1.0版本升级日志
=====================
发行日: 2021.11.05

洞态 IAST Server 端
------------------------
**功能**
- 组织管理中修改为``部门管理``和``用户管理``两部分
- 调整导出功能为异步
- 增加自定义规则关键字搜索功能
- Agent 自动创建项目版本

Java Agent
--------------
**功能**
- 新增 agent 启动参数：自动创建项目版本 -Dproject.version=<v1.1.0>
- 新增 agent 启动参数：配置agent获取的响应体长度 -Dresponse.length=<1000>。该功能于下个版本支持Server端配置
- Eclipse 插件已开源：https://github.com/HXSecurity/DongTai-Plugin-Eclipse

**修复**
- 修复某些 SQL 注入漏洞无法检出的bug: https://github.com/HXSecurity/DongTai/issues/253
- 修复参数导致 SSRF 误报的 bug: https://github.com/HXSecurity/DongTai/issues/134
- 修复安装探针后应用日志无法显示的 bug: https://github.com/HXSecurity/DongTai/issues/315
- 解决 attach 模式的异常报错: https://github.com/HXSecurity/DongTai/issues/321


Python Agent
---------------
**功能**
- Agent 服务端启停
- Agent 根据 CPU 阈值启停
- 使用环境变量 `AUTO_CREATE_PROJECT=1` 在首次使用 Agent 时自动创建项目
- 上报服务启动时间
- 增加 XSS 检测
- 增加 XXE 检测
- 增加 SSRF 检测

**修复**
- 修复上报数据参数 `className` 为完整的类名
- 修复上报的请求体和响应体格式
- 修复流式响应处理
- 修复响应体处理
- 修复 Django 请求表单数据处理
- 修复污点数据的 `kwargs` 参数
- 修复方法池中的无效的污点数据
- 修复无效的污点数据过滤

**构建**
- 代码提交时自动打包上传
- 代码提交时自动执行靶场测试脚本

**测试**
- 增加靶场测试脚本

PHP Agent (Beta)
--------------------
**功能**
- 检测及上传数据至洞态 IAST Server

