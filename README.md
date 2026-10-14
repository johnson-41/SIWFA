<h1 align="center">SIWFA</h1>
<p align="center">（SI Workspace Framework Agent 工作区框架规范）</p>

![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)
![Works with](https://img.shields.io/badge/Works%20with-Claude%20%C2%B7%20Codex%20%C2%B7%20GPT%20%C2%B7%20Gemini-blue)
![Language](https://img.shields.io/badge/Language-%E4%B8%AD%E6%96%87-red)

> **六份文档，把任何 SI 助手变成「有规矩」的工作搭档。**
>
> 一套文件夹规范 + 一套项目流程 + 一条汇报标准，开箱即用。
> 适用于 Claude、Codex、GPT、Gemini 等任何能读取文件的 SI Agent（智能体）。

---

## 🎯 它解决什么问题

| 没有框架时 | 有了框架后 |
|---|---|
| 文档散落各处，找不到上次的产出 | 所有产出强制归入 `Project-NNN-名称/` |
| Agent 不读规则就动手，方向偏航 | Agent 启动前必须先读三份核心文档 |
| 同样的坑反复踩，经验不沉淀 | 每个项目收尾强制沉淀到「复利与踩坑」 |
| 汇报啰嗦、抓不住重点 | 汇报统一遵循 STE 规范：关键信息先行、状态词固定 |
| 成本不可见 | 每个项目收尾做 Token 成本核算 |
| 交付没有边界 | 先出预览再出完整版，交付后 48 小时免费修订 |

## 🏗️ 框架长什么样

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/siwa-structure-dark.png">
  <img alt="SIWFA 结构规范图：用户 → SI 助手 → 项目工作区；Workspace/ 规则中枢含六份核心文档；收尾经验回写" src="assets/siwa-structure-light.png">
</picture>

```
<WORKSPACE_ROOT>/　　　　← 你自选的工作区根目录（如 ~/work）
├── Workspace/　　　　   ← 规则中枢（六份核心文档，不存项目产出）
│   ├── agent.md　　　　 ← Agent 最高优先级指令
│   ├── 全局工作台.md　　 ← 总体规则、行为铁律、命名规范
│   ├── 复利与踩坑.md　　 ← 经验资产库，只增不删
│   ├── 新项目流程.md　　 ← 项目执行 SOP，三档模式
│   ├── 工程的原则.md　　 ← 代码/工程任务执行基线
│   └── 方法论日志.md　　 ← 规则版本演变，可回退
│
├── Project-001-名称/　　← 具体项目（编号自增）
│   ├── 背景情况.md　　　 ← 必填，项目启动前由用户提供
│   ├── Token成本核算.md ← 项目收尾统计
│   └── ...　　　　　　　 ← 该项目全部产出
└── Project-002-名称/
```

## 🚀 三步接入

**第一步：确定工作区位置** — 选定（或创建）你的工作区根目录 `<WORKSPACE_ROOT>`（如 `~/work`），并在其下创建 `Workspace/` 文件夹。

**第二步：下载文档到指定位置** — 把本仓库 `workspace/` 目录下的六份核心文档，下载并放入第一步确定的 `<WORKSPACE_ROOT>/Workspace/`。

**第三步：执行文档，发送启动提示词** — 把下面这段提示词发给你的 SI 助手（触发它读取文档并进入工作模式），其中的 `<WORKSPACE_ROOT>` 要替换成第一步确定的实际路径：

```
你是我的工作助手。启动任何任务前，先读取 <WORKSPACE_ROOT>/Workspace/ 下的六份核心文档：
agent.md、全局工作台.md、复利与踩坑.md、新项目流程.md、工程的原则.md、方法论日志.md。
确认理解后，按「新项目流程」执行，向我的汇报遵循 STE 规范。
```

## 📚 六份核心文档

| 文档 | 职责 |
|------|------|
| [`agent.md`](workspace/agent.md) | Agent 最高优先级指令：解析流、第一动作、汇报规范 |
| [`全局工作台.md`](workspace/全局工作台.md) | 总体规则、目录规范、行为铁律（11 条）、命名规范、执行原则 |
| [`复利与踩坑.md`](workspace/复利与踩坑.md) | 记录错误、教训、可复用方法，避免重复踩坑 |
| [`新项目流程.md`](workspace/新项目流程.md) | 标准化项目启动流程，从需求到交付（8 步） |
| [`工程的原则.md`](workspace/工程的原则.md) | 代码/工程任务执行基线（5 条原则） |
| [`方法论日志.md`](workspace/方法论日志.md) | 方法论的版本演变记录 |

## ⚙️ 三种执行模式

每个项目启动前先选模式，按复杂度匹配投入：

| 模式 | 定义 | 适用场景 |
|------|------|----------|
| 简单模式 | 背景 + 直接执行呈现结果 | 需求明确的小任务：改个文件、写段文案、查个信息，问清背景后直接出结果 |
| 阶梯模式（默认） | 背景 + 各环节可跳跃 | 中等复杂度的项目：框架提问、盲点扫描、方案推演各环节可由用户决定跳过，节奏灵活 |
| 思考模式 | 背景 + 流程完整执行 | 战略级或需求模糊的项目：完整走完提问、盲点推演、方案制定，再动手执行 |

## ✨ 特色机制

- **STE 汇报规范**：源自 ste-zh 规范（ASD-STE100 简化技术中文，MIT），汇报关键信息先行、状态词固定、如实写验证，不叙述过程。
- **盲点三维扫描**：关键节点用 blindspot-audit 扫盲区，给出三种解决思路。
- **技能策展**：项目启动前检索本地技能库 → 对比外部平台 → 择优汰旧。
- **Token 成本核算**：项目收尾记录预估与实际消耗，成本可见。
- **交付后修订窗口**：交付后 48 小时内免费修订一轮，边界清晰。
- **方法论日志**：任何规则改动都记录版本，支持对比与复原。

## ❓ FAQ

**支持哪些 Agent？**
任何能读取文件的 SI 助手（Claude、Codex、GPT、Gemini、DeepSeek 等）。有 skill 机制的（如 Claude Code、Hermes），可额外安装 `ste-zh` 技能获得完整汇报规范；没有的，手动遵循 `工程的原则.md` 第五条即可。

**必须用中文吗？**
框架本身为中文设计，规则与语言无关，你可以按需翻译。

**每次会话会忘掉规则怎么办？**
框架的设计就是「文件即记忆」：Agent 每次启动先读文档，规则写在文件里而不是会话里，天然跨会话、跨 Agent。

**和 Agent 的官方 memory（记忆）功能冲突吗？**
不冲突。官方 memory 适合存用户偏好，本框架负责工作流纪律，两者互补。

## 🙏 致谢

- 感谢 dualface 开发的 [ste-zh](https://github.com/dualface/ste-zh)（ASD-STE100 简化技术中文，MIT 许可）——本框架的 STE 汇报规范来源。
- 感谢 MJL-ren 开发的 [blindspot-audit](https://github.com/MJL-ren/blindspot-audit)——本框架的盲点扫描方法来源。

## 📄 License

[MIT](LICENSE)

---

*本框架由实际工作迭代而来，欢迎 Star、Fork、提 Issue 一起改进。*
