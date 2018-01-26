
# 平台组件生态圈
实现平台组件生态圈，结合运行态、开发态、实现自动化

前端开发工程化
-----------
前端工程化的主要目标是解放生产力、提高生产效率。通过制定一系列的 **规范**，借助 **工具和框架** 解决前端开发以及前后端协作开发过程中的痛点和难点问。规范为蓝本，以工具实现为媒介，其最终目的是为了提高研发效率以及保证Web产品的线上质量

工程化下规范的设计理念
-----------

到目前为止，在软件开发领域，**测试驱动的设计** 是一种很常见且被广泛接受的开发方式，在动手编写具体代码之前，先写好一套测试用例，用来描述该代码应该完成什么样的功能。**模式驱动的设计** 跟测试驱动的设计是相似的，区别在于后者使用测试用例来描述正确的功能，前者使用JSON来创建模式

#### 使用模式驱动理念设计的工程化规范
在项目中使用单独的.json文件统一描述实现开发规范所需要的 **元数据**，在本地基于 **元数据** 使用工具把复杂的人工操作流程封装进标准化功能(CLI、Shell)，在服务端使用自动构建工具(Gitlab、Jenkins)提取 **元数据** 触发标准化流程 （*[spb-builder](https://github.com/zygeilit/spb-builder)*）

#### 被纳入标准化的功能主要分为两大部分：
* 工程化目标导向（在此为实现平台组件生态圈）
* 项目开发的诟病（i.e：CSS、版本升级带来的BUG）

工程化下实现规范的本地工具链
-----------
#### 文档
* 自组织／分布式 的文档开发模式
* 提供搜索功能，结合 builder.json 提取文档相关配置，搜索时进行整合从 Gitlab 上提取 README.md

#### 组件版本更新扫描
* 结合 builder.json 解决组件 依赖／扩展 后，版本更新带来的破坏性更新不可见

#### 自动化测
* 单元测试

#### 组件更新替换
* 实现平台吸收业务的组件功能，（命令的方式）

#### CSS开发规范
* 命名规范
* 样式扩展规范

#### 组件联动设计规范
* Pagebuilder事件配置的元数据获取

#### 事件联动的标准接口
* 输入、输出

工程化下实现规范的服务端工具链
-----------
#### Gitlab Pull Request
* 自动化测试（单元测试）
* 变更记录

#### 自定义构建流程
* 拆分Jenkins构建流程，可使用模式元数据自定义构建流程，并可以加入自定义构建策略
* [Gitlab CI](https://about.gitlab.com/features/gitlab-ci-cd/)

#### 动态打包机制
* 和目前的静态打包不同，动态打包通过元数据动态拼装多个组件输出到前端
