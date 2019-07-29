---
title: "F5 连接NetOps/SecOps与DevOps」 -- 「3」Cloud Templates"
date: 2019-07-29T12:12:11+08:00
draft: false
tags: ["super-netops", "f5"]
---

# 「F5 连接NetOps/SecOps与DevOps」 -- 「3」Cloud Templates

![Cloud Templates](https://ottodeng.oss-cn-shenzhen.aliyuncs.com/20.png)   

本文主要介绍的第一个F5声明式组件 -- Cloud Templates

![cd-pipeline](https://ottodeng.oss-cn-shenzhen.aliyuncs.com/19.png)   

在上一篇系列文章中有提到，在持续交付流水线中，包含部署，上线，配置，监控等环节，而第一步就是需要在不同的环境中部署对应的资源，对于很多运维人员来说，他们需要根据特定应用程序的不同配置以及云提供商之间的差异，手动地根据这些特点部署到不同的云环境中，而这些步骤，有大部分都是重复的步骤，而F5的Cloud templates正好可以解决这些不同环境差异化的问题，它主要有以下特点：

### 1. 快速、可靠   

手动配置应用程序服务耗时且容易出错；Cloud Templates可以在几分钟内部署应用程序服务，这些服务由F5专家根据云最佳实践进行设计和测试，以满足不同的架构而设计，您无需预先了解很多BIGIP关于部署方面的知识，只需要按照模板填写一些基本的信息即可。

![ct](https://ottodeng.oss-cn-shenzhen.aliyuncs.com/26.png)   

### 2. 简单、自动化   

随着基础设施复杂性的增加，对自动化和协调的需求也在增加。模板化应用程序服务可以轻松地与第三方自动化工具（如Ansible, Chef, Puppet, Terraform等）集成，以提高效率，同时降低部署的成本、可变性和风险。

### 3. 多云的通用部署

随着多云环境的需求日益增多，F5提供多个公有云和私有云的Cloud Templates，以实现跨多个云平台的应用程序服务快速简单复制。

Cloud Templates对于主流公有云的支持如下：   
![Public-templates](https://ottodeng.oss-cn-shenzhen.aliyuncs.com/21.png)   

Cloud Templates对于主流私有云的支持如下：   
![Private-templates](https://ottodeng.oss-cn-shenzhen.aliyuncs.com/22.png)   

以下是一些公有云中的参考架构（以AWS为例）：

![aws-1](https://ottodeng.oss-cn-shenzhen.aliyuncs.com/23.png)   

![aws-2](https://ottodeng.oss-cn-shenzhen.aliyuncs.com/24.png)   

![aws-3](https://ottodeng.oss-cn-shenzhen.aliyuncs.com/25.png)   

详细的AWS的模版支持列表，请参考：   
https://github.com/F5Networks/f5-aws-cloudformation/blob/master/template-index.md   

有了这些不同的Cloud Templates，可以帮助我们快速地部署BIGIP到对应的环境中，缩短环境交付所需要的时间，最终可以通过自动化工具调用对用的公有云/私有云的模版，就可以轻松地bootstrap对应的BIGIP资源，部署到不同的云环境中。   

Every App, Anywhere.

有关更多的Cloud Template资料和部署文档，请参考以下链接：   
`AWS`: https://github.com/F5Networks/f5-aws-cloudformation   
`Azure`: https://github.com/F5Networks/f5-azure-arm-templates   
`Google`: https://github.com/F5Networks/f5-google-gdm-templates   
`Azure Stack`: https://github.com/F5Networks/f5-azure-stack-arm-templates   
`OpenStack`: https://github.com/F5Networks/f5-openstack-hot   
`VMware`: https://github.com/F5Networks/f5-vmware-vcenter-templates   
