
# 平台组件生态圈
在模式驱动的组件设计之上，实现Cloud平台组件生态圈、结合运行态、开发态（Pagebuilder），全部实现自动化

前端开发工程化
-----------
前端工程化的主要目标是解放生产力、提高生产效率。通过制定一系列的 [规范]()，借助 [工具和框架]() 解决前端开发以及前后端协作开发过程中的痛点和难点问。规范为蓝本，以工具实现为媒介，其最终目的是为了提高研发效率以及保证Web产品的线上质量

前端工程化规范的实现的设计理念
-----------
到目前为止，在软件开发领域，**测试驱动的设计** 是一种很常见且被广泛接受的开发方式，在动手编写具体代码之前，先写好一套测试用例，用来描述该代码应该完成什么样的功能。**模式驱动的设计** 理念跟测试驱动的设计是相似的，区别在于后者使用测试用例来描述正确的功能，前者使用JSON来创建模式

#### 使用模式驱动理念设计的前端开发规范
在项目中使用单独的.json文件统一描述前端开发的规范，使用本地工具(CLI、Shell)基于.json文件中的描述把复杂的需要人工操作流程封装进标准化方案，在服务端使用自动构建工具(Gitlab、Jenkins)提取.json文件中标准化功能的描述，触发标准流程

被纳入规范化的功能主要分为两大部分：
* 工程化目标导向（在此为实现平台组件生态圈）
* 项目开发的诟病（i.e：CSS、版本升级带来的BUG）

在模式驱动实现的规范之上的工具链（组件标准化）
-----------
#### 文档
* 自组织／分布式 的文档开发模式
* 提供搜索功能，结合 builder.json 提取文档相关配置，搜索时进行整合从 Gitlab 上提取 README.md

#### 组件版本更新扫描
* 结合 builder.json 解决组件 依赖／扩展 后，版本更新带来的破坏性更新不可见

#### 自动化测
* 单元测试

#### 组件回归自动化
* 实现平台吸收业务的组件功能，（命令的方式）

#### CSS开发规范
* 命名规范
* 样式扩展规范

#### 组件联动设计规范
* Pagebuilder事件配置的元数据获取

#### 开发态
* 提供开发态组、运行态组件
* 联动配置也在组件中定义，Pagebuier提取事件的元数据描述，初始化事件配置功能

生态中的组件维护方式
-----------
#### Pull Request
* 自动化测试（单元测试）
* 变更记录

运行态解析器
-----------
#### 支持React
* [React Slot](https://www.npmjs.com/package/react-slot)

#### 事件联动的标准接口
* 输入、输出

Pagebuilder
-----------
#### 注册方案
* 替换掉之前的组件注册方案

#### 事件配置
* Pagebuilder支持事件的配置
> i.e 配置事件属性组件，可配置组合面板中的组件事件，元数据从组件中获取

CI构建
-----------
#### 自定义构建流程
* [Gitlab CI](https://about.gitlab.com/features/gitlab-ci-cd/)

#### 灰度

动态打包机制
-----------
#### 中间层
* 和目前的静态打包不同，动态打包通过元数据动态拼装多个组件输出到前端

#### 前端模块
* 结合业界现有技术（直接使用或二次封装），提供动态获取组件的 “loader模块”，或通过 “Webpack插件 + babel（AST）” 技术动态替换模块引用策略
