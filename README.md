
# 在模式开发的基础之上，实现Cloud平台组件生态圈、结合运行态、开发态（Pagebuilder），全部实现自动化

模式开发
-----------

组件标准化
-----------
 * 文档（搜索）
 * 版本升级扫描
 * 自动化测
   ** 单元测试
 * 组件回归自动化
 * CSS开发规范
 * 组件联动设计规范
 * 支持开发态
   ** 提供开发态组、运行态组件
   ** 联动配置也在组件中定义，Pagebuier提取事件的元数据描述，初始化事件配置功能
   ** 

组件维护
-----------
 * Pull Request
   ** 自动化测试（单元测试）
   ** 变更记录

运行态
-----------
 * 解析器支持React
   ** React组件[Slot模块](https://www.npmjs.com/package/react-slot)
 * 解析器提出组件联动的标准接口（输入、输出）

Pagebuilder
-----------
 * 注册方案
   ** 替换掉之前的组件注册方案
 * 事件配置
   ** Pagebuilder支持事件的配置
      i.e 配置事件属性组件，可配置组合面板中的组件事件，元数据从组件中获取

CI构建
-----------
 * 自定义构建流程（Gitlab-ci)
   ** https://about.gitlab.com/features/gitlab-ci-cd/
 * 灰度

动态打包机制
-----------
 * 中间层
   ** 和目前的静态打包不同，动态打包通过元数据动态拼装多个组件输出到前端
 * 前端模块
   ** 结合业界现有技术（直接使用或二次封装），提供动态获取组件的 “loader模块”，或通过 “Webpack插件 + babel（AST）” 技术动态替换模块引用策略
