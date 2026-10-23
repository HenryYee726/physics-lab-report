# Physics Lab Report

用 Codex 根据原始实验数据和现成 Word 表格，完成大学物理实验的英文 postlab report。

本项目包含报告 skill、参考教材、写作要求和带水印的长短报告模板。使用同一课程材料时，每次实验只需加入 **手写原始数据** 和 **对应的 Word 数据表格**，然后告诉 Codex 实验名称及报告类型。

## 快速开始

### 1. 下载并打开整个项目

在 GitHub 点击 **Code → Download ZIP** 并解压，或使用 Git 克隆仓库。用 Codex 打开解压后的项目根目录，确保能看到 `template/`、`lab/` 和 `参考教材.pdf`。

请保留 `.agents/` 隐藏文件夹，其中保存了项目 skill。只下载 `SKILL.md` 会缺少教材和报告模板。

这是需要 Codex 执行的工作流程，不是独立运行的报告生成程序。Codex 环境需要能读取文件、处理 Word/PDF、查看图片并渲染文档；推荐使用提供 Documents 和 PDF 技能的环境。报告生成过程中，Codex 可能需要配置当前环境的文档处理依赖。

### 2. 放入本次实验的两个材料

在 `lab/` 中为每次实验创建文件夹，例如：

```text
lab/lab1/
├─ 原始数据.jpg
└─ 数据表格.docx
```

- 原始数据可以是多张照片或扫描 PDF，必须能看清读数、单位和完整表头。
- 数据表格应是与本次实验、教材一致的可编辑 Word 表格；可以是空表，也可以已有本次实验数据。不要使用其他人的测量数据代替自己的记录。
- 文件名可以不同，也可以加入已有的 prelab 作为补充材料，但它不是必需文件。

### 3. 发送生成指令

例如：

```text
使用 $physics-lab-report，根据 lab/lab1 的原始数据和 Word 表格，
完成 Measuring Laser Wavelength and Index of Refraction of Air
by Michelson Interferometer 的 long postlab report。
```

短报告把 `long` 换成 `short`。姓名、学号、教师、实验日期如果未包含在材料中，可在同一条消息里提供；不确定的信息不会自动猜测。

Codex 支持从项目的 `.agents/skills/` 读取技能，见 [OpenAI 官方技能说明](https://learn.chatgpt.com/docs/build-skills)。如果当前界面没有识别 `$physics-lab-report`，可以明确要求：“读取并使用 `.agents/skills/physics-lab-report/SKILL.md` 完成本次报告。”

### 4. 获取报告

最终 Word 文档保存在本次 `labX` 文件夹中，默认命名为：

```text
姓名+学号+实验名称+postlab.docx
```

原始教材、模板、记录照片和表格保持不变。默认交付 DOCX；需要 PDF 时可在指令中提出。提交前请核对自己的原始读数和实验信息。

## 项目结构

```text
physics-lab-report/
├─ .agents/skills/physics-lab-report/SKILL.md
├─ AGENTS.md
├─ README.md
├─ .gitignore
├─ 参考教材.pdf
├─ template/
│  ├─ Writing a lab report-Appendix 1.pdf
│  ├─ Template for long report.docx
│  └─ Template for short report.docx
└─ lab/
   ├─ README.md
   └─ lab1/
      └─ .gitkeep
```

## 报告会怎样完成

1. 先读写作要求，再读取指定的长报告或短报告模板。
2. 查看本次手写数据和 Word 数据表格。
3. 先读教材目录，再定位实验章节；不全文提取、OCR 或渲染整本教材。
4. 按教材完成计算、结果讨论和 postlab questions，最后写摘要。
5. 从模板副本编辑，保留水印、评分栏及原有样式；直接复制提供的 Word 表格。
6. 将手写原始记录实际插入 Appendix，公式经 LaTeX 转换并渲染，逐页检查最终版式。

文字采用本科生实验报告语气。读数疑问、缺失信息和文件制作备注放在聊天中，不混进 report 正文。遇到影响计算的材料问题，Codex 会先提出具体问题。

## 本地数据与课程材料

`lab/` 中新增的个人数据和生成报告默认被 Git 忽略，方便每位使用者独立完成实验。仓库不包含发布者的个人报告、学号、实验照片或已填写的数据表。

教材及模板是本项目所使用的课程材料，保留其原有作者信息和水印；第三方材料的权利归原作者，本仓库不为其另行授予许可。参考教材为付浩等编写的《大学物理实验》英文版，科学出版社，2017，ISBN 9787030514073。其他课程可用自己的教材和模板替换，但应重新核对课程写作要求。
