# LLM x 书签收藏：摘要 & 全文索引 - Nekonull's Garden
- URL: https://nekonull.me/posts/llm_x_bookmark/
- Added At: 2024-10-17 10:18:31
- [Link To Text](2024-10-17-llm-x-书签收藏：摘要-&-全文索引---nekonull's-garden_raw.md)

## TL;DR
作者使用osmos::memo插件将书签存入Github，但面临死链接和查找困难。为此，创建bookmark-summary存储库，通过Github Actions自动生成全文、摘要和总结，提升查找效率。未来计划优化摘要质量、结构化数据、重构代码，并探索向量搜索和自动周报生成。

## Summary
1. **背景**：
   - **书签收藏需求**：作者在网上冲浪时经常遇到有趣的文章或网站，希望收藏以备后用。
   - **工具使用**：自2021年5月以来，使用名为[osmos::memo](https://github.com/osmoscraft/osmosmemo)的书签插件，将收藏记录到公开的Github存储库。
   - **工作原理**：设置Github token，每次点击收藏按钮时，浏览器临时clone存储库，追加新条目，生成commit并提交，然后推送回Github。

2. **问题**：
   - **死链接**：书签指向的URL可能不再存在，导致死链接。
   - **查找困难**：记录项只有URL、标题和可选标签，查找时如果关键词记忆不清，可能找不到。
   - **内容遗忘**：长文章时间一久可能忘记内容，通读费时费事，查找和引用效率下降。

3. **解决**：
   - **新存储库**：建立新存储库[bookmark-summary](https://github.com/jerrylususu/bookmark-summary)，作为现有书签存储库的辅助数据，包含Markdown格式全文、列表摘要、一句话总结。
   - **工作原理**：
     1. 通过书签插件在现有存储库新增条目。
     2. 代码提交触发Github Actions（`summarize`）。
     3. Actions执行：
        - 解析书签README.md文件，找到新增条目。
        - 将URL保存到Wayback Machine。
        - 使用[jina reader](https://jina.ai/reader/) API获取网址的Markdown全文，保存到`YYYYMM/{title}_raw.md`。
        - 使用LLM生成列表摘要和一句话总结，保存到`YYYYMM/{title}.md`。
        - 更新摘要存储库的README.md，增加到摘要文件的链接。
   - **代码实现**：主要由Claude和GPT4o编写，人肉调整，使用深度求索的deepseek-chat生成摘要，成本低效果尚可。

4. **未来**：
   - **列表摘要质量**：优化prompt或换用其他模型。
   - **数据结构化**：考虑在Markdown之外维护JSON，便于未来查询。
   - **代码整理和重构**：重构Python文件，改进存储库交互方式。
   - **向量搜索**：考虑接embedding模型生成嵌入，存入SQLite或向量数据库。
   - **自动生成周报**：已完成，每周新增书签、原文、摘要自动生成周报，放在Github Release。
   - **工具链更新**：考虑使用更现代的工具链，如uv。

5. **部署指南**：
   - **初始化书签存储库**：参考[osmos::memo](https://github.com/osmoscraft/osmosmemo)指引，安装浏览器插件并连接到Github。
   - **新建摘要存储库**：添加`process_changes.py`，调整存储库名和prompt。
   - **配置Github Actions**：将`bookmark_summary.yml`添加到书签存储库，替换存储库名。
   - **生成PAT**：创建Personal Access Token，添加到书签存储库的环境变量。
   - **测试**：添加书签，观察工作流是否正常运行，摘要存储库是否生成对应摘要。
6. **笔者新增**：
   - 推荐先试用 deepseek，注册完成有免费额度使用。当然，如果 chatgpt 有充值额度可忽略，否则会出现 429 http code。
   - `bookmark_summary` 存储库在添加 `process_changes.py` 时，同时创建 `data.json` 文件，并且写入内容 `[]`，避免 json 序列化失败.
