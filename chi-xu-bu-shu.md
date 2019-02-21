
## 持续部署
AWS的[AWS CodeDeploy](aws-codedeploy.md)提供持续部署服务 , AWS的持续部署有部署组的概念和回滚策略支持自动回滚。虽然PSET支持自动部署（同样在MAM模块）同时也支持多节点部署但是缺少不同环境件同时部署的服务。同样地，如果部署异常需要手动回滚不具备回滚策略，具体的对比分析看下表。

| | AWS | PEST |
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