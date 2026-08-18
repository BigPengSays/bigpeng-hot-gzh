<h1 align="center">微信公众号爆款AI选题Skill</h1>

<p align="center">
  <strong>给微信公众号做选题和标题。材料来自大约 100 篇爆款 AI 公号文章，拆的是标题里反复出现的身份、数字、反转。换到电商或体制内也能用：槽位留下，语料里的产品名不要跟着搬。不写正文。</strong>
</p>

<p align="center">
  <a href="./SKILL.md"><img src="https://img.shields.io/badge/skill-bigpeng--hot--gzh-E23D2D?style=for-the-badge" alt="skill"></a>
  <a href="./LICENSE"><img src="https://img.shields.io/badge/license-MIT-blue?style=for-the-badge" alt="MIT"></a>
  <img src="https://img.shields.io/badge/for-WeChat%20公众号-07C160?style=for-the-badge" alt="WeChat">
</p>

<p align="center">
  <a href="#爆款标题的-7-种公式">公式</a> ·
  <a href="#使用方法">用法</a> ·
  <a href="#安装">安装</a> ·
  <a href="#边界">边界</a> ·
  <a href="#仓库结构">结构</a> ·
  <a href="examples/prompts.md">示例</a>
</p>

---

## 爆款标题的 7 种公式

能点开的标题，多半先让人看懂：写给谁、在讲什么、看完能带走什么。

| 公式 | 怎么写 |
|---|---|
| 数字清单 | 身份 + 必装/推荐 + N 个 + 对象 |
| 我+代价+收获 | 我用 X 做了 Y（夸张量）+ 得到 Z |
| 反转结论 | 以为是 A，其实是 B / 不是 X，是 Y |
| 速成教程 | 时长或字数 + 精通/速通/保姆级 |
| 社会证明 | Star / 下载 / 大厂 / 热榜 + 对象 |
| 对比站队 | A 和 B 到底选哪个 / 实测 A 和 B |
| 情绪短句 | 短、口语；一篇里最多 1 条 |

选题还有 8 个模板：必装清单、亲测复盘、从 0 到 1 教程、热点产品落地、对比抉择、开源神器安利、身份场景化、反常识/情绪钩。

写的时候卡住这几条：

- 主标题大约 18–32 字，工具名尽量放进前 16 字
- 数字要具体，7、50、209 页都可以，「多个」「一系列」不行
- 标题写了「附教程 / 提示词 / 开源仓库」，正文就得有
- 别编 Star、下载量、实验样本量
- 一组标题不要互相同义改写
- 别用震惊、重磅、炸裂，也别写 `XX 发布了`

规则全文在 [references/title-formulas.md](references/title-formulas.md) 和 [references/topic-templates.md](references/topic-templates.md)。真实标题样本在 [references/title-corpus.md](references/title-corpus.md)。

---

## 使用方法

对 Agent 说「用 bigpeng-hot-gzh」，再贴一段想法或草稿。它按不同公式出一组标题，并标一条首选。

其他叫法见 [examples/prompts.md](examples/prompts.md)。

### 例子

**输入**

```text
用 bigpeng-hot-gzh 帮我起几个爆款公众号标题。

想法：我把最近两个月用 AI 做小红书封面的流程收成了 8 个 Skill，
从选题、文案、出图到封面文字都覆盖。给自己做号的中文创作者看。
正文里会写每个 Skill 的装法和一个真实用例。
```

**输出（节选）**

| 公式 | 候选标题 |
|---|---|
| 数字清单 | 中文创作者必装的 8 个小红书封面 Skill |
| 我+代价+收获 | 我把小红书封面流程收成 8 个 Skill，从选题到出图不用再临时想 |
| 反转结论 | 做小红书封面，缺的不是灵感，是这 8 个可安装的 Skill |
| 速成教程 | 8 个 Skill 把小红书封面从选题做到出图 |
| 对比站队 | 与其每次让 AI 重想封面，不如装这 8 个 Skill |
| 情绪短句 | 小红书封面这件事，终于不用每次从头聊 |

首选：`中文创作者必装的 8 个小红书封面 Skill`。前 16 字就能看懂给谁、几条、干什么。

---

## 安装

### Cursor

```bash
git clone https://github.com/BigPengSays/bigpeng-hot-gzh.git
cd bigpeng-hot-gzh
ln -sfn "$(pwd)" "${HOME}/.cursor/skills/bigpeng-hot-gzh"
```

### Claude Code / Codex 等

把本目录放到对应产品的 skills 路径，能读到 `SKILL.md` 即可。入口是 [SKILL.md](./SKILL.md)。

---

## 边界

- 不写正文、大纲和配图
- 标题偏长，给公众号信息流用，不是推文那套 20 字
- 语料偏 AI 工具。换赛道只搬公式，别把 Codex、WorkBuddy 硬套进去
- 没有公开可查的 Star 或下载量，就不要走社会证明，改清单或教程

---

<details>
<summary>📁 <strong>仓库结构</strong></summary>

```text
bigpeng-hot-gzh/
├── SKILL.md
├── README.md
├── LICENSE
├── examples/prompts.md     # 调用样例
└── references/
    ├── topic-templates.md  # 8 个选题模板
    ├── title-formulas.md   # 7 种公式与禁用规则
    ├── title-corpus.md     # 真实标题样本
    └── qa-checklist.md     # 发出前检查
```

</details>

---

## License

[MIT](./LICENSE) · 作者 [BigPeng](https://github.com/BigPengSays)
