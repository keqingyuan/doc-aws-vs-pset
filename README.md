# 前言

本文目的是比较AWS的DevOps服务与PSET对比。

亚马逊AWS（英语：Amazon Web Services，缩写：AWS ）是亚马逊提供的专业云计算服务，于2006年推出，以Web服务的形式向企业提供IT基础设施服务，通常称为云计算。其主要优势之一是能够以根据业务发展来扩展的较低可变成本来替代前期资本基础设施费用。 亚马逊网络服务所提供服务包括：亚马逊弹性计算网云（Amazon EC2）、亚马逊简单储存服务（Amazon S3）、亚马逊简单数据库（Amazon SimpleDB）、亚马逊简单队列服务（Amazon Simple Queue Service）以及Amazon CloudFront等。

民生银行PSET是软件工程支撑平台的缩写。是民生银行技术管理中心提供的面向行内开发人员的软件开发项目管理平台。PSET集成了工程管理、持续集成、持续交付、驾驶舱服务，对软件项目全生命周期进行管理覆盖需求、任务、源码托管、构建、测试、部署、交付、运营。

AWS共176个产品划分了开发人员工具、分析、存储等23个大类。 本文目的是与PSET提供的服务进行对比分析，因此偏重分析开发人员工具相关的产品服务。

我们会从下表展现的维度展开对比。

|  | AWS | PSET |
| :--- | :--- | :--- |
| 生命周期覆盖范围 | AWS生命周期范围覆盖项目管理、源码托管、开发、CI/CD、交付、测试、监控 | PSET生命周期覆盖项目管理、源码托管、CI/CD、交付、测试、监控 |
| 项目管理 | AWS没有自己的项目管理产品，依托于[Atlassian JIRA Software](https://www.atlassian.com/software/jira) 来管理项目 | PSET也是依托于[Atlassian JIRA Software](https://www.atlassian.com/software/jira) 跟踪问题和管理项目 |
| 源码管理 | AWS源码托管有自己的源码托管产品 [AWS CodeCommit](aws-codecommit.md) 和支持GitHub | PSET源码托管支持SVN和bitbucket |
| 开发 | AWS提供在线编辑IDE [AWS Cloud9](aws-cloud9.md) |  |
| 持续集成 |  |  |
| 持续部署 |  |  |
| 持续交付 |  |  |
| 测试管理 |  |  |
| 配置管理 |  |  |
| 介质管理 |  |  |
| 监控 |  |  |
| 运营 |  |  |

{% include "git+https://github.com/GitbookIO/documentation.git/README.md#0.0.1" %}

