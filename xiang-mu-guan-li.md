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

# PSET


### 源码

点击Code菜单会跳转到 [AWS CodeCommit](chapter4.5.md) 或者 GitHub。

### 构建

按下Build菜单，会跳转到 [AWS CodeBuild](chapter4.4.md) 服务。左边的菜单栏按照[源码](chapter4.5.md)、[构建](chapter4.4.md)、[部署](chapter4.6.md)、[Pipeline](chapter4.7.md)展开，每一个菜单都有一个各自的说明操`Getting started`。  
![CodeStar控制面板-构建](/assets/2019-02-17_152908.png)

**源码**

点击源码就是 [AWS CodeCommit](chapter4.5.md) 服务。如果你使用AWS CodeCommit来托管你的源码在这里你可以看到你的源码库的信息。  
![aws codecommit](/assets/2019-02-17_155625.png)

**构建**

构建是 [AWS CodeBuild](chapter4.4.md) 服务。这里可以通过应用列表看到我们创建的应用信息，同时也可以看到某个应用的详细信息和构建历史。
  
**部署**



**Pipeline**  

Pipeline是 [AWS CodePipeline](chapter4.7.md) 服务。点击`Pipelines`菜单后如下图所示，已经有一个预制的Pipeline，截至目前位置，读者可能已经发现AWS在每一个惨淡下面都会预置了一个项目，这都预置都是基于我们在创建项目时所选择的项目开发架构模板。  
![pipeliine](/assets/2019-02-17_165947.png)  
点击Pipeline的名字，展现下图，从源码到部署一个完整的流水线。  
![pipeline](/assets/2019-02-17_170651.png)

#### 团队

在这里，您可以轻松管理项目所有者、参与者和观察者的访问权限，而无需针对每项服务手动配置策略。AWS CodeStar 通过提供符合 AWS Identity and Access Management 最佳实践的基于角色的内置策略，为团队简化了设置项目访问权限的过程。  
![team](/assets/2019-02-17_173652.png)

#### 扩展

查看你的项目使用到了那些插件，笔者的项目托管在GitHub上，所以有GitHub插件，Jira插件时项目管理需要使用，详情见[源码管理](yuan-ma-guan-li.md)。  
![extensions](/assets/2019-02-17_173911.png)

### Projects

这里你可以看到项目用到的其它资源，以及删除项目操作。  
![projects](/assets/2019-02-17_175614.png)

