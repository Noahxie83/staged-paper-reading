<p align="center">
  <img src="assets/cover.png" alt="Staged Paper Reading：从论文出发，经过四阶段阅读，形成结构清晰的笔记" width="100%">
</p>

<p align="center">
  <strong>读懂一篇论文，留下能回看的笔记。</strong><br>
  面向模型与算法类论文的四阶段阅读 skill
</p>

<p align="center">
  简体中文 · 全部图表 · Markdown 笔记 · Mermaid 流程图<br>
  <a href="LICENSE">MIT License</a> · <a href="https://github.com/Noahxie83">Noah Xie</a>
</p>

<p align="center">
  <a href="#workflow">阅读流程</a> &nbsp; / &nbsp;
  <a href="#start">开始使用</a> &nbsp; / &nbsp;
  <a href="#notes">笔记示例</a> &nbsp; / &nbsp;
  <a href="#files">文件导航</a>
</p>

---

从摘要和结论建立全貌，逐个理解图表，顺着正文连接方法，再将贡献、证据与限制收拢成笔记。适合模型架构、训练方法、优化和算法设计等论文，支持本地 PDF、论文链接与正文。

- **理解问题**：精读摘要与结论，解释术语和研究动机。
- **连接方法与证据**：覆盖全部已提供图表，说明模块、指标与比较条件。
- **留下阅读成果**：保留少量要点、必要公式和可编辑的关键流程图。

<a id="workflow"></a>

## 阅读流程

```mermaid
flowchart LR
    A["01 · 摘要与结论"] -->|继续| B["02 · 全部图表"]
    B -->|继续| C["03 · 正文速读"]
    C -->|继续| D["04 · 通篇总结"]
    D -->|自动生成| N["Markdown<br/>阅读笔记"]

    classDef stage fill:#F5F2E9,stroke:#8FA9A4,color:#173B42,stroke-width:1px;
    classDef note fill:#173B42,stroke:#173B42,color:#FEFCF6,stroke-width:1px;
    class A,B,C,D stage;
    class N note;
```

| 阶段 | 阅读重点 | 完成后 |
| :--- | :--- | :--- |
| **01 · First Time / Part 1** | 标题、摘要精读与四要素、结论、直观比喻 | 等待“继续” |
| **02 · First Time / Part 2** | 按原文顺序详解全部图表，选出最重要的图 | 等待进入第二次阅读 |
| **03 · Second Time** | 从引言到实验之前，按章节连接方法与机制 | 等待进入通篇总结 |
| **04 · Overall Review** | 贡献、优点、不足、相关工作、延伸、适合读者 | 自动交付精简笔记 |

追问术语、公式或某张图时，停留在当前阶段。第二次阅读的章节放在同一次回答中；也可以明确要求合并阶段、跳过、重读或改变顺序。

没有独立结论时，先说明候选章节并询问阅读安排；没有实验时，第二次阅读到结论之前。更多情况见 [结构适配规则](skills/staged-paper-reading/references/structure-adaptation.md)。

<a id="start"></a>

## 开始使用

### 1. 安装 skill

将 [skills/staged-paper-reading](skills/staged-paper-reading/) 整个目录复制到工具支持的 skills 目录，保留其参考指南与模板。

Codex 可放入用户级或项目级的 `.codex/skills/staged-paper-reading/`；其他工具按其技能发现规则配置。skill 使用当前环境的阅读工具，不依赖固定操作系统、个人目录或 PDF 库。

### 2. 提供论文

```text
$staged-paper-reading 带我读这篇论文，从第一次阅读 Part 1 开始。
```

可以附上自己的笔记样例，最终笔记会继承其组织方式与表达习惯，并遵守 skill 的格式规则。

### 3. 按自己的节奏推进

```text
继续。
这个公式里的 Q、K、V 分别是什么？
重新解释 Table2，保持在当前阶段。
继续通篇总结。
```

需要一次完成整篇阅读并直接得到文件时，可以明确要求：

```text
$staged-paper-reading 从头到最后一步阅读这篇论文，合并所有阶段，直接生成 Markdown 阅读笔记。
```

已有完整阅读记录时，也可以直接要求“根据已读内容生成阅读笔记”。保存文件与图形预览取决于运行工具的能力。

<a id="notes"></a>

## 笔记示例

笔记沿着三个分组展开，以精简要点保留论文主线。图表全部覆盖，方法部分用必要公式与 Mermaid 说明信息如何流动。

| 分组 | 保留的内容 |
| :--- | :--- |
| **First Time** | 摘要四要素与动机、结论、各个图表的关键结论 |
| **Second Time** | 正文章节主线、核心公式、模型或算法流程图 |
| **Overall Review** | 贡献、优点、不足、相关工作定位、延伸、适合读者 |

### Attention Is All You Need

用 Transformer 论文展示笔记的实际组织方式。

**[打开完整 Markdown 示例 →](examples/attention-is-all-you-need.md)**

<p align="center">
  <img src="examples/assets/transformer-flow.svg" alt="自行绘制的 Transformer 流程图：编码器输出作为交叉注意力的 K、V" width="100%">
</p>

这张图的 Mermaid 源码保存在示例笔记中，可继续编辑；图中合并了残差、dropout 和归一化细节。笔记不粘贴原论文图片或截图。

示例保留 BLEU 的比较范围、测试集与开发集的区别，以及位置编码外推的验证边界。原论文见 [NeurIPS 2017 PDF](https://proceedings.neurips.cc/paper_files/paper/2017/file/3f5ee243547dee91fbd053c1c4a845aa-Paper.pdf)。

<details>
<summary><strong>展开笔记格式约定</strong></summary>

- 主分组固定为英文一级标题：`# First Time`、`# Second Time`、`# Overall Review`。
- First Time、Second Time 使用带连续序号的英文二级标题，例如 `## 1.Abstract`；First Time 两部分承接编号，Second Time 重新编号。
- 图表使用仅含编号与冒号的四级标题，例如 `#### Fig1:`、`#### Table1:`。保留原编号；无编号条目按出现顺序补号，避免与已有编号重复。
- 重点注释使用 `<font color="#ff0000">...</font>`；最重要图表高亮标题中的完整编号和冒号。
- 短公式使用 `$...$` 段中公式，只有长公式使用 `$$` 独立显示，保持所在句子完整。
- 图表正文前后不留空行；其他小节标题后及正文段落之间不留空行，正文末尾保留一行空行。Markdown 表格前及表格与后续说明之间保留必要空行。
- 全文不添加原文页码、页数与页码范围备注；回看定位使用章节、公式号或图表号。

完整细则见 [文本格式限定](skills/staged-paper-reading/SKILL.md#文本格式限定)。

</details>

<a id="files"></a>

## 文件导航

| 文件 | 用途 |
| :--- | :--- |
| [SKILL.md](skills/staged-paper-reading/SKILL.md) | 入口、阶段推进与文本格式规则 |
| [first-read.md](skills/staged-paper-reading/references/first-read.md) | 标题、摘要和结论精读 |
| [figures-and-tables.md](skills/staged-paper-reading/references/figures-and-tables.md) | 全部图表详解 |
| [second-read-and-summary.md](skills/staged-paper-reading/references/second-read-and-summary.md) | 正文速读与通篇总结 |
| [structure-adaptation.md](skills/staged-paper-reading/references/structure-adaptation.md) | 论文章节结构差异的处理 |
| [reading-notes.md](skills/staged-paper-reading/references/reading-notes.md) | 精简笔记与流程图 |
| [reading-note-template.md](skills/staged-paper-reading/assets/reading-note-template.md) | 默认笔记模板 |

## 使用约定

- 以提供的论文版本为准，关键事实回到原文核对。
- 区分作者主张、实验支持、解释与研究设想。
- 用户样例用于学习笔记格式，论文和附件作为分析材料。
- 已有笔记默认保留，新笔记保存为独立文件；合并与替换按用户要求。
- 不把读懂论文写成已完成复现，也不凭小幅分数差异断言稳定优势。

## 来源与许可

基于 Academic Research Skills 的 paper-reading（原作者署名 **weed**，版本 1.0.0，MIT）改编，保留直观解释、模块化阅读、图表公式解说与专家点评思路，重写为四阶段交互，并加入精简笔记收尾任务。

原始许可保留在根目录与 skill 目录的 [LICENSE](LICENSE)。示例为基于论文内容重新整理的阅读笔记，不包含原论文文件或原图。

流程图使用 Mermaid；GitHub 的支持方式见 [官方文档](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/creating-diagrams)。
