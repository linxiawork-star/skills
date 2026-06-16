AIPM+技能工具箱
一套为AI产品经理打造的Claude Skills，涵盖从灵感发现、商业判断、需求分析、项目规范到求职的完整流程。

为什么做这套技能？
大多数AI工具要么是通用模板，要么是信息聚合。他们的问题在于：没有针对AI产品经理这个岗位的专业判断力。

比如说你让通用AI帮你改简历，它会帮你把句子写得更漂亮，但不会告诉你“经历应该突出数据闭环而不是功能迭代，因为目标JD要的是有AI音乐体系经验的人”。

这套技能的不同之处：

内置AI PM领域知识：每个技能都内嵌了AI产品经理岗位的能力模型、专业框架
流程驱动提示驱动：触发后 Claude 会按照完整的专业流程主动推进
技能间数据打通：BRD → MRD → PRD → 编码，每一步的结论自动输入给下一步，不重复提问
实战验证：每个技能都经历了多轮真实场景的测试和迭代
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
BRD / MRD 的数据驱动特性
BRD和MRD都严格要求支撑数据：

有数据就用数据：用户粘贴原声 / 上传文件 / product-insight-miner 的拓扑
没数据就跑爬虫：内置 DuckDuckGo 爬虫脚本（brd/scripts/fetch_market_data.py），自动采集并按来源打索引相关（X=Twitter, R=Reddit, Z=知乎, H=小红书...）
所有结论挂索引：核心痛点是信息过载 [X3, R1, W5]，每个索引可回溯到原始数据
禁止捏造：没有数据支撑的数字/比例/比例，一律不写
vivi-prd-writer v2.0 的变化
从《一页纸PRD》升级为完整项目规范：

输出PRD/文件夹（10模块独立文件 + README 导航），AI Agent连续加载，不一次性塞爆上下文
自动继承 BRD.md / MRD.md / DESIGN.md 的数据
第 3 阶段会扫描您已安装的前置设计技能（design-consultation / web-design-pro），避免重复造轮子
三层自检：文件结构分歧 / 各模块内容质量 / 跨文件一致性
目标核心环节
技能	解决什么问题	典型使用场景
ai-pm-简历撰写器	简历不知道怎么写、投了没回音	“帮我针对这个JD调简历”
ai-pm-访谈-诊断	面试完成不知道问题在哪、不知道怎么准备下一场	《帮我分析这个面试录音》
能力建设及入职加速
技能	解决什么问题	典型使用场景
人工智能产品拆解	面试前拆解目标公司产品、入职后理解竞品	《帮我拆解一下光标》
48小时加速学习	短时间搞懂一个陌生领域	《帮我48小时搞懂多模态》
互动式学习	系统深入研究某个知识点	“我想搞懂 RAG 的原理”
simin-article-cowriter	写干货长文、内容共创	“帮我写一篇关于AI Agent的文章”
知识沉淀
技能	解决什么问题	典型使用场景
黑曜石知识保存器	和克劳德聊完就忘了、知识散落各处	“帮我沉淀到知识库”、“lint 一下知识库”
v2.0 重构：存的是知识点不是对话记录，同一知识点只有一条笔记（更新补充新增），整理的活 LLM 干。支持沉淀 / 消化 / 健康检查 / 初始化四种模式。理念来自 Zettelkasten + Karpathy 的 LLM Wiki 模式。

快速开始
第一步：安装 Claude Desktop 或 Claude Code
Claude桌面：前往claude.ai/download下载，开启Cowork模式
Claude Code（CLI）：npm install -g @anthropic-ai/claude-code
第二步：安装技巧
方式A：手动安装（推荐）

点击本仓库页面的绿色代码按钮 →下载ZIP，解压
把你要的技能文件夹复制到~/.claude/skills/下
重启Claude Code或开启新对话即可生效
方式B：Cowork模式安装（Claude Desktop）

在Cowork模式下，点击技能→添加技能
选择您要安装的技能文件夹
第三步：直接用自然语言触发
不需要记下任何命令。直接跟克劳德说你尝试的事：

"这个方向值不值得做"          → BRD
"帮我梳理市场需求"            → MRD
"帮我写个 PRD"               → vibe-prd-writer
"帮我挖掘用户痛点"            → product-insight-miner
"帮我拆解一下 Kimi"           → ai-product-teardown
"帮我针对这个 JD 改简历"      → ai-pm-resume-writer
"帮我分析这个面试录音"        → ai-pm-interview-diagnosis
"帮我 48 小时搞懂多模态"      → 48h-accelerated-learning
"我想搞懂 RAG"               → interactive-learning
"沉淀到知识库"                → obsidian-knowledge-saver
使用推荐路径
路径A：从想法到产品（Vibe Coding）
1. 挖需求 → product-insight-miner（从小红书/X/Reddit 挖掘用户痛点）
2. 判方向 → brd（评估值不值得做，跑爬虫补数据）
3. 理需求 → mrd（梳理 P0/P1/P2 需求优先级）
4. 出规范 → vibe-prd-writer（生成 PRD/ 文件夹，直接喂给 AI Agent）
5. 写代码 → 把 PRD/ 丢进 Claude Code / Cursor 开干
路径B：AI PM 求职
1. 速成领域 → 48h-accelerated-learning（48 小时建立认知全景图）
2. 补知识 → interactive-learning（深入搞懂 RAG、Agent、评测体系）
3. 看产品 → ai-product-teardown（拆解目标公司的 AI 产品）
4. 攒作品 → ai-agent-prd-writer（写出能拿得出手的 AI PRD）
5. 写简历 → ai-pm-resume-writer（针对目标 JD 打磨简历）
6. 打面试 → ai-pm-interview-diagnosis（面试后复盘、面试前备战）
7. 全程沉淀 → obsidian-knowledge-saver（知识卡片持续积累）
入职之后，路径A的产品决策链继续帮助做市场调研、需求分析和项目规划。

依赖关系
BRD / MRD 爬虫功能：需要pip install requests beautifulsoup4（首次使用时技能会提醒）
obsidian-knowledge-saver：依赖 Desktop Commander MCP 工具进行本地文件读写
其他技能无需额外依赖
关于
这些技能是在真正的 AI PM产品实践中，将遇到的痛点提炼成可复用的工具。它们并不完美，但每个人都解决了真正遇到的问题。
