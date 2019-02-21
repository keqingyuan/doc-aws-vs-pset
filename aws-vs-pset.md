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











## 持续部署
AWS的[AWS CodeDeploy](aws-codedeploy.md)提供持续部署服务 , AWS的持续部署有部署组的概念和回滚策略支持自动回滚。虽然PSET支持自动部署（同样在MAM模块）同时也支持多节点部署但是缺少不同环境件同时部署的服务。同样地，如果部署异常需要手动回滚不具备回滚策略，具体的对比分析看下表。

|  | AWS | PEST |
| :--- | :--- | :--- |
| **可重复部署** | 可以重复部署不同的应用实列 | PSET也可以重复部署不同的应用实例，在部署历史就可以进行操作。 |
| **自动化实例部署** | AWS可以通过与Pipeline结合实现构建完成后自动部署。 | PSET相对AWS自动部署操作要简单许多，只需一个勾选操作就可以，在用户构建完成后就实现部署操作。 |
| **自动扩展** | CodeDeploy 与 Auto Scaling 集成。Auto Scaling 让您可以根据自己定义的条件（如流量高峰）自动扩展 EC2 容量。当新实例进入 Auto Scaling 组时，CodeDeploy 会收到通知，并且在新实例添加到 Elastic Load Balancing 负载均衡器之前，CodeDeploy 会在该新实例上自动执行应用程序部署。 | PSET不具备自动扩展功能。 |
| **滚动更新和蓝/绿更新** | AWS根据滚动策略支持滚都滚更新，需要和`部署运行状况跟踪`配合使用，AWS同时也支持蓝/绿更新，仅支持 [Amazon EC2 实例](amazon-ec2.md)、[Amazon ECS 服务](amazon-elastic-block-store.md)（EC2 和 AWS Fargate 启动类型）或 [AWS Lambda](aws-lambda.md) 的计算平台。 | 很遗憾PSET的滚动更新和蓝/绿更新没有直接支持，而是开放了可配置部署的接口来实现，用户需要添加脚本插入到部署流程中，间接的实现滚动更新或者蓝/绿部署。 |
| **部署运行状况跟踪** | 部署运行状态追踪与滚动更新共同发挥作用，可以保持应用程序在部署期间高度可用。如果部署了不良更新，有可能会发生意外停机。AWS CodeDeploy 会监控您的部署，并会在发生太多次更新失败时停止部署。 | PSET仅仅支持有限的应员部署进行状态跟踪，例如REX项目部署、weblogic部署、Tomcat部署。 |
| **停止和回滚** | 您可以使用 AWS 管理控制台、AWS CLI 或任何 AWS 开发工具包随时停止正在执行的应用程序部署。如果您在之后想要继续进行已停止的部署，则只需重新部署该版本即可。您还可以通过重新部署以前的版本来立即回滚。 | PSET不支持部署停止和回滚操作。 |
| **监控和控制** | 您可以直接通过 AWS 管理控制台、AWS CLI、开发工具包或 API 来启动、控制和监控软件部署。如果发生故障，您可以准确找到出现故障的脚本。您还可以设置推送通知，通过 Amazon Simple Notification Service 提供的 SMS 或电子邮件信息监控部署状态。 | PSET可以通过控制台的日志看到部署状态。 |
| **部署组** | 可以将一个应用程序部署到多个部署组中。部署组用于将配置与特定环境（例如转储环境或生产环境）进行匹配。您可以在转储环境中测试新版本，并在满意后将相同的代码和相同的部署说明部署到生产环境中。 | PSET没有部署组的概念 |
| **部署历史记录** | 支持 | 支持 |

## 持续交付

| AWS | PEST |
| :--- | :--- |
| [AWS Pipeline](aws-pipeline.md)支持自动交付能力，交付虽然和部署都是把应用部署到目标服务器，不同的是交付需要开发人员/经理人手动确认，而部署不需要。 | PSET有交付能力（在CMS模块），但是和持续构建（MAM）是隔离的，目前两个模块没有打通，需要线下操作。 |

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

