## 开发

| AWS | PEST |
| :--- | :--- |
| AWS提供在线编辑IDE [AWS Cloud9](aws-cloud9.md)，同时以插件的形式支持其它的IDE。 | PSET暂时不支持IDE。|

# AWS
CodeStar不仅支持自家的 [AWS Cloud9](chapter4.3.md)，同时支持Eclipse、IntelliJ、Visual Studio等流行的第三方IDE，第三方的IDE都是以插件为媒介的方式支持，插件安装方式都有详细的说明文档（见[AWS Cloud9](chapter4.3.md) 体验Visual Studio Code），下图是AWS能够支持的IDE。  
![ide](/assets/2019-02-17_131028.png)  

需要注意的是你的源码需要托管在AWS CodeCommit上才能使用Cloud9服务，下图在Code Star菜单栏会多一个IDE菜单。
![cloud9](/assets/2019-02-21_155206.png)

下图是Cloud9的操作界面
![ide editor](/assets/2019-02-21_155406.png)

# PSET
PSET不支持IDE，或者第三方IDE。