## 源码管理

| AWS | PEST |
| :--- | :--- |
| AWS源码托管有自己的源码托管产品 [AWS CodeCommit](aws-codecommit.md) 和支持GitHub。 | PSET源码托管支持SVN和bitbucket。 |

# AWS
AWS的源码管理服务由AWS CodeCommit提供，如果是选择GitHub托管源码，源码管理的服务就会移交给GitHub，如果使用AWS自家产品，AWS会根据你选择的项目模板生成一套代码原型。
下图是笔者选择了应用类型：web service, 开发语言：Java, 计算平台：AWS Lambda。
![template](/assets/2019-02-21_154544.png)
在CodeCommit生成的源码。
![code](/assets/2019-02-21_154648.png)

# 总结
PSET使用SVN和bitbucket托管源码，会在源码管理相应都移交给了SVN和bitbucket，但是对第三方服务的集成度没有AWS CodeCommit高，我们在Dashboard可以看到用户托管在GitHub上的历史信息、Issue信息，但是PSET需要登陆bitbucket。