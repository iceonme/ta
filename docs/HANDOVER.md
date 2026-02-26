# Trading Agent (TA) - 全局元仓库交接日志 (Global Handover)

> **定位**: 跨项目决策记录、架构演进脉搏以及多项目协作的“灵魂”。
> 此文档旨在解决跨电脑、跨 Agent 协作时的“上下文断层”问题。

---

## 📅 当前状态 (2026-02-26)

### 1. 核心决策背景 (The "Why")
- **三足鼎立架构**：决定将系统拆分为 TAA (Arena), TAS (Squad), TS (Skills)。目的是为了实现“平台-应用-工具”的完全解耦。
- **Git 策略**：采用 Meta-repo + 3 Sub-repos (Submodule) 模式。这种方式既保证了各项目的独立演进，又能在元仓库中统一协调版本和全局文档。
- **协作规范**：所有子项目必须同步 `COLLABORATION_GUIDE.md`，作为 AI 助手的系统提示词，确保 VibeCoding 风格一致。

### 2. 关键项目进度
- [x] **基础设施支撑**：已完成 `C:\projects\ta` 的物理结构搭建。
- [x] **Git 环境初始化**：主仓库与三个子模块仓库已建立并关联。
- [x] **文档同步**：VISION, ROADMAP, BOARD 等模板已分发至各子项目并完成了个性化愿景描述。

---

## 🚀 接下来要做什么 (Next Steps)

1. **[TAA] 引擎迁移** (当前最高优先级):
   - 从 `C:\projects\CTS1\engines\backtest.py` 抽取核心撮合逻辑。
   - 在 `TradingAgentArena` 下建立独立的引擎模块，解耦对 Grid RSI 策略的依赖。
2. **[TS] Skill 协议原型**:
   - 定义标准的 JSON 请求/响应格式，使 TS 能够作为 AI 的工具被调用。
3. **[TAS] 小队握手**:
   - 建立一个小型的 PA 助手，尝试连接启动后的 TAA。

---

## 💡 决策快照 (Architectural Decisions)

| 决策点 | 选定方案 | 理由 |
|--------|----------|------|
| TAA 调性 | 游戏化/角斗场 | 提高回测和模拟的趣味性，支持多 Agent 竞技 |
| TS 规范 | MCP/Anthropic | 拥抱开放生态，让大模型能直接调用策略 |
| 协作语言 | 简体中文 | 符合用户全局规则，提升交流效率 |

---

## 📝 电脑/Agent 切换备忘录
如果你在另一台电脑上启动：
1. 请先执行 `git submodule update --init --recursive`。
2. **必读**：首先阅读此 `ta/docs/HANDOVER.md` 了解全局局势。
3. 接着阅读各子项目的 `docs/HANDOVER.md` 进行细节落地。
