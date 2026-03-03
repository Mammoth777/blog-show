---
title: 我在 Agents 时代的工作流思考
date: 2026-03-03T12:54:01+08:00
categories:
  - AI
  - 工作流
tags:
  - Agent
  - LLM
  - AgentEngineering
draft: false
---

## 引言

> 我建议大家在用词的时候尽量使用 **Agentic Engineering** 而不是 **Vibe Coding**。这个真的会影响 mindset。Coding 越来越 cheap，但工程思维的价值是越来越高。

这是在 X 上看到的一句话，深以为然。

未来不是 `Vibe Coding` 的时代——这注定是昙花一现，难成气候。**未来属于 `Agentic Engineering`。**

## 什么是 Agent？

在讨论 `Agentic` 之前，我们先明确：什么是 **Agent**？

### 抽象定义

**基础模型：**
```
Agent = (Perception, Policy, Action)
         感知      决策    行动
```

**完整模型：**
```
Agent = (Goal, State, Perception, Policy, Action)
         目标   状态   感知      决策    行动
```

### 核心特征

一句话总结：

> **Agent = 目标驱动的、可调用外部能力的、带状态循环的 LLM 控制系统。**

开发一个 Agent，需要具备以下条件：

- ✅ 有明确的目标（Goal）- 具体或抽象
- ✅ 有状态管理（State）
- ✅ 有决策能力（基于状态进行 Policy 选择）
- ✅ 有工具调用能力（Action）
- ✅ 有循环执行机制
- ✅ 能根据反馈调整策略

### 判断标准：自主决策循环

如何判断一个软件是否可称为 **Agent**？只要看一个核心特征：

> **是否存在自主决策循环？**
>
> Agent 的行为必然是：**观察 → 思考 → 行动 → 反馈 → 调整**

## Agent 的分类

| 类型 | 目标类型 | 生命周期 | 举例 |
|------|----------|----------|------|
| **Task Agent** | 固定目标 | 短 | 写单测、代码解释 |
| **Workflow Agent** | 任务链 | 中 | CI 自动修复、自动化部署 |
| **Meta Agent** | 抽象目标 | 长 | Claude Code、OpenCode |
| **System Agent** | 持续自治 | 持续 | 未来形态 |

## 三层架构

理解 Agent 生态，可以从三个层次来看：

### 1️⃣ Tool（工具层）

**函数执行器** - 提供基础能力, 这不是Agent

- API 调用
- 文件操作
- 代码执行
- 外部服务集成

### 2️⃣ Agent（代理层）

**围绕目标执行循环** - 完成特定任务

- 接收明确目标
- 自主规划执行步骤
- 调用工具完成目标
- 返回结果

### 3️⃣ System-Agent（系统级代理）

**生成目标、拆分目标、持续存在** - 最高形态

- 能够理解抽象意图
- 自主拆解复杂目标
- 协调多个 Agent 协作
- 持续学习和优化

> **OpenCode / Claude Code** 属于第 3 层。

## 结语

从 `Vibe Coding` 到 `Agentic Engineering`，不仅仅是用词的变化，更是思维模式的转变。

- `Vibe Coding` 依赖直觉和随机性
- `Agentic Engineering` 强调工程化和系统性

在这个 Agents 时代，我们需要培养的不仅是使用工具的能力，更是**设计系统、定义目标、构建循环**的工程思维。

Coding 越来越 cheap，但**工程思维的价值越来越高**。
