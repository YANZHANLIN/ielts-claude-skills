# IELTS Claude Code Skills

5 个自建 Claude Code Skill，覆盖雅思听说读写全科备考。

**成绩：听力 8.0 ｜阅读 8.0 ｜写作 7.0 ｜口语 7.0 ｜总分 7.5**
**备考：2个月，每天2小时，花了230元**

---

## Skills

| 命令 | 功能 |
|------|------|
| `/ielts` | 入口，路由到具体 Skill |
| `/ielts-diagnose` | 成绩诊断 + 弱项定位 + 8周个人计划 |
| `/ielts-writing` | 四维批改（TR/CC/LR/GRA）+ 改写对比 + 审题模式 |
| `/ielts-reading` | 同义替换词表 + T/F/NG 逻辑拆解 + 错题分析 |
| `/ielts-speaking` | 话题分组 + 万能故事生成 + Part 3 追问预测 |

## 安装

```bash
# 方法1：Claude Code Skill 安装命令
claude skill install YANZHANLIN/ielts-claude-skills

# 方法2：手动复制
git clone https://github.com/YANZHANLIN/ielts-claude-skills.git
cp -r ielts-claude-skills/ielts* ~/.claude/skills/
```

## 配合使用的工具

- **Claude Code** — 运行 Skill 的主环境
- **NotebookLM** — 生成英文播客磨耳朵
- **Gemini Live / ChatGPT 语音** — 模拟口语考官
- **剑桥真题** — 诊断和练习素材

## 备考流程

```
第1天：做一套剑桥真题 → /ielts-diagnose 出个人计划
  ↓
每天：听力60min精听 + 阅读60min + 口语30min
  ↓
每3天：写一篇Task 2 → /ielts-writing 四维批改
  ↓
8周后：上考场
```

## 详细教程

→ [CC+NotebookLM 每天2小时 不报班自学雅思7.5](https://zhanlinyan.com/resources/ielts-ai-self-study)

## License

MIT
