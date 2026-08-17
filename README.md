# 爆款公众号选题与标题

<p align="center">
  <a href="./SKILL.md"><img src="https://img.shields.io/badge/skill-bigpeng--hot--gzh-E23D2D?style=flat-square" alt="skill"></a>
  <a href="./LICENSE"><img src="https://img.shields.io/badge/license-MIT-1E1B18?style=flat-square" alt="MIT"></a>
  <img src="https://img.shields.io/badge/for-WeChat%20公众号-07C160?style=flat-square" alt="WeChat">
</p>

这是一个给微信公众号做**选题和标题**的 Agent Skill。公式不是拍脑袋想的，而是从约 100 篇爆款 AI 公众号文章里拆出来的：什么身份、什么数字、什么反转，会反复出现在能点开的标题上。

换到电商、体制内、教育时，复用同一套槽位，不要复用语料里的产品名。只做选题和标题，不写正文。

## 爆款标题的 7 种公式

高转化标题通常同时有三件事：**具体对象 + 可感知结果 + 读者身份或情绪**。

| 公式 | 怎么写 |
|---|---|
| 数字清单 | 身份 + 必装/推荐 + N 个 + 对象 |
| 我+代价+收获 | 我用 X 做了 Y（夸张量）+ 得到 Z |
| 反转结论 | 以为是 A，其实是 B / 不是 X，是 Y |
| 速成教程 | 时长或字数 + 精通/速通/保姆级 |
| 社会证明 | Star / 下载 / 大厂 / 热榜 + 对象 |
| 对比站队 | A 和 B 到底选哪个 / 实测 A 和 B |
| 情绪短句 | 短、口语；一篇里最多 1 条 |

选题侧还有 8 个可复制模板：必装清单、亲测复盘、从 0 到 1 教程、热点产品落地、对比抉择、开源神器安利、身份场景化、反常识/情绪钩。

写法上的硬约束：

- 主标题约 18–32 字；工具名尽量出现在前 16 字
- 数字必须具体（7、50、209 页），禁止「多个」「一系列」
- 标题写了「附教程 / 提示词 / 开源仓库」，正文就得真有
- 不编造 Star、下载量、实验样本量
- 候选标题禁止同义改写
- 不用震惊、重磅、炸裂，也不写 `XX 发布了` 这种通稿

完整规则在 [references/title-formulas.md](references/title-formulas.md) 和 [references/topic-templates.md](references/topic-templates.md)。真实标题样本见 [references/title-corpus.md](references/title-corpus.md)。

## 安装

### Cursor

```bash
git clone https://github.com/BigPengSays/bigpeng-hot-gzh.git
cd bigpeng-hot-gzh
ln -sfn "$(pwd)" "${HOME}/.cursor/skills/bigpeng-hot-gzh"
```

### Claude Code / Codex 等

把本目录放到对应产品的 skills 路径，保证能读到 `SKILL.md`。入口文件是 [SKILL.md](./SKILL.md)。

调用样例见 [examples/prompts.md](examples/prompts.md)。

## 边界

- 不写正文、大纲、配图。写稿交给其他写作 skill。
- 不是推文 20 字短标题器。这是给公众号信息流用的偏长标题。
- 语料偏 AI 工具赛道。换赛道时只复用公式，不要把 Codex / WorkBuddy / Skill 硬套进去。
- 社会证明类标题没有公开可查数字时，会改用清单或教程公式，而不是编一个星标数。

## 仓库结构

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

## License

[MIT](./LICENSE) · 作者 [BigPeng](https://github.com/BigPengSays)
