## 配置

| AWS | PEST |
| :--- | :--- |
| AWS的配置管理是集成到了AWS Commit或者GitHub上。方便跟踪配置文件的版本。 | PSET支持配置管理是基于CMS，可以对环境需要的配置文件统一管理，可查看更改记录，以及历史记录。 |

# AWS
在Code Commit为例子，类似GitHub我们可以在线编辑一个配置文件然后提交，这样配置文件的修改记录用户都可以跟踪到，也能够回退，在线编辑的好处是，用户发现问题后能够快速修改。
![](/assets/2019-02-22_104426.png)

#总结
1. PSET没有提供配置管理，比较AWS的配置方式，PSET可以采用可以采用这种方式，把版本管理交给专业的版本管理工具做。
2. 能提供在线编辑功能，而非用户线下编辑后再上传到服务器。
3. 笔者在体验AWS过程中 AWS 帮助文档做的很充分，在每一个菜单下面都有一个`Getting started`链接帮助小白用户入门，在很多输入项目中有一个了解更多的连接帮助用户填写。
4. AWS把应用的生命周期每一个节点做成一个独立的产品提供服务，同时也提供了all in one的产品以此满足不同用户的需求。

