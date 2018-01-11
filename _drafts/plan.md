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


subjective

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

roles:
1. Customers: PM, admin, ...
1. QA
2. SE
3. Ops

whole team

scrum/xp/tdd/ATTD

DDD

business

env:
1. local
1. devel (for each team), iteration source of other modules? CI/CD issue, openstack/kubernetes?
1. testing
1. staging: db issue?
1. production

workflow:
1. PRD discuss: PM + QA + SE
2. interation plan/milestone (粒度控制) => backlog => staging/production, init PRD status
1. PRD -> backlog (分解issue): QA + SE
1. QA submit issue + coding for acceptance test
1. 确定sprint/kanban/burn down -> test thread ...?, TODO, notify SE/QA
1. issue assign, issue assigned
1. 创建issue branch: first response: in progress, notify SE/QA
1. coding, include UT
1. push (as frequently as possible)
1. Auto: code analysis/scan, UT (all? android/iOS?)
1. code review +1 and discuss
1. 提交merge/pull request, 注意rebase & squash commit
1. run UT (in devel env): consider sql build
1. code review +2
1. merge to master
2. deploy to devel/team env
2. auto: close issue?
1. auto: update sprint/kanban? DONE, notify SE/QA?
2. merge to testing branch
1. deploy to testing env
2. notify QA
1. acceptance testing
1. integration testing (if failed: re-open or open a new issue?)
2. merge to staging branch
1. deploy to staging env (DB sync issue)
2. notify customers (PM, ...)
3. PM review (acceptance), update PRD status
2. merge to production branch
1. CD to production env (PM review?)
2. Ops

monitor, notify

nightly test and report

architecture:

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
