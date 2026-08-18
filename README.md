<h1 align="center">bigpeng-hot-gzh</h1>

<p align="center">
  <strong>为微信公众号生成爆款选题方向与候选标题——只做选题和标题，不写正文。</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Agent_Skills-Open_Standard-blueviolet?style=for-the-badge" alt="Agent Skills standard">
  <img src="https://img.shields.io/badge/for-WeChat%20公众号-07C160?style=for-the-badge" alt="WeChat Official Account">
  <img src="https://img.shields.io/badge/7_Title_Formulas-8_Topic_Templates-blueviolet?style=for-the-badge" alt="7 formulas, 8 templates">
  <img src="https://img.shields.io/badge/License-MIT-blue?style=for-the-badge" alt="MIT License">
</p>

<p align="center">
  <a href="#-why">Why</a> ·
  <a href="#-能产出什么">Features</a> ·
  <a href="#-适用场景">Use cases</a> ·
  <a href="#-how-it-works">How it works</a> ·
  <a href="#-usage">Usage</a> ·
  <a href="#-install">Install</a> ·
  <a href="examples/prompts.md">Examples</a>
</p>

<p align="center">
  <strong>约 100 篇爆款 AI 公号标题拆成 7 种公式 + 8 个选题模板</strong>，换赛道复用槽位，不硬搬语料里的产品名。
</p>

**How it works, in 3 steps:**

1. **给材料** — 贴草稿、关键词，或只说「最近写点什么」
2. **自动选路径** — 有明确选题走路径 A 出标题；没选题走路径 B 先给 4 个方向
3. **拿结果** — 默认 6 条不同公式候选 + 1 条首选，每条附「正文须兑现什么」

---

## 🤔 Why

写公众号，最难的往往不是正文，而是**选题和标题**：

- 📝 有想法，但不知道哪个角度值得写
- 🏷️ 标题改十遍，还是像通稿、像广告
- 🔢 想用数字和身份钩读者，又怕编 Star、下载量
- ⏱️ 每次从零想句式，浪费在「起标题」而不是「写内容」

**bigpeng-hot-gzh 把爆款标题拆成可复用的公式与选题模板**，Agent 按你的材料自动选路径，一次给出多条不同公式的候选标题，并标一条首选。不写正文、不出大纲——写正文交给 khazix-writer 等写作 skill。

语料来自 AI 工具/效率赛道约 100 篇爆款公号；换到电商、体制内也能用：**槽位留下，语料里的 Codex、WorkBuddy 等产品名不要跟着搬**。

---

## 📦 能产出什么

| 路径 | 你给了什么 | 输出 |
|------|-----------|------|
| **A · 已有选题** | 草稿、描述、明确主题，或「帮我起标题」 | 6 条不同公式候选 + 1 条首选；每条含字数、公式、兑现点 |
| **B · 尚无选题** | 关键词、一句话想法、空输入 | 4 个选题方向（模板不重复）× 每方向 3 条标题 + 1 个「最值得先写」 |

底层规则来自 `references/`：7 种标题公式、8 个选题模板、真实语料校准、发出前 QA 清单。

<details>
<summary>📋 <strong>7 种标题公式</strong></summary>

| 公式 | 怎么写 |
|------|--------|
| 数字清单 | 身份 + 必装/推荐 + N 个 + 对象 |
| 我+代价+收获 | 我用 X 做了 Y（夸张量）+ 得到 Z |
| 反转结论 | 以为是 A，其实是 B / 不是 X，是 Y |
| 速成教程 | 时长或字数 + 精通/速通/保姆级 |
| 社会证明 | Star / 下载 / 大厂 / 热榜 + 对象 |
| 对比站队 | A 和 B 到底选哪个 / 实测 A 和 B |
| 情绪短句 | 短、口语；一篇里最多 1 条 |

规则全文 → [references/title-formulas.md](references/title-formulas.md)

</details>

<details>
<summary>📋 <strong>8 个选题模板</strong></summary>

必装清单 · 亲测复盘 · 从 0 到 1 教程 · 热点产品落地 · 对比抉择 · 开源神器安利 · 身份场景化 · 反常识/情绪钩

模板说明 → [references/topic-templates.md](references/topic-templates.md) · 真实样本 → [references/title-corpus.md](references/title-corpus.md)

</details>

---

## 🏢 适用场景

- **已有草稿，差标题** — 路径 A，6 条公式覆盖，标首选
- **只有关键词** — 路径 B，先出 4 个方向再配标题
- **不知道写什么** — 路径 B + 当前热点检索，给出可写方向
- **换赛道写公号** — 复用公式槽位，替换身份与对象，不搬 AI 语料产品名
- **长标题信息流** — 主标题约 18–32 字，工具名尽量进前 16 字（非推文 20 字短标题）

---

## ⚙️ How it works

Agent 读 [SKILL.md](./SKILL.md) 做路由：有明确选题 → **路径 A**；只有想法或空输入 → **路径 B**。

- 路径 A：抽可钩元素（身份、数字、对象、冲突）→ 覆盖 6 个不同公式 → 过 [qa-checklist](references/qa-checklist.md) → 标首选
- 路径 B：关键词映射模板，或 WebSearch 绑当前热点 → 4 方向 × 3 标题 → 标「最值得先写」

硬规则：不编 Star/下载量；标题写了附教程/提示词/仓库，兑现点必须写清；6 条禁止同义改写。

🔧 **完整路由与输出格式 → [SKILL.md](./SKILL.md)**

---

## 🚀 Usage

对 Agent 说「用 bigpeng-hot-gzh」，再贴想法或草稿：

```text
用 bigpeng-hot-gzh 帮我起几个爆款公众号标题。

想法：我把最近两个月用 AI 做小红书封面的流程收成了 8 个 Skill，
从选题、文案、出图到封面文字都覆盖。给自己做号的中文创作者看。
正文里会写每个 Skill 的装法和一个真实用例。
```

▶️ **更多调用样例 → [examples/prompts.md](examples/prompts.md)**

---

## 📥 Install

### Cursor

```bash
git clone https://github.com/BigPengSays/bigpeng-hot-gzh.git
cd bigpeng-hot-gzh
ln -sfn "$(pwd)" "${HOME}/.cursor/skills/bigpeng-hot-gzh"
```

### Claude Code / Codex 等

把本目录放到对应产品的 skills 路径，能读到 `SKILL.md` 即可。入口是 [SKILL.md](./SKILL.md)。

---

<details>
<summary>❓ <strong>FAQ & 边界</strong></summary>

**会写正文吗？**  
不会。只做选题和标题；正文、大纲、配图交给其他 skill。

**和推文短标题 skill 的区别？**  
本 skill 标题偏长，给公众号信息流用，不是 title-optimizer 那套 20 字推文标题。

**没有 Star 数据能用社会证明公式吗？**  
不能编造。没有公开可查的数据就改走数字清单或教程公式。

**换赛道要注意什么？**  
只搬公式槽位，别把 AI 语料里的产品名硬套进新赛道。

**写出前检查什么？**  
→ [references/qa-checklist.md](references/qa-checklist.md)

</details>

<details>
<summary>📁 <strong>Repository structure</strong></summary>

```
bigpeng-hot-gzh/
├── SKILL.md                 # Skill 入口与路由
├── README.md
├── LICENSE
├── examples/
│   └── prompts.md           # 调用样例
└── references/
    ├── topic-templates.md   # 8 个选题模板
    ├── title-formulas.md    # 7 种公式与禁用规则
    ├── title-corpus.md      # 真实标题样本
    └── qa-checklist.md      # 发出前检查
```

</details>

---

## License

[MIT](./LICENSE) · 作者 [BigPeng](https://github.com/BigPengSays)

## Star History

<a href="https://www.star-history.com/?repos=BigPengSays%2Fbigpeng-hot-gzh&type=date&legend=top-left">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/chart?repos=BigPengSays/bigpeng-hot-gzh&type=date&theme=dark&legend=top-left" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/chart?repos=BigPengSays/bigpeng-hot-gzh&type=date&legend=top-left" />
   <img alt="Star History Chart" src="https://api.star-history.com/chart?repos=BigPengSays/bigpeng-hot-gzh&type=date&legend=top-left" />
 </picture>
</a>
