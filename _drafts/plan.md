---
layout: post
title: "Plan"
---

<!-- TOC -->

- [1. 快速反应组](#1-%E5%BF%AB%E9%80%9F%E5%8F%8D%E5%BA%94%E7%BB%84)
- [2. Workflow](#2-workflow)
    - [2.1. 工具与选型](#21-%E5%B7%A5%E5%85%B7%E4%B8%8E%E9%80%89%E5%9E%8B)
        - [2.1.1. 核心工具](#211-%E6%A0%B8%E5%BF%83%E5%B7%A5%E5%85%B7)
    - [2.2. Product-service Workflow](#22-product-service-workflow)
- [3. 架构组（加强）](#3-%E6%9E%B6%E6%9E%84%E7%BB%84%EF%BC%88%E5%8A%A0%E5%BC%BA%EF%BC%89)
        - [3.0.1. 其他工具](#301-%E5%85%B6%E4%BB%96%E5%B7%A5%E5%85%B7)
- [4. Tech Talk （技能提升）](#4-tech-talk-%EF%BC%88%E6%8A%80%E8%83%BD%E6%8F%90%E5%8D%87%EF%BC%89)

<!-- /TOC -->

# 1. 快速反应组

# 2. Workflow

## 2.1. 工具与选型

### 2.1.1. 核心工具
Component | Candinates
----------|-----------
SCM | Gitlab, Bitbucket, Github
Issue/Kanban | built-in, Jira
CI | built-in, Jenkins, Bamboo
WiKi | built-in, Confluence
Code analysis | codecov, IDEA built-in, …
Code coverage | Coco/imagix/bullseye (or alike)
Notification | Dingding, Wechat, E-mail, SMS


confluence不止存放PRD，除PRD还有存放所有必要的文档，包括但不局限于：
1. 数据库设计
1. 项目架构
1. DevOps
1. ...

## 2.2. Product-service Workflow

1. PRD discuss
2. 分解issue，确定sprint/kanban
3. 测试提交issue
4. 创建issue branch
5. coding
6. 提交merge/pull request
7. code check
8. code review
9. UT，自动化测试
10. 测试人员测试
11. merge, close issue, update spring/kanban
12. merge to test env, integration testing

# 3. 架构组（加强）



开发环境，包括：
1. markdown
1. ...

### 3.0.1. 其他工具
Component | Candinates
----------|-----------
Docker | Kubernetes
VM | OpenStack
DB Unit | ?
Mem leakage | ?
Nexus | *
DB/Cache/MQ monitoring and analysis | ?
LDAP | *

# 4. Tech Talk （技能提升）
