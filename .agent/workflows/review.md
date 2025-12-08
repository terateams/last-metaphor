---
description: 对指定文件执行结构化评审 (Structural Audit Review)
---

1. 确认用户希望评审的具体文件 (Target File)。如果用户在命令中未指定 (例如 `/review chapters/01/05.md`)，则先询问用户。

2. 读取评审标准文件 (Prompt)。
   - [ ] `view_file` .github/prompts/review.prompt.md

3. 读取目标文件 (Target File) 的内容。
   - [ ] `view_file` [Target File Path]

4. 以 "结构审计型编辑" 的身份，严格按照 review.prompt.md 中的维度和格式要求，对目标文件进行评审并输出报告。
