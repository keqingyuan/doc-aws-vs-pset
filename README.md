# 前言

本文目的是比较AWS的DevOps服务与PSET对比。

亚马逊AWS（英语：Amazon Web Services，缩写：AWS ）是亚马逊提供的专业云计算服务，于2006年推出，以Web服务的形式向企业提供IT基础设施服务，通常称为云计算。其主要优势之一是能够以根据业务发展来扩展的较低可变成本来替代前期资本基础设施费用。 亚马逊网络服务所提供服务包括：亚马逊弹性计算网云（Amazon EC2）、亚马逊简单储存服务（Amazon S3）、亚马逊简单数据库（Amazon SimpleDB）、亚马逊简单队列服务（Amazon Simple Queue Service）以及Amazon CloudFront等。

民生银行PSET是软件工程支撑平台的缩写。是民生银行技术管理中心提供的面向行内开发人员的软件开发项目管理平台。PSET集成了工程管理、持续集成、持续交付、驾驶舱服务，对软件项目全生命周期进行管理覆盖需求、任务、源码托管、构建、测试、部署、交付、运营。

AWS共176个产品划分了开发人员工具、分析、存储等23个大类。 本文目的是与PSET提供的服务进行对比分析，因此偏重分析开发人员工具相关的产品服务。

我们会从下表展现的维度展开对比。

|  | AWS | PSET |
| :--- | :--- | :--- |
| 生命周期覆盖范围 | AWS生命周期范围覆盖项目管理、源码托管、开发、CI/CD、交付、测试、监控。 | PSET生命周期覆盖项目管理、源码托管、CI/CD、交付、测试、监控。 |
| 项目管理 | AWS没有自己的项目管理产品，依托于[Atlassian JIRA Software](https://www.atlassian.com/software/jira) 来管理项目。 | PSET也是依托于[Atlassian JIRA Software](https://www.atlassian.com/software/jira) 跟踪问题和管理项目。 |
| 源码管理 | AWS源码托管有自己的源码托管产品 [AWS CodeCommit](aws-codecommit.md) 和支持GitHub。 | PSET源码托管支持SVN和bitbucket。 |
| 开发 | AWS提供在线编辑IDE [AWS Cloud9](aws-cloud9.md)，同时以插件的形式支持其它的IDE。 | PSET暂时不支持IDE。 |
| 持续集成 | [AWS CodeBuild](aws-codebuild.md) 是AWS持续集成的服务，AWS提供适用于 Java、Python、Node.js、Ruby、Go、Android、.NET Core for Linux 和 Docker 的构建环境，构建环境支持比较PSET丰富。 | PSET同样支持持续构建服务在MAM模块，仅仅支持Java、Go、Android、iOS、Node.js。 |
| 持续部署 | AWS支持持续部署服务 [AWS CodeDeploy](aws-codedeploy.md), AWS的持续部署有部署组的概念和回滚策略支持自动回滚。 | 虽然PSET支持自动部署（同样在MAM模块）同时也支持多节点部署但是缺少不同环境件同时部署的服务。同样地，如果部署异常需要手动回滚不具备回滚策略。 |
| 持续交付 | [AWS Pipeline](aws-pipeline.md)支持自动交付能力，交付虽然和部署都是把应用部署到目标服务器，不同的是交付需要开发人员/经理人手动确认，而部署不需要。 | PSET有交付能力（在CMS模块），但是和持续构建（MAM）是隔离的，目前两个模块没有打通，需要线下操作。 |
| 测试 | AWS支持 | PSET的测试集成了Jest & Puppeteer对应用进行端到端的测试。 |
| 配置 |  | PSET支持修改sql、 |
| 监控 | [Amazon CloudWatch](amazon-cloudwatch.md) 是AWS提供的监控服务，该服务集成到了[AWS CodeBuild](aws-codebuild.md)里，在 Code Build控制台可以看到构建任务的指标，以及构建日志信息。 | PSET的监控分两部分一个是Monitor对PSET各个模块本身的监控，一个是集成到了MAM能够监控构建日志信息，和应用构建的健康状况、构建数量等指标。 |
| 介质管理 | AWS | PSET集成的MAM模块集成了应用的介质管理能力，没每次构建的应用包都在构建历史获取到，Docker镜像管理依托Docker Trusted Registry\(DTR\)。 |



