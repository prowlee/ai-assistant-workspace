# AI助手工作区

这是专属于您的AI助手工作区。

这是一个入门套件，旨在将AI编码工具（Claude Code / Codex CLI / Gemini CLI）用作您的个人助手。首次启动时，将通过对话形式为您创建专属助手。

这也是 [xangi](https://github.com/karaage0703/xangi)（常驻Discord的AI助手）的推荐工作区。与xangi结合使用，可以通过聊天调用技能，实现日常任务的自动化。

## 功能特性

- **笔记管理** — 整理并保存调研结果、想法、会议记录
- **日记** — 与Notion联动，管理日常记录
- **猫咪日记** — 发送猫咪照片即可自动识别并记录到Notion
- **Notion联动** — 搜索、创建页面，上传文件
- **语音转文字** — 将音频文件转换为文本
- **播客** — 下载并总结播客内容（内置预设节目）
- **YouTube** — 将YouTube视频内容整理成笔记
- **制作演示文稿** — 从Markdown生成幻灯片
- **科技新闻** — 收集并介绍最新的AI及技术新闻
- **arXiv论文调研** — 集成执行论文搜索、发现趋势、详细分析
- **代码审查** — 使用多AI（Claude/Codex/Gemini）对PR进行系统性审查
- **GitHub仓库分析** — 分析仓库结构和技术栈
- **工作区搜索** — 通过向量搜索跨文件检索内容
- **日历** — 查看ICS日历（如Google日历）的日程安排
- **健康管理** — 记录饮食、运动并获取健康建议
- **设置更改** — 通过聊天更改AI助手的设置（使用xangi时）
- **主动聊天** — AI会主动发起对话（基于概率判断+支持cron）
- **创建技能** — 打造您自己的自定义技能

## 快速开始

### 准备工作

- 安装 [Claude Code](https://docs.anthropic.com/en/docs/claude-code/overview)、[Codex CLI](https://github.com/openai/codex) 或 [Gemini CLI](https://github.com/google-gemini/gemini-cli) 之一
- 如需在Discord中使用: 需要 [xangi](https://github.com/karaage0703/xangi)

### 设置步骤

```bash
# 1. 克隆仓库
git clone https://github.com/karaage0703/ai-assistant-workspace
cd ai-assistant-workspace

# 2. 启动AI工具（任选其一）
claude          # 使用 Claude Code 时
codex           # 使用 Codex CLI 时
gemini          # 使用 Gemini CLI 时

# 3. 自动设置开始
# AI会向您提问，并为您创建专属助手
```

对于 Claude Code，仓库中已包含从 `.claude/skills` 到 `skills/` 的符号链接，因此克隆后即可直接使用技能。

## 目录结构

```
ai-assistant-workspace/
├── AGENTS.md              # 配置文件（所有工具通用）
├── CLAUDE.md              # → 指向 AGENTS.md 的符号链接
├── GEMINI.md              # → 指向 AGENTS.md 的符号链接
├── BOOTSTRAP.md           # 用于首次设置（设置完成后将被删除）
├── .claude/
│   └── skills -> ../skills  # Claude Code 用的符号链接
├── .agents/
│   └── skills -> ../skills  # Codex CLI 用的符号链接
├── .gemini/
│   └── skills -> ../skills  # Gemini CLI 用的符号链接
├── memory/                # 日记、笔记的保存位置
├── notes/                 # 笔记、调研记录的保存位置
└── skills/                # 技能（AI的扩展功能）
    ├── calendar/          # 日历技能
    ├── cat-diary/         # 猫咪日记技能
    ├── diary/             # 日记技能
    ├── arxiv/             # arXiv论文调研技能
    ├── code-reviewer/     # 代码审查技能
    ├── github-repo-analyzer/ # GitHub仓库分析技能
    ├── health-advisor/    # 健康管理技能
    ├── marp-slides/       # 幻灯片制作技能
    ├── note-taking/       # 笔记管理技能
    ├── notion-manager/    # Notion联动技能
    ├── podcast/           # 播客技能
    ├── skill-creator/     # 创建技能技能
    ├── tech-news-curation/# 科技新闻技能
    ├── transcriber/       # 语音转文字技能
    ├── spontaneous-talk/  # 主动聊天技能
    ├── workspace-rag/     # 工作区搜索技能
    ├── xangi-settings/    # xangi设置更改技能
    └── youtube-notes/     # YouTube笔记技能
```

## 使用技巧

### 记笔记
```
“帮我总结一下调研结果”
“保存会议记录”
“告诉我最近的笔记”
```

### 写日记
```
“写一下今天的日记”
“到写日记的时间了”
```

### 记录猫咪日记
```
[发送猫咪图片]
→ AI会自动检测猫咪并记录到Notion

“这周的猫咪最佳照片”
```

### 制作演示文稿
```
“做一个关于AI历史的5页幻灯片”
“根据这个笔记制作演示文稿”
```

### 调研arXiv论文
```
“查找关于LLM代理的最新论文”
“告诉我这周的AI趋势论文”
“详细分析一下论文 2401.12345”
```

### 审查PR
```
“审查一下PR #123”
“对 owner/repo 的 PR #45 进行代码审查”
```

### 分析GitHub仓库
```
“分析一下这个仓库: owner/repo”
“看一下 https://github.com/owner/repo”
```

### 收听播客
```
“总结一下播客的最新一期”
```

### 查看科技新闻
```
“告诉我今天的科技新闻”
```

### 查看日历
```
“今天的日程安排”
“确认一下这周的日程”
```

### 健康管理
```
“记录饮食：拉面”
“这周的健康报告”
```

### 创建自己的技能
```
“创建一个管理读书笔记的技能”
```

## 自定义

### 改变AI的性格

编辑 `AGENTS.md` 中的“关于我自己”部分，可以改变AI的说话方式和性格。

### 添加技能

只需在 `skills/` 目录下创建文件夹，并编写 `SKILL.md` 文件，即可添加新技能。详情请参考 `skills/README.md`。

## 许可证

MIT License
