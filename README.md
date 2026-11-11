# Paper Reading Notes · 论文精读笔记

一个用于论文精读的 Agent Skill。输入论文 PDF，生成中文 Markdown 解读，讲清研究问题、方法、实验结果和局限。需要配图时，从原文裁切方法图、案例图或结果表，注明图表编号和 PDF 页码。

## 安装

在装有 Node.js 的终端运行以下命令，将 Skill 安装到 Codex 的用户范围。

```sh
npx skills add ylxnn/paper-reading-notes --skill paper-reading-notes --agent codex --global
```

也可以手动把本仓库的 `SKILL.md` 和 `agents/` 复制到 Codex 的用户技能目录下的 `paper-reading-notes/` 文件夹。安装后，在 Codex 对话中用 `$paper-reading-notes` 调用。

## 使用示例

```text
用 $paper-reading-notes 解读 ./papers/Meta-Tool.pdf，保存到 ./notes。
重点讲清楚模型什么时候检索工具、如何排序，以及检索命中率和调用准确率分别测什么。
```

路径可以换成自己的 PDF 和输出目录。生成文件类似：

```text
notes/
├── Meta-Tool 论文解读.md
└── Meta-Tool-原图/
    ├── figure-1.png
    └── table-3.png
```

生成完整笔记需要当前环境能读取 PDF 并写入输出目录。提取原图还需要可用的 PDF 渲染工具。

## 仓库文件

- [SKILL.md](SKILL.md) 定义适用场景、解读流程和交付检查。
- [agents/openai.yaml](agents/openai.yaml) 提供 Codex 界面的显示名称和调用示例。

格式参考 [Agent Skills 规范](https://agentskills.io/specification)。安装参数见 [Skills CLI 文档](https://github.com/vercel-labs/skills/blob/main/docs/commands.md)。
