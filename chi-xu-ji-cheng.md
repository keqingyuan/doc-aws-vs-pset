## 持续集成

AWS CodeBuild 在预配置的构建环境中运行构建任务，此类环境中包含完成任务所需的操作系统、编程语言运行时和构建工具（例如 Apache Maven、Gradle 和 npm）。您只需指定源代码的位置并选择构建设置（例如要使用的构建环境以及要在构建过程中运行的构建命令）即可。AWS CodeBuild 会生成代码并将项目存储到 Amazon S3 存储桶中，而您也可以使用构建命令将其上传到项目存储库中。您可以使用 AWS CodePipeline、AWS 管理控制台、AWS CLI 或开发工具包来创建、管理和启动构建项目。

PSET的MAM提供了持续集成服务，用户根据自己的项目类型选择构架环境，构建环境包含了编程语言、构建工具（Maven、Gradle、Ant和npm）,和AWS CodeBuild一样指定源码位置并且选择构建环境就可以。目前PSET构建只能通过PSET控制台去操作，比较Code Build来说支持的工具单一。

| AWS | AWS | PEST |
| :--- | :--- | :--- |
| **预配置构建环境** | [AWS CodeBuild](aws-codebuild.md) 是AWS持续集成的服务，AWS提供适用于 Java、Python、Node.js、Ruby、Go、Android、.NET Core for Linux 和 Docker 的构建环境，构建环境支持比较PSET丰富。 | PSET同样支持持续构建服务在MAM模块，仅仅支持Java、Go、Android、iOS、Node.js。 |
| **自定义构建环境** | 用户可以在自己的构建环境中使用 AWS CodeBuild，例如适用于 Microsoft .NET Framework 的环境。您可以将适用于您的构建任务的运行时和工具打包到 Docker 镜像中，然后将其上传到公共 Docker Hub 存储库或 Amazon EC2 Container Registry \(Amazon ECR\) 中。创建新构建项目时，您可以指定 Docker 镜像的位置，而 CodeBuild 会提取这一镜像，并将其用作构建项目的配置。AWS支持的镜像请参照[这里](https://docs.aws.amazon.com/zh_cn/codebuild/latest/userguide/build-env-ref-available.html) | PSET可以通过Ant或者Shell脚本来提供支持，同时也支持Docker构建，用户可以把完整的运行环境打包到Docker镜像里，然后发布到民生DTR（目前仅支持民生DTR）。和PSET不同的是Code Build可以在创建项目时指定Docker镜像的位置，而PSET仅仅支持从源码开始的构建，PSET会提取源码来构建程序包然后打入到镜像镜像里。PSET支持的镜像有限，目前仅支持SUSE12、SUSE13、weblogic等。 |
| **指定构建命令** | 您可以定义想要 AWS CodeBuild 执行的具体命令，例如安装构建工具包、运行单元测试和打包代码等。构建规范是一个 YAML 文件，让您能够选择要在每个构建阶段运行的命令以及选择其他设置。CodeBuild 可以使用适用于常见场景（例如使用 Apache Maven、Gradle 或 npm 的构建任务）的构建规范示例文件帮助您快速入门。 | PSET在特定的构建环境中支持用户指定的构架命令，目前支持Maven、npm构建工具能够支持用户指定构建命令。 |
| **选择计算类型** | 您可以选择最能满足开发需求的计算类型。您可以从三种级别的计算容量中进行选择，每种级别都有不同的 CPU 和内存容量。这样，如果您想更快完成构建任务，就可以选择较高的 CPU 和内存计算容量；如果您的构建任务只需最低级别的 CPU 和内存容量就能完成，您可以选择较低的计算容量。  CodeBuild 支持 Linux 和 Windows 操作系统。 | PSET暂不支持选择计算类型。 |
| **选择源集成** | 您可以通过多种方式使用 AWS CodeBuild 启动构建任务。例如，您可以在连接到 AWS CodeCommit、GitHub、GitHub Enterprise、Bitbucket 或 Amazon S3 之后，在 CodeBuild 中启动构建任务。您还可以使用 AWS CodePipeline 将 CodeBuild 与您的源存储库连接到一起，而 AWS CodePipeline 会在您每次提交更改时自动启动构建任务。 | PSET在创建构建时需要指定源码库源连接到PSET上，在每次启动构建时MAM会到源码库拉取源码来构建应用，目前PSET仅支持SVN和bitbucket。 |

# AWS
笔者在CodeStar创建一个构建非常快速和边界，就两个步骤选择项目模板、选择源码托管存储一个最基本的项目创建完成。  
![创建流程](/assets/2019-02-17_122412.png)

下面随着笔者体验下在AWS创建一个构建的速度。
#### 选择项目开发架构模板

直接上图，清晰明了，从图中可以清晰看出CodeStar根据应用种类、开发语言和AWS服务划分了很多应用模板。
![项目开发架构模板](/assets/2019-02-17_115738.png)

#### 源码托管存储库

选择应用模板后，需要用户选择源码托管位置，我们可以选择 [AWS CodeCommit](chapter4.5.md) 或者 GitHub 来托管源码。  
![源码托管存储库](/assets/2019-02-17_120103.png)

#### ooh, 一个项目建好了

下图所示，就是利用CodeStar创建项目后的一个控制面板界面，目前仅支持英文、日文、韩文。
![CodeStar控制面板](/assets/2019-02-17_124608.png)

# 总结
1. PSET的预置构建环境相比AWS要少。
2. PSET项目模板用户创建一个持续集成需要填写很多信息，而且PSET创建一个新项目并不具备“落地”的能立。在AWS上用户选择好开发架构模板，并且在CodeCommit托管源码，创建好项目后用户就可以开发了。

在Dockers上