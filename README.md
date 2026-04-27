# IELTS Claude Skills · v1.0

> 一套跑在 Claude Code 上的雅思备考 AI 教练 skill。
> **无状态、零依赖、纯文本提示词。** 装上就能用。

---

## 这是什么

4 个 [Claude Code Skill](https://docs.claude.com/en/docs/claude-code/skills)，构成一个最小可用的雅思备考助手：

| Skill | 干啥 | 触发词 |
|-------|------|--------|
| `/ielts` | 路由入口 + 摸底 + 给建议 | 「我要备考雅思」「IELTS」 |
| `/ielts-writing` | 写作四维批改 + 改写对比 + 审题 | 「批改作文」「帮我看看这篇」 |
| `/ielts-reading` | 同义替换提取 + T/F/NG 拆解 + 错题诊断 | 「分析阅读」「这道为什么错」 |
| `/ielts-speaking` | 5 个万能故事覆盖 80% Part 2 话题 | 「口语素材」「Part 2 准备」 |

**特点：**
- 完全无状态——不写任何本地文件，每次对话独立
- 无依赖——纯 markdown 提示词，无 npm、无 Python、无数据库
- 中文交互 + 英文术语
- MIT License，随便改

---

## 适合谁

- 备考雅思、想用 AI 当陪练的考生
- 已经在用 Claude Code 的开发者
- 想看看雅思 skill 怎么写的人（拿去改成自己的版本）

**不适合：** 想要进度追踪、错题本、可视化数据的人——这是无状态版本，要这些功能请等后续版本或自己加。

---

## 安装

### 前提
你要先装好 [Claude Code](https://docs.claude.com/en/docs/claude-code)。

### 方法一：直接复制

```bash
# Mac / Linux
cp -r ielts ielts-writing ielts-reading ielts-speaking ~/.claude/skills/
```

```powershell
# Windows PowerShell
Copy-Item -Recurse ielts, ielts-writing, ielts-reading, ielts-speaking $env:USERPROFILE\.claude\skills\
```

### 方法二：克隆

```bash
git clone https://github.com/YANZHANLIN/ielts-claude-skills.git
cd ielts-claude-skills
cp -r ielts ielts-writing ielts-reading ielts-speaking ~/.claude/skills/
```

装完之后重启 Claude Code，输入 `/ielts` 就能用。

---

## 怎么用

### 场景 1：什么都不知道，想被引导

```
你：/ielts
AI：（问你 3 个问题：目标分、考试日期、今天想练啥）
   → 路由到对应的子 skill
```

### 场景 2：直接批改作文

```
你：/ielts-writing
   [粘贴题目 + 你的作文]
AI：
- 四维评分（TR / CC / LR / GRA）
- 句子级标注每个问题
- 改写成目标分数版本
- 给提分优先级
```

### 场景 3：分析阅读错题

```
你：/ielts-reading
   [粘贴文章 + 题目 + 你的答案 + 标准答案]
AI：
- 逐题拆解错因
- 提取同义替换词表
- T/F/NG 逻辑分析
```

### 场景 4：准备口语素材

```
你：/ielts-speaking
   "帮我准备 Part 2 描述一次旅行"
AI：
- 200-250 词的 Part 2 回答
- 4-6 个 Part 3 追问预测
- 关键表达标注
```

---

## 文件结构

```
ielts-claude-skills/
├── ielts/SKILL.md              # 路由教练
├── ielts-writing/SKILL.md      # 写作批改
├── ielts-reading/SKILL.md      # 阅读分析
├── ielts-speaking/SKILL.md     # 口语素材
├── README.md                   # 你正在看
└── LICENSE                     # MIT
```

每个 skill 就是一个文件夹 + 一个 `SKILL.md`。Claude Code 通过 `name` 字段识别和触发。

---

## 怎么改

想改成自己的版本：

1. Fork 一份
2. 改对应的 `SKILL.md`——人格、评分标准、模板都在里面
3. 重新复制到 `~/.claude/skills/`
4. 重启 Claude Code

**常见改法：**
- 改 SOUL 段落 → 换教练人格
- 改评分标准表 → 适配托福/GRE
- 改模式表 → 加新的工作流
- 改边界段 → 调整 skill 之间的分工

---

## 为什么是无状态的

这是 v1.0。设计原则：**最小可用、最少依赖、最低门槛**。

无状态意味着：
- ✅ 你不用装 Node.js、Python、数据库
- ✅ 每次对话独立，没有"忘记上次说了啥"的烦恼
- ✅ skill 文件夹拷走就能用，没有迁移成本
- ❌ 不记录批改历史
- ❌ 没有进度追踪
- ❌ 没有图表

如果你需要进度追踪、错题本、可视化 dashboard，那是下一个版本要解决的事。

---

## License

[MIT](./LICENSE)

随便用、随便改、随便商用。注明出处不强制但欢迎。

---

## 反馈

发 [issue](https://github.com/YANZHANLIN/ielts-claude-skills/issues) 或者 PR。
