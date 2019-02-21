## 测试

| AWS | PEST |
| :--- | :--- |
| AWS的测试集成到了CodeBuild，没有发现AWS有集成的测试工具。 | PSET的测试集成了Jest & Puppeteer对应用进行端到端的测试。 |

# 总结
AWS的测试管理集成到了CodeBuild中，用户可以通过自定义构建的方式来创建一个测试用例。例如，用户提交测试代码后通过自定义构建方式来构建测试代码，下图是自定义构建的界面，用户可以随意配置。
![custome-codebuild](/assets/2019-02-21_195908.png)


PSET目前提供了WEB自动化测试实现端到端的测试功能。用到的是Jest, Pupeeter。
