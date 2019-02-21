## 项目管理

| AWS | PEST |
| :--- | :--- |
| AWS没有自己的项目管理产品，依托于[Atlassian JIRA Software](https://www.atlassian.com/software/jira) 来管理项目。 | PSET也是依托于[Atlassian JIRA Software](https://www.atlassian.com/software/jira) 跟踪问题和管理项目。 |


#### 选择项目开发架构模板

直接上图，清晰明了，从图中可以清晰看出CodeStar根据应用种类、开发语言和AWS服务划分了很多应用模板。
![项目开发架构模板](/assets/2019-02-17_115738.png)

#### 源码托管存储库

选择应用模板后，需要用户选择源码托管位置，我们可以选择 [AWS CodeCommit](chapter4.5.md) 或者 GitHub 来托管源码。  
![源码托管存储库](/assets/2019-02-17_120103.png)

#### ooh, 一个项目建好了

下图所示，就是利用CodeStar创建项目后的一个控制面板界面，目前仅支持英文、日文、韩文、中文。
![CodeStar控制面板](/assets/2019-02-17_124608.png)