包含哪些技能？
产品决策链（BRD → MRD → PRD → Code）
这是最核心的一条流程，覆盖了从“我有一个想法”到“AI Agent可以开始写代码”的全流程：
/product-insight-miner → 采集用户原声（可选，没数据时推荐先跑）
  ↓
/brd → 评估方向值不值得做 → BRD.md（含数据索引 + 交接区）
  ↓ 自动继承
/mrd → 深入分析市场需求 → MRD.md（含 P0/P1/P2 优先级 + 数据索引）
  ↓ 自动继承
/vibe-prd-writer → 生成完整项目规范 → PRD/ 文件夹（10 模块 + README 导航）
  ↓ 投喂
Claude Code / Cursor 读 PRD/README.md 开始编码

技能	解决什么问题	触发方式
产品洞察挖掘器	没有数据，想知道用户在抱怨什么	“帮我挖掘用户痛点”、“去三个平台看看”
brd 🆕	有想法但不确定值不值得做	“帮我评估这个方向”、“这个能不能做”
mrd 🆕	方向确认了，需抑制市场需求	“帮我写MRD”、“从用户反馈里提炼需求”
vibe-prd-writer 🔄	需求明确了，要出一份AI代理能执行的项目规范	“帮我写一个PRD”、“我尝试一个XX”
ai-agent-prd-writer	正式PRD的工作场景（给开发团队看）	《帮我写正式的需求文档》

能力建设及入职加速
技能	解决什么问题	典型使用场景
人工智能产品拆解	面试前拆解目标公司产品、入职后理解竞品	《帮我拆解一下光标》
48小时加速学习	短时间搞懂一个陌生领域	《帮我48小时搞懂多模态》
互动式学习	系统深入研究某个知识点	“我想搞懂 RAG 的原理”
simin-article-cowriter	写干货长文、内容共创	“帮我写一篇关于AI Agent的文章”

从想法到产品（Vibe Coding）
1. 挖需求 → product-insight-miner（从小红书/X/Reddit 挖掘用户痛点）
2. 判方向 → brd（评估值不值得做，跑爬虫补数据）
3. 理需求 → mrd（梳理 P0/P1/P2 需求优先级）
4. 出规范 → vibe-prd-writer（生成 PRD/ 文件夹，直接喂给 AI Agent）
5. 写代码 → 把 PRD/ 丢进 Claude Code / Cursor 开干
