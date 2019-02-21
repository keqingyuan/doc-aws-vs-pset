
## 持续交付

| AWS | PEST |
| :--- | :--- |
| [AWS Pipeline](aws-pipeline.md)支持自动交付能力，交付虽然和部署都是把应用部署到目标服务器，不同的是交付需要开发人员/经理人手动确认，而部署不需要。 | PSET有交付能力（在CMS模块），但是和持续构建（MAM）是隔离的，目前两个模块没有打通，需要线下操作。 |

# AWS
Pipeline是 [AWS CodePipeline](chapter4.7.md) 服务。点击`Pipelines`菜单后如下图所示，已经有一个预制的Pipeline，截至目前位置，读者可能已经发现AWS在每一个惨淡下面都会预置了一个项目，这都预置都是基于我们在创建项目时所选择的项目开发架构模板。  
![pipeliine](/assets/2019-02-17_165947.png)

点击Pipeline的名字，展现下图，从源码到部署一个完整的流水线。  
![pipeline](/assets/2019-02-17_170651.png)

