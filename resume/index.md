---
layout: resume
title: 简历
permalink: /resume/
---

# 马鹏

📞 18089212445 ｜ 📧 peng.ma.user@outlook.com

## 🧠 个人简介

全栈 / AI 工程师，4 年软件开发经验。

具备扎实 Java 后端与数据工程基础，正在向 **AI Engineer** 演进：熟悉 Agent / MCP / LLM 辅助开发范式，能将 Cursor、Spec-Driven Development（SDD）与工程交付结合，在复杂业务系统中提升从需求到联调的全链路效率。

**核心优势：**
- 企业级后端与微服务交付（Spring Boot / MySQL / Redis / Feign）
- AI 辅助工程化实践（SDD、Prompt Engineering、Agent 协作、Mock 基线建设）
- 电商订单 / 国补结算 / 税务开票等跨系统链路抽象与落地经验
- 全栈能力（React / Vue3）与数据平台经验（Spark / Flink / 星型建模）

---

## 🚀 工作经历

### 英湃（西安）科技有限公司

**软件开发工程师（全栈 / AI 方向）｜2026.02 - 至今**

#### DJI-OMS（订单与售后系统）

面向 C 端电商场景的订单与售后域中台，对接京东、抖音、拼多多等平台及 CRM / ERP / 税务系统，支撑拉单同步、履约、国补结算、自动开票与退货退款等核心链路。

**技术栈：** Java / Spring Boot / MySQL / MyBatis / Redis / Apollo / Feign

**AI 工程实践：**
- 基于 **Cursor + SDD** 交付：需求 `spec.md` → 设计 `plan.md` → 实现 → E2E 用例同源维护，形成可审计的需求—代码追溯链
- 使用 LLM 辅助领域建模、接口契约设计与复杂联调场景拆解，缩短跨系统需求澄清周期
- 建设 **MockRegistry + knowledge stub** 联调基线，结合 Playwright / SLS 日志检索做 Agent 化排障，提升多系统对接效率

##### 京东国补结算 · 一期（正向 + 逆向结算 / ERP 入账）

负责京东政府全资 / 混资国补结算能力落地，覆盖结算导入校验、多笔逆向结算（退货 / 折让）与 ERP 双轨入账。

- 主导混资国补逆向结算链路：支持多笔结算笔次识别、折让结清与全额冲销等场景，完成导入校验与异常兜底
- 梳理结算金额与 ERP 应收 / 折让分轨规则，修复零金额推送、状态不同步等边界问题，保障财务对账口径一致
- 建设 10+ 复杂导入场景的 mock 联调基线与测试文档，配合单测与代码质量治理保障上线

##### 京东国补结算 · 二期（税务自动开票）

在一期结算能力上，参与国补订单对接企业税务平台（iTax）的自动开票。

- 实现政府全资 / 混资场景下的蓝票推送、红票冲销与大批量拆票，含失败重推、幂等与异常处理
- 打通结算 → 开票 → 异步回调 → 发票落库 → ERP 归档全链路，负责 20+ 跨系统集成场景联调验收
- 参与发票查询与对账能力，支撑运营复盘与异常处理

##### 售后退款链路

- 主导平台自动退款开关按售后类型（退款 / 退货退款）拆分，统一多入口推款门禁
- 实现平台手工退款后拉单被动感知、售后单自动完结，打通 OMS → ERP 退款推送依赖链

**职责摘要：**
- 负责京东国补结算一期逆向导入与二期 iTax 开票链路的方案落地、联调验收与 E2E 保障
- 设计结算域金额语义、ERP / iTax 状态机与异常处理规则，保障跨系统数据一致性
- 将 AI 工具嵌入 SDD 与联调流程，建设可复用 mock / stub 测试基线

---

### Thoughtworks

**软件开发工程师｜2022.06 - 2026.01**

作为咨询公司开发工程师，参与多个客户项目交付，覆盖汽车、金融、电商与数据平台领域，具备跨行业系统设计与落地经验。

#### 代表项目

**汽车金融平台（Daimler）**
- 实现抵押 / 解抵押线上化流程，对接政府车管所
- 参与 Web 与移动端全栈开发

**汽车业务中台（FAW TOYOTA）**
- 设计支付发票模块并成功上线
- 梳理业务中台数据资产体系

**IT 基础平台（Daimler ITT）**
- 设计灰度发布与多实例部署能力
- 参与 IAM / RBAC 权限系统建设
- 主导 FinOps 数据建模与分析系统落地

**财务数据中台（LONGi）**
- 主导 EBS 数据迁移与建模（星型模型）
- 提升查询性能与数据处理效率

**CRM 系统（OPPO）**
- 参与 CRM 系统设计与开发
- 支持预算管理系统建设
- 积累微服务与业务建模经验

**技术关键词：** Spring Boot / 微服务 / 数据建模 / K8s / React / 数据平台 / DevOps

---

### 广联达

**助理软件开发工程师｜2021.07 - 2022.02**

- 参与建筑行业系统开发
- 完成后端服务开发与测试支持
- 掌握面向对象设计与敏捷开发流程

---

## 🧰 技能

### AI & 工程范式
- LLM 应用：Prompt Engineering、RAG 思路、Agent 任务编排
- 工具链：Cursor / ChatGPT / Copilot
- 方法论：**SDD（Spec Driven Development）**、需求—代码同源、E2E 用例驱动验收
- 协议与扩展：MCP Server 概念与实践、AI 辅助联调与日志分析

### 后端
- Java / Spring Boot / Spring Cloud / MyBatis / JPA
- MySQL / Redis / RabbitMQ / Apollo / Elasticsearch
- 微服务集成：Feign、定时 Job、事件监听、分布式配置

### 全栈
- React / Vue3 / TypeScript
- REST API 设计与前后端协作
- 业务中台、CRM、订单域界面与接口联调经验

### 数据工程
- Spark / Flink / Hive / DBT
- 数据建模（Kimball 星型模型）
- Airflow / Azure Data Factory
- ETL、数据迁移、查询性能优化

### DevOps & 质量
- Kubernetes / Istio / Jenkins / ArgoCD / GitHub Actions
- 单元测试、JaCoCo / SonarQube、E2E（Python / Playwright）
- Mock / Stub 联调基线、跨系统集成测试

---

## 🎓 教育背景

### 西北农林科技大学

软件工程 · 本科  
2017.09 - 2021.07



