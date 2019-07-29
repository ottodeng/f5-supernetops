---
title: "F5 连接NetOps/SecOps与DevOps」 -- 「2」Infrastructure as Code"
date: 2019-07-08T10:45:53+08:00
draft: false
tags: ["super-netops", "f5"]
---

# 「F5 连接NetOps/SecOps与DevOps」 -- 「2」Infrastructure as Code

本文主要分享什么叫做Infrastructure as Code, 还有实现它的两种方式：

![InfraAsCode](https://ottodeng.oss-cn-shenzhen.aliyuncs.com/14.png)

基础设施即代码(以下均简称IaC)是一种用描述性的方式来管理基础设施（包括网络，虚拟机，存储，负载均衡等），IaC模型在每次应用时都生成相同的环境，它是与DevOps结合的关键时间，与持续交付(Continue Delivery)结合使用。   

IaC的发展，解决了CD流水线中的环境飘移问题。如果没有IaC，团队必须维护各个环境的设置。随着时间的推移，每个环境都会成为了信息孤岛，无法自动复制相同的配置。环境之间的不一致会导致部署期间出现问题，最后会导致基础设施的管理，变得非常难以跟踪，并且只能通过手动进行单独的维护。   

![IaC](https://ottodeng.oss-cn-shenzhen.aliyuncs.com/10.png)   

## 与DevOps的关系

IaC可以成为在DevOps中实现最佳实践的关键属性，开发人员可以更多地参与定义配置，Ops团队在开发过程的早期阶段就参与其中。利用IaC的工具可以提高服务器状态和配置的可见性，最终为企业内的用户提供可视性，旨在将团队聚集在一起，最大限度地发挥他们的作用。自动化通常旨在解决手动过程中的混乱和容易出错的问题，并使其更高效，更高效。允许创建更好的软件和应用程序，灵活，减少停机时间，并为公司提供整体成本效益的方式。IaC旨在降低从手动配置中带来的复杂性。自动化和协作被认为是DevOps的核心要点，基础架构自动化工具通常作为DevOps工具链的重要一环。

## IaC的特点：
##### 1. 版本控制和历史管理
##### 2. 所有操作可以追溯和进行审计
##### 3. 快速简单，容易回滚
##### 4. 方面团队协作，共同维护
##### 5. 幂等性(Idempotence)

而幂等性是这里面一个很重要的规范原则，无论环境的起始状态如何，这个部署指令执行了多少次，它都可以保证环境最终的状态是一致的。因此，通过IaC，团队对环境描述进行更改并对配置模型进行版本化，通常会采用标准化并容易理解的代码格式（如JSON，YAML）。持续交付Pipeline以IaC方式配置目标环境。如果团队需要进行更改，他们会编辑源，而不是目标。记住，`Source of the truth`!

## IaC主要带来三个主要的价值：
##### 1. 成本（减少）
##### 2. 速度（更快的执行）
##### 3. 风险（人为的操作错误所带来的安全隐患）

实施IaC的团队可以快速，大规模地提供稳定的环境。团队通过代码表示环境的最终期望状态，从而避免手动配置环境并强制实现一致性。使用IaC进行基础架构部署都是可重复的，可防止因配置偏差或缺少依赖性而导致的运行时问题。DevOps团队可以与统一的实践和工具协同工作，快速，可靠，大规模地交付应用程序及其支持基础架构。

## 实现IaC通常有两种方法：
##### 1. Imperative（命令式） 
##### 2. Declarative（声明式）

![IaC](https://ottodeng.oss-cn-shenzhen.aliyuncs.com/15.png)   

命令式的特点非常明显，如果需要达到最终的目的，你要以适当的顺序执行特定的命令，比如你执行的顺序是123，就绝对不能是321。并且每一步操作，你都需要执行对应的API或者指令应该在哪里。

![Imperative](https://ottodeng.oss-cn-shenzhen.aliyuncs.com/16.png)   


而声明式就非常简单了，只需要描述你所需环境的最终状态，然后通过少量的API任务，post过去，最终环境就可以根据你所需要的描述，生成最终的状态，所以也非常受开发者喜爱。

![Declarative](https://ottodeng.oss-cn-shenzhen.aliyuncs.com/17.png)   

而f5有4种声明式的组件来匹配在持续交付流水线中的每一个环节：部署，上线，配置，监控。

![cd-pipeline](https://ottodeng.oss-cn-shenzhen.aliyuncs.com/19.png)   

![tools](https://ottodeng.oss-cn-shenzhen.aliyuncs.com/18.png)   

下一章开始，我将会具体的展开每一个组件（Cloud Template, Declarative Onboarding, Application Services 3 Extension, Telemetry Streaming)具体的作用和使用的方法以及场景。