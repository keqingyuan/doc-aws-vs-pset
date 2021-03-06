## 介质管理

| AWS | PEST |
| :--- | :--- |
| AWS支持公共 Docker Hub 存储库、 Amazon EC2 Container Registry \(Amazon ECR\) | PSET集成的MAM模块集成了应用的介质管理能力，没每次构建的应用包都在构建历史获取到，Docker镜像管理依托Docker Trusted Registry\(DTR\)。 |

# AWS
AWS的介质管理是(Amazon S3)[]提供服务，下图是S3的一个控制界面
![s3](/assets/2019-02-21_204020.png)
介质管理库的安全是重中之重，用户可以修改你的介质库的公有访问级别。
![access](/assets/2019-02-21_204337.png)
下面我们来创建一个存储桶

第一步填写名称和区域，也可以从现有的复制过来。
![](/assets/2019-02-21_204605.png)

第二步配置选项，在每一个项目里可以通过了解更多去学习怎么填写。
![](/assets/2019-02-21_205016.png)
`版本控制`允许您在一个存储桶中保留多个版本的对象。本节介绍如何在存储桶上启用对象版本控制。

`服务器访问日志记录`详细地记录对存储桶提出的各种请求。对于许多应用程序而言，服务器访问日志很有用。例如，访问日志信息可能在安全和访问权限审核方面很有用。它还可以帮助您了解您的客户群并了解您的 Amazon S3 账单。

`标签`要跟踪单个项目或项目组的存储成本或其他标准，请使用成本分配标签标记您的 Amazon S3 存储桶。成本分配标签是与 S3 存储桶相关联的键-值对。在激活成本分配标签后，AWS 将使用这些标签在成本分配报告上组织您的资源成本。成本分配标签只能用于标记存储桶。

`Amazon S3 与 AWS CloudTrail 集成`，后者是在 Amazon S3 中提供用户、角色或 AWS 服务所采取操作的记录的服务。CloudTrail 将对 Amazon S3 的 API 调用子集作为事件捕获，包括来自 Amazon S3 控制台的调用和对 Amazon S3 API 的代码调用。如果您创建跟踪，则可以使 CloudTrail 事件持续传送到 Amazon S3 存储桶（包括 Amazon S3 的事件）。如果您不配置跟踪，则仍可在 CloudTrail 控制台的 Event history (事件历史记录) 中查看最新事件。通过使用 CloudTrail 收集的信息，您可以确定向 Amazon S3 发出了什么请求、发出请求的 IP 地址、何人发出的请求、请求的发出时间以及其他详细信息。

`默认加密`数据保护指在数据传输 (发往和离开 Amazon S3 时) 和处于静态 (存储在 Amazon S3 数据中心的磁盘上时) 期间保护数据。可以使用 SSL 或使用客户端加密保护传输中的数据。您可以通过以下选项在 Amazon S3 中保护静态数据。

`Amazon S3 Object Lock`使您能够使用“一次写入，多次读取”(WORM) 模式存储对象。使用 S3 Object Lock，您可以在固定的时间段内或无限期地阻止删除或覆盖对象。S3 Object Lock对象锁定使您能够满足要求 WORM 存储的法规要求，或只是添加了一个额外的保护层来防止对象更改和删除。Amazon S3 Object Lock已由 Cohasset Associates 评估，可在受 SEC 17a-4、CTCC 和 FINRA 法规约束的环境中使用。

`Amazon S3 的 Amazon CloudWatch 指标`可帮助您了解和提高使用 Amazon S3 的应用程序的性能。将 CloudWatch 与 Amazon S3 结合使用的方法有两种。

存储桶的每日存储指标 ‐ 您可以使用 CloudWatch 监控bucket存储，此工具可收集来自 Amazon S3 存储的数据并将其处理为便于读取的每日指标。Amazon S3 的这些存储指标每天报告一次并提供给所有客户，无需额外费用。

请求指标 ‐ 您可以选择监控 Amazon S3 请求，以快速识别运行问题并对其采取措施。这些指标在要处理的某些延迟后每隔 1 分钟提供一次。这些 CloudWatch 指标的计费费率与 Amazon CloudWatch 自定义指标的相同。有关 CloudWatch 定价的信息，请参阅 Amazon CloudWatch 定价。要了解有关如何选择获取这些指标的更多信息，请参阅存储桶的指标配置。

启用后，将为所有对象操作报告请求指标。默认情况下，这些 1 分钟指标在 Amazon S3 存储桶级别提供。您还可以为使用共享前缀或对象标签收集的指标定义筛选条件，这样您就可以使各个指标筛选条件满足特定业务应用程序、工作流或内部组织的需求。

所有 CloudWatch 统计数据会保留十五个月，从而使您能够访问历史信息，并能够更好地了解您的 Web 应用程序或服务的运行情况。

第三步权限设置
![](/assets/2019-02-22_100731.png)

第四步审核确认
![](/assets/2019-02-22_100751.png)

# 总结
1. AWS在构架成功后默认都是压缩包的形式打包介质。AWS在会要求项目配置标准的yml文件来标记介质的位置和名称。
2. AWS提供了一套可配置的脚本，这个是PSET不具备的，一套可配置的脚本虽然提升了用户学习门槛，但是也增加了产品的通用性，下图是AWS提供的脚本示例。
![](/assets/2019-02-22_102808.png)

在buildspec.yml里会指明构建的介质压缩包类型，和介质的结果物。
![](/assets/2019-02-22_103107.png)

综上，比较AWS，PSET的介质管理稍显薄弱，PSET的介质支持WAR、jar、zip、tar.gz，但是这些都是预制的，且不可配置。用户如果要需选择性的配置介质里的内容PSET不支持。