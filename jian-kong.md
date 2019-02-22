## 监控

| AWS | PEST |
| :--- | :--- |
| [Amazon CloudWatch](amazon-cloudwatch.md) 是AWS提供的监控服务，该服务集成到了[AWS CodeBuild](aws-codebuild.md)里，在 Code Build控制台可以看到构建任务的指标，以及构建日志信息。 | PSET的监控分两部分一个是Monitor对PSET各个模块本身的监控，一个是集成到了MAM能够监控构建日志信息，和应用构建的健康状况、构建数量等指标。 |

# AWS
AWS的监控是AWS CloudWatch提供服务，下图是监控的控制面板，菜单栏分了CloudWatch、控制面板、警报、事件按、日志、指标四个菜单、除了CloudWatch和控制面板外每个菜单下有各自的子菜单。
![](/assets/2019-02-22_105616.png)