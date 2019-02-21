## 项目管理

| AWS | PEST |
| :--- | :--- |
| AWS没有自己的项目管理产品，依托于[Atlassian JIRA Software](https://www.atlassian.com/software/jira) 来管理项目。 | PSET也是依托于[Atlassian JIRA Software](https://www.atlassian.com/software/jira) 跟踪问题和管理项目。 |

# AWS

### Dashboard
AWS有一个优势就是仪表盘，通过仪表盘用户能够对整个项目有一个全局的认识，仪表盘中前两个贴图（点击Close可以关闭），第一个贴图里展现项目的状态，以及关联的IDE工具，AWS支持哪些IDE详见[开发IDE](kaifa-ide.md)。  
![CodeStar控制面板-仪表盘](/assets/2019-02-17_121934.png)  
仪表盘其它的贴图就是其它服务的入口，例如应用监控（[AWS CloudWatch](chapter18.1.md)）、[CodePipeline](chapter4.7.md)、托管工具，通过`Add tile`添加其它的服务入口，例如：Jira、持续部署等服务。

### Projects
左边菜单栏最后一个`Project`菜单是项目自身的一个信息展现入口，这里你可以看到项目用到的其它资源，以及删除项目自身操作。  
![projects](/assets/2019-02-17_175614.png)


#### 团队

在这里，您可以轻松管理项目所有者、参与者和观察者的访问权限，而无需针对每项服务手动配置策略。AWS CodeStar 通过提供符合 AWS Identity and Access Management 最佳实践的基于角色的内置策略，为团队简化了设置项目访问权限的过程。  
![team](/assets/2019-02-17_173652.png)

#### 扩展
查看你的项目使用到了那些插件，笔者的项目托管在GitHub上，所以有GitHub插件，Jira插件时项目管理需要使用，在这里可以控制第三发方服务是否显示在Dashboard。  
![extensions](/assets/2019-02-17_173911.png)

# 总结
PSET集成了许多模块和服务，但是没有一个类似Dashboard这样的界面，帮助用户快速获取必要信息的能力。
