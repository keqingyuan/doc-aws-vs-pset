# AWS CodeCommit
AWS CodeCommit 是完全托管的源代码控制服务，可托管安全的 Git 存储库。它可让团队在安全且高度可扩展的生态系统中轻松协作处理代码。使用 CodeCommit，您无需运行自己的源代码控制系统，也无需担心基础设施的扩展能力。您可以使用 CodeCommit 将来自源代码的任何数据安全存储为二进制文件，而且它可以无缝兼容您现有的 Git 工具

AWS CodeCommit 是一种高度可扩展的托管型源代码控制服务，可托管私有 Git 存储库。您只需创建一个存储库来存储您的代码。没有需要预置和扩展的硬件或需要安装、配置和操作的软件。借助 AWS CodeCommit，您可以通过拉取请求、拆分和合并来协作处理代码。您可以实施默认包含代码审核和反馈的工作流程，并控制哪些人可以更改特定分支。

## 优势
#### 协作
AWS CodeCommit 专门用于协作软件开发。您可以轻松提交、分化和合并代码，从而轻松掌控团队的项目。CodeCommit 还支持拉取请求，从而提供一种请求代码审查和与协作者讨论代码的机制。您可以从 AWS 管理控制台、AWS CLI 或 AWS 软件开发工具包创建存储库，并开始使用 Git 处理存储库。
#### 加密
您可以使用 HTTPS 或 SSH（根据您的喜好）从 AWS CodeCommit 来回传输文件。您的存储库还会使用客户特定的秘钥在休息时通过 AWS Key Management Service (AWS KMS) 自动加密。
#### 访问控制
AWS CodeCommit 使用 AWS Identity and Access Management 来控制和监控谁可以访问您的数据，以及访问的方式、时间和位置。此外，CodeCommit 还可以帮助您通过 AWS CloudTrail 和 AWS CloudWatch 监控您的存储库。

#### 高可用性和持久性
AWS CodeCommit 会将您的存储库存储在 Amazon S3 和 Amazon DynamoDB 中。  您的加密数据会以冗余方式存储在多个设施上。该架构提高了存储库数据的可用性和耐用性。
无限存储库
借助 AWS CodeCommit，您可以根据需要创建任意数量的存储库，默认情况下最多可创建1000 个存储库，并且没有请求数限制。您可以存储并创建任何类型的文件版本，包括您的代码随附的镜像和库等应用程序资产。

#### 轻松访问和集成
您可以使用 AWS 管理控制台、AWS CLI 和 AWS 软件开发工具包来管理您的存储库。您还可以使用 Git 命令或 Git 图形化工具与您的存储库源文件进行交互。AWS CodeCommit 支持所有 Git 命令且兼容现有 Git 工具。您可以与您的开发环境插件或持续集成/持续交付系统集成。
通知和自定义脚本
借助 AWS CodeCommit 存储库触发器，您可以使用 Amazon Simple Notification Service (Amazon SNS) 发送通知和创建 HTTP Webhook，或调用 AWS Lambda 功能以响应所选的存储库事件。

## 定价
详情参考[定价](https://aws.amazon.com/cn/codecommit/pricing/)