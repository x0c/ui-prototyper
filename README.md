# ui-prototyper

> A **Claude Code** / **Codex CLI** skill that turns a product idea into high-fidelity UI/UX prototype images — grounded in real shipped apps via [Mobbin](https://mobbin.com), rendered with AI image generation, and confirmed with you at every step before anything gets generated.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-Skill-5A67D8?logo=anthropic&logoColor=white)](https://claude.ai/code)
[![Codex CLI](https://img.shields.io/badge/Codex%20CLI-Skill-10A37F?logo=openai&logoColor=white)](https://github.com/openai/codex)

**Languages:** [English](#english) | [中文](#中文)

---

<a id="english"></a>
## English

### Why this exists

Ask an AI agent to "design a UI" and you usually get one of two bad outcomes: a generic template that looks like every other AI-generated screen, or a single confident image with no room to steer before it's rendered. `ui-prototyper` is a skill (not a full app) that fixes both problems by treating UI prototyping as an actual design process:

- **Reference-grounded, not hallucinated.** Every design direction is anchored to a real interface pulled from [Mobbin](https://mobbin.com)'s screen/flow library — an actual shipped product, not the AI's generic idea of "a clean app."
- **Three genuinely different directions, not three palette swaps.** Before touching the rest of a flow, the skill generates three main-screen explorations that differ in layout skeleton, information density, navigation rhythm, and visual language — not just color.
- **You approve every prompt before it renders.** The exact prompt text is shown to you — on-screen copy included — and nothing is generated until you confirm or edit it.
- **Stays in its lane.** It's a UI/UX designer, not a product manager — it won't quietly redefine your product scope while you're just trying to see three home-screen options.

### What it does

1. Asks up to five sharp, high-leverage preference questions (one at a time, always with a recommended default) — only when the answer would actually change the visible design.
2. Searches Mobbin for real screens/flows/sections and inspects them visually before proposing any direction.
3. Generates three distinct main-screen design languages as three separate images, each grounded in its own Mobbin reference, and waits for you to pick one (or ask for a blend) before generating anything else.
4. Continues the rest of the flow in the selected design language, one image generation call per screen — never a multi-screen collage.
5. Supports targeted in-place corrections (fix one detail without regenerating the whole screen) instead of open-ended re-rolls.

### Prerequisites

This skill is a thin orchestration layer over two external capabilities it does **not** provide — you need both set up and paid for before it's useful:

- **Mobbin MCP server, with a paid Mobbin Pro account.** The skill calls `search_flows` / `search_screens` / `search_sections` on every design direction. Mobbin's free tier does not expose this search access — a Mobbin Pro subscription (billed by Mobbin, independent of your AI provider) is required, and the MCP server must be connected to your agent and authenticated with that account.
- **A paid image-generation tool available to the agent** — the built-in `imagegen` tool in Claude Code, or the equivalent image-generation tool in Codex CLI/OpenAI. Every exploration direction, every additional screen, and every in-place correction is a **separate metered image-generation call** billed against your account/API usage — a typical run (3 initial directions + several downstream screens + a few corrections) can add up to a dozen or more paid calls. There is no free/local fallback built into the skill.

Without both, the skill has no reference source and no way to render output — these are the core mechanics, not optional enhancements. If cost is a concern, keep exploration runs small (fewer screens, fewer correction rounds) rather than expecting the skill to batch or economize on your behalf.

### Quick Install

**Claude Code:**

```bash
git clone https://github.com/x0c/ui-prototyper-skill.git ~/.claude/skills/ui-prototyper
```

**Codex CLI:**

```bash
git clone https://github.com/x0c/ui-prototyper-skill.git ~/.codex/skills/ui-prototyper
```

Restart your agent. The entry point is `SKILL.md`; `agents/openai.yaml` provides the Codex-specific interface metadata (display name, default prompt, Mobbin MCP dependency declaration).

### Design philosophy

Prompts stay short and reference-carried rather than turning into exhaustive component-by-component UI specs — over-specifying layout, spacing, and color in text tends to collapse every direction into the same safe, generic template. Visual identity comes from the Mobbin reference image passed alongside the prompt; the prompt itself only locks in what must not drift (screen purpose, critical on-screen copy, a couple of hard interaction rules). See `references/imagegen-ui-prompts.md` for the full prompting approach, including the optional structured scaffold reserved for finishing a single high-fidelity final screen.

### License

[MIT](LICENSE)

---

<a id="中文"></a>
## 中文

### 为什么做这个

让 AI 直接"设计一个界面"，通常会得到两种糟糕结果之一：要么是一眼看出是 AI 生成的通用模板，要么是一张自信满满却没法沟通调整的成品图。`ui-prototyper` 是一个 skill（不是完整应用），把 UI 原型设计当成真实的设计流程来做：

- **有真实参考，不是凭空想象**：每个设计方向都锚定 [Mobbin](https://mobbin.com) 界面库里的真实产品截图，而不是模型对"一个干净的 App"的通用臆想。
- **三个真正不同的方向，不是换个配色**：展开完整流程前，先生成三版主界面探索，彼此在版式骨架、信息密度、导航节奏、视觉语言上有实质差异，而不只是颜色不同。
- **每次生图前都会给你看提示词**：完整提示词（含上屏文案）会先展示给你确认或修改，未经确认不会生成。
- **只做 UI/UX 设计**：定位是设计师而非产品经理，不会在你只想看三版主屏时悄悄替你重新定义产品范围。

### 核心能力

1. 最多问五个高价值偏好问题（一次一个，总是给出推荐答案），只在答案会实质改变可见设计时才问。
2. 生成任何方向前，先用 Mobbin 搜索真实界面/流程/板块并实际查看。
3. 生成三版风格迥异的主界面设计语言（各自独立成图），每版绑定各自的 Mobbin 参考；等你选定或要求融合后，才继续生成其他界面。
4. 后续界面延续选定的设计语言，一次调用只生成一张单一界面，不拼接多屏合图。
5. 支持定点修正（只改一处细节而不重新生成整张图），而不是无限制地重新生成。

### 前置依赖（含真实费用，务必确认后再用）

这个 skill 本身只是编排逻辑，不提供以下两项能力，使用前需要自行开通并承担各自费用：

- **Mobbin MCP，且账号需为 Mobbin Pro 付费订阅**：每个设计方向都会调用 `search_flows` / `search_screens` / `search_sections`；Mobbin 免费版不开放这部分搜索权限，必须是付费的 Mobbin Pro 账号（费用由 Mobbin 收取，与你的 AI 服务商无关），并把对应 MCP 服务接入并授权给 Agent。
- **可调用的付费图片生成工具**：Claude Code 内置的 `imagegen`，或 Codex CLI / OpenAI 侧对应的图片生成工具。三版初版探索、后续每张界面、每次定点修正，都是**各自独立计费的一次生图调用**——一次典型流程（3 版初探 + 若干后续界面 + 若干次修正）累计可能达到十几次甚至更多付费调用，skill 没有免费或本地兜底方案。

两者缺一，这个 skill 要么没有参考素材来源、要么没法出图——这是核心机制，不是可选增强。如果在意花费，建议主动缩小探索范围（少要几张界面、少要几轮修正），不要指望 skill 会替你精打细算控制调用次数。

### 快速安装

**Claude Code：**

```bash
git clone https://github.com/x0c/ui-prototyper-skill.git ~/.claude/skills/ui-prototyper
```

**Codex CLI：**

```bash
git clone https://github.com/x0c/ui-prototyper-skill.git ~/.codex/skills/ui-prototyper
```

重启你的 Agent 即可生效。入口是 `SKILL.md`；`agents/openai.yaml` 提供 Codex 专用的界面元数据（显示名称、默认提示词、Mobbin MCP 依赖声明）。

### 设计理念

提示词保持简短、由参考图承载视觉方向，而不是写成逐组件的完整 UI 规格——用文字过度锁定版式、间距、颜色，反而容易让所有方向收敛成同一套安全但通用的模板。视觉身份来自随提示词一起传入的 Mobbin 参考图；提示词本身只锁定不能漂移的部分（界面目的、必须准确的上屏文案、少量不可违反的交互规则）。完整的提示词方法见 `references/imagegen-ui-prompts.md`，其中也包含仅用于收尾单张高保真终稿的可选结构化骨架。

### 许可证

[MIT](LICENSE)