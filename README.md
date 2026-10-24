# 短篇小说写作 skill

面向**原创与同人短篇小说**的 AI 写作 skill，也适用于独立场景和局部故事。从构思、搭建骨架、展开人物行动与心理，到成文、审稿和按反馈改稿，围绕一个核心情节与一组关键情感变化推进。

你可以从一个念头、一份人物设定、一张大纲或一篇已有稿件开始。技能按当前材料和委托范围接续工作；写作经验保留来源、适用范围与具体案例，方便回看和修正。

当前版本 **v0.1.0**（2026-10-24 首次公开发布）。变更、分发范围与已知缺口见 [CHANGELOG](CHANGELOG.md)。外部用户完整试用和同条件对照尚未完成，现阶段不承诺稳定优于其他写作方法；0.x 期间结构与规则可能调整。

本项目自有内容采用 [CC BY-NC-SA 4.0](LICENSE)：署名、非商业、相同方式分享。第三方人物、引用与投稿作品另按 [NOTICE](NOTICE.md) 和各自授权处理；本协议不自动适用于使用技能生成的独立作品。

## 安装

把**整个仓库目录**放进客户端的 skills 目录，目录名保持 `short-story-writing`。只复制 `SKILL.md` 会缺 `references/`、`knowledge/`、`experience/`，技能跑不完整。

| 客户端 | 目录 | 调用 |
| --- | --- | --- |
| Claude Code | `~/.claude/skills/short-story-writing` | 说"用 short-story-writing 写……" |
| Codex | `~/.codex/skills/short-story-writing` | `$short-story-writing` |
| DSH | `~/.agents/skills/short-story-writing` | `$short-story-writing` |

装完新开一个会话（不要用当前会话），确认目录里有 `SKILL.md` 和 `references/style-guidance.md`，再试一句委托。

## 第一次用

说明想写的人物或处境、已有材料，以及这次需要的范围：构思、骨架、正文、审稿或改稿。已有稿件可以直接附上，并指出需要保留的段落、事件或结局；已知信息会从材料里提取。

| 从哪里开始 | 可以补充什么 |
| --- | --- |
| 原创短篇 | 人物想得到什么、遇到什么阻力，已有的世界设定与叙述视角 |
| 同人短篇 | 原作、角色、故事阶段或剧透边界，以及本篇采用的额外设定；作品不限于《BanG Dream!》 |
| 已有稿件 | 正文、目前最想解决的问题、允许修改的范围和必须保留的内容 |

例如：

- 原创：“用 short-story-writing 写一篇现实题材短篇。夜班便利店员想在交班前退还一笔多收的钱，顾客却一直没有回来。先给骨架。”
- 同人：“用 short-story-writing 写我指定作品的两位角色，时间放在原作结局后，保持既有关系。这次先讨论三种可能的矛盾。”
- 改稿：“用 short-story-writing 审这篇短篇，重点看人物动机与结尾是否成立，只列问题，先不改正文。”

原创以作者给定的设定为依据；同人按当前作品与阶段核对人物和剧情，资料缺口会明确标出。默认产出目录仍为当前工作区的 `fanfiction-workbench/`，原创与同人都可使用，也可指定其他目录。

## 当前资料与适用范围

写作流程面向短篇小说与局部故事，支持不同题材、不同作品的原创和同人。目前库内的官方人物资料与早期案例主要来自《BanG Dream!》，另有模型拟人资料；这些是现有素材的覆盖范围，后续可按需要补充其他作品或原创设定。具体人物资料与成熟度见[人物总表](knowledge/roster.md)。

当前关注单篇或局部单元的矛盾演化、人物互动、文字表达与收束；长篇和连载的多线规划仍需另外设计。

公开署名为黄晓黑。原始材料、近期工作稿与原始测试生成稿仅本地使用；公开版保留获准引用的作者原话和经验分析，过滤内部聊天标识、本机绝对路径与学号邮箱。分发边界见[公开分发说明](references/public-distribution.md)。

写作材料默认留在本地，不自动发布；[AI参考稿件](AI参考稿件/README.md) 的投稿完全可选。

---

### 维护速查

| 你想做什么 | 去哪个文件 | 改什么 |
| --- | --- | --- |
| 新增一篇稿件 | [文本目录](knowledge/texts/index.md)、[登记模板](assets/text-record.md) | 分配下一个W编号；原文放同编号texts目录，经验使用同编号作品文件 |
| 自愿贡献一篇参考稿 | [AI参考稿件](AI参考稿件/README.md) | 将同一篇的brief.md与manuscript.md放在独立子目录，通过PR投稿；完全可选 |
| 补一条作者批注 | [作品目录](experience/index.md)中的该篇文件 | 在该篇补判断与定位；新收到的原始消息另存版本，已有原稿保持原样 |
| 改一条规则 | [规则总表](references/style-guidance.md) | 只改对应R编号行的用法、范围或状态；具体例子写回该篇 |
| 跑一次对照实验 | [评估入口](test/README.md) | 按实验README固定模型与提示词；来源、参数、原始评价一起存档 |
| 查人物官方设定 | [总表](knowledge/roster.md)、[祥子](knowledge/characters/sakiko.md)、[睦](knowledge/characters/mutsumi.md)、[都子](knowledge/characters/miyako.md)、[薇欧拉](knowledge/characters/viola.md) | 先看总表状态；查来源与阶段；核到新事实时补来源 |
| 查或补模型拟人 | [总表](knowledge/roster.md)拟人节、[共用框架](knowledge/personas/_contract.md)、[DeepSeek](knowledge/personas/deepseek.md) | 外形与外号先查社群来源并署名；采用版本由作者定 |
| 判断一句话是谁说的 | [证据标签](SKILL.md#证据标签)，再看该篇的判断来源列 | 检查[作者]/[AI]/[来源]及原始材料链接；缺归属时补来源 |
| 回滚一次维护 | [回滚说明](#回滚) | 找到要撤销的提交，检查差异后用git revert生成反向提交 |
| 查旧编号或合并去向 | [编号与合并对照](maintenance/migration-map.md) | 旧编号只用于检索；现行资料使用W/N/R编号 |
| 核验迁移完整性 | [验收记录](maintenance/acceptance.md)、[原稿哈希（仅本地）](references/public-distribution.md#local-materials) | 对照文件、哈希及逐项批注清单 |

### 常用直达

- [人物总表：采样范围与状态](knowledge/roster.md)
- [R006 当前用法](references/style-guidance.md#r006)
- [全部作品与过程记录](experience/index.md)、[规则总表](references/style-guidance.md)
- [评估流程](test/README.md)、[待办](<TODO list.md>)、[现状与规划](maintenance/2026-10-21-status-and-plan.md)

### 层级矩阵

| 范围 × 材料层 | 知识层 | 结构层 | 文字层 |
| --- | --- | --- | --- |
| 单篇 × 原始材料 | texts/W编号：原稿中的设定与原始批注 | 同份原稿：事件、大纲 | 同份原稿：原句、改句 |
| 单篇 × 经验 | works/W编号：本篇设定、待核事实 | 同文件：意图、矛盾、转折结论 | 同文件：批注、具体改法、正反例 |
| 单篇 × 规则 | 规则表中标单篇的R条目，引用该篇证据 | 同左 | 同左 |
| 整体 × 原始材料 | characters/plots/research：官方来源；personas：作者确立的拟人设定；texts/history：历史消息 | texts/history：原始结构要求 | texts/history：原始文字要求 |
| 整体 × 经验 | notes：跨篇人物线索 | records/N编号：编辑过程；结构指南：操作步骤 | records/N编号：编辑过程；文字指南：操作步骤 |
| 整体 × 规则 | style-guidance中R条目的知识与归属要求 | 同表结构条目 | 同表文字条目 |

W是作品或独立写作片段，N是过程记录，R是全部规则；候选与已确认使用状态区分，确认后保留编号。一个作品文件集中存放结论、意图、笔记和批注。原稿只在texts保留原始字节。现行文件名使用 `编号-英文短名.md`；texts目录沿用同一编号与短名，版本用original/revision/annotated/excerpts命名。跨篇说明文件使用英文短横线命名。

同一指南内，每篇案例只列一个入口，相关批注号与用途合并在该处；人物卡只链接作品文件，由作品文件连接原稿和本篇意图。

### 工作入口

调用名为 `$short-story-writing`。[SKILL](SKILL.md)负责执行流程；[存稿](references/manuscript-archive.md)、[经验回流](references/experience-loop.md)、[知识核对](references/knowledge-workflow.md)按任务读取。

### 自愿分享作品

如果你觉得使用 skill 写出的这篇文章还可以，欢迎把本篇简报 `brief.md` 和正文 `manuscript.md` 一起投稿到 [AI参考稿件](AI参考稿件/README.md)。任何使用者都可以参与，也可以只在本地保留作品；投稿完全可选。目录按篇收纳，具体格式和提交方法见目录说明。

### 回滚

1. 用 `git status --short` 检查尚未提交的修改，先保存需要保留的工作。
2. 用 `git log --oneline` 找到提交，再用 `git show <提交号>` 核对其范围。
3. 用 `git revert <提交号>` 生成反向提交；发生冲突时核对相关文件后继续。

写作材料默认私人本地保存，自愿投稿按上述说明公开提交。公开仓库从 v0.1.0 最终审核的文件建立独立根提交，本机维护历史与旧私有仓库对象均不导入；回滚只针对公开仓库中的提交。[完整文件清单](maintenance/file-inventory.md)用于盘点。
