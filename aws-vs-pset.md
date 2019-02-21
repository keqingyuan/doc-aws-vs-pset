# AWS VS. PSET

我们会从下表展现的维度展开对比。

|  | AWS | PSET |
| :--- | :--- | :--- |
| 生命周期覆盖范围 | ![yes](/assets/yes.svg) | ![yes](/assets/yes.svg) |
| 项目管理 | ![yes](/assets/yes.svg) | ![yes](/assets/yes.svg) |
| 源码管理 | ![yes](/assets/yes.svg) | ![yes](/assets/yes.svg) |
| 开发IDE | ![yes](/assets/yes.svg) | ![no](/assets/no.svg) |
| 持续集成 | ![yes](/assets/yes.svg) | ![yes](/assets/yes.svg) |
| 持续部署 | ![yes](/assets/yes.svg) | ![yes](/assets/yes.svg) |
| 持续交付 | ![yes](/assets/yes.svg) | ![yes](/assets/yes.svg) |
| 测试 | ![yes](/assets/yes.svg) | ![yes](/assets/yes.svg) |
| 配置 | ![yes](/assets/yes.svg) | ![yes](/assets/yes.svg) |
| 监控 | ![yes](/assets/yes.svg) | ![yes](/assets/yes.svg) |
| 介质管理 | ![yes](/assets/yes.svg) | ![yes](/assets/yes.svg) |











## 测试

| AWS | PEST |
| :--- | :--- |
| AWS的测试集成到了CodeBuild，没有发现AWS有集成的测试工具。 | PSET的测试集成了Jest & Puppeteer对应用进行端到端的测试。 |

## 配置

| AWS | PEST |
| :--- | :--- |
| AWS CodeBuild 可以执行的具体命令，例如安装构建工具包、运行单元测试和打包代码等。构建规范是一个 YAML 文件，让您能够选择要在每个构建阶段运行的命令以及选择其他设置。CodeBuild 可以使用适用于常见场景（例如使用 Apache Maven、Gradle 或 npm 的构建任务）。 | PSET支持配置管理是基于CMS，可以对环境需要的配置文件统一管理，可查看更改记录，以及历史记录。 |

## 监控

| AWS | PEST |
| :--- | :--- |
| [Amazon CloudWatch](amazon-cloudwatch.md) 是AWS提供的监控服务，该服务集成到了[AWS CodeBuild](aws-codebuild.md)里，在 Code Build控制台可以看到构建任务的指标，以及构建日志信息。 | PSET的监控分两部分一个是Monitor对PSET各个模块本身的监控，一个是集成到了MAM能够监控构建日志信息，和应用构建的健康状况、构建数量等指标。 |

## 介质管理

| AWS | PEST |
| :--- | :--- |
| AWS支持公共 Docker Hub 存储库、 Amazon EC2 Container Registry \(Amazon ECR\) | PSET集成的MAM模块集成了应用的介质管理能力，没每次构建的应用包都在构建历史获取到，Docker镜像管理依托Docker Trusted Registry\(DTR\)。 |

以上是AWS和PSET的对比分析。笔者深刻体会到AWS有两点是PSET欠缺的，一是AWS把应用的生命周期每一个节点做成一个独立的产品提供服务，同时也提供了all in one的产品 [AWS CodeStar]() ,满足不同用户的需求；二是 AWS 帮助文档做的很充分（全球服务对中文支持不是太友好，笔者是在 AWS 全球服务体验的），在每一个菜单下面都有一个`Getting started`链接帮助小白用户入门。

