# awesome-n8n-agent-workflows [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of n8n workflows for AI Agents — with OpenClaw/MCP integration guides and safety labels for irreversible operations.

![workflows](https://img.shields.io/badge/workflows-258-blue)
![updated](https://img.shields.io/badge/updated-2026-03-green)
![license](https://img.shields.io/badge/license-MIT-orange)

### Who is this for?

- Builders using **n8n as the execution layer for AI agents** (OpenClaw, MCP, custom orchestrators).
- Indie hackers and teams who want **real, working automations**, not just prompts.
- People exploring how **AI agents + workflows** behave in production.

Recently I started deploying OpenClaw in my own stack and realised how well it pairs with n8n:  
OpenClaw handles the reasoning and tools, while n8n provides a stable, visual execution layer with retries, logging, and integrations.  
This list collects the n8n workflows that work especially well in that combo.

[中文版](README.zh.md)

## ⚠️ Before You Use

- MCP Server workflows grant AI Agents direct execution permissions — review carefully before mounting
- The **OpenClaw** column shows a ready-to-use natural language instruction you can paste into OpenClaw so an AI Agent knows how to call that n8n workflow.
- All workflows require API key configuration — never expose a credentialed n8n instance to the public internet
- Community-sourced workflows are not independently verified — test in a sandbox environment first
- Workflows marked ⚠️ contain irreversible operations (send / delete / publish) — use with caution
- Comply with the Terms of Service of Gmail, WhatsApp, Google Drive, and other third-party platforms

## 🤖 OpenClaw Quickstart

Install the n8n skill:

npx playbooks add skill openclaw/skills --skill n8n

text

Configure your n8n instance:

{
"skills": {
"n8n": {
"env": {
"N8N_API_KEY": "your-api-key",
"N8N_BASE_URL": "your-n8n-url"
}
}
}
}

text

## 📖 Contents

- [🤖 AI Agents](#ai-agents) (44 workflows)
- [🔌 MCP Server Integration](#mcp-server-integration) (16 workflows)
- [🧠 Memory & Long-term Context](#memory--long-term-context) (8 workflows)
- [📚 RAG & Knowledge Base](#rag--knowledge-base) (8 workflows)
- [📱 Social Media Automation](#social-media-automation) (50 workflows)
- [📧 Email & Messaging](#email--messaging) (18 workflows)
- [📊 Data Processing & Analytics](#data-processing--analytics) (54 workflows)
- [👥 HR & Recruitment](#hr--recruitment) (12 workflows)
- [🛒 E-commerce & Sales](#e-commerce--sales) (7 workflows)
- [💰 Finance & Trading](#finance--trading) (1 workflows)
- [🔧 DevOps & Engineering](#devops--engineering) (33 workflows)
- [🎧 Customer Support](#customer-support) (7 workflows)


## 🤖 AI Agents


| Workflow | Difficulty | 🛠 Services | 🤖 OpenClaw | Source |
|----------|-----------|------------|------------|--------|
| [Google SheetsHTTP RequestTelegram+7Create & Upload AI-Generated ASMR YouTube Sho… ⚠️](https://n8n.io/workflows/5110-create-and-upload-ai-generated-asmr-youtube-shorts-with-seedance-fal-ai-and-gpt-4/) | ⭐⭐⭐⭐ | Telegram, Google Sheets | 生成ASMR短视频并上传YouTube | official |
| [Draft and Manage Academic Research Papers with GPT-4 and Pinecone](https://n8n.io/workflows/12730-draft-and-manage-academic-research-papers-with-gpt-4-and-pinecone/) | ⭐⭐⭐⭐ | — | 把我的科研问题发送给这个 workflow，先在 Pinecone 里做语义检索，再用 GPT-4 生成带引用的结构化回答和论文草稿章节，并通过邮件把结果发给我。 | official |
| [Multi-Agent Research Assistant for Structured Articles](https://github.com/christinametalouli/MultiagentResearchAssistant) | ⭐⭐⭐⭐ | — | 围绕指定研究主题，调用多智能体 workflow：先生成章节大纲，再用 Web 检索收集证据，按章节写作并加上引用，最后把完整的研究型文章通过邮件发给我。 | community |
| [Deep Research Agent: Generate In-Depth PDF Reports from Any Topic](https://www.youtube.com/watch?v=TeFCb5-4e5U) | ⭐⭐⭐⭐ | — | 围绕指定研究主题运行深度研究 Agent：自动拆分子问题，多智能体并行检索与写作，最后生成带引用的 PDF 研究报告并发送给我。 | community |
| [AI Literature Review Writer with Tavily and ChatGPT](https://www.youtube.com/watch?v=oVf1kPXwyTo) | ⭐⭐⭐⭐ | — | 针对某个研究主题，自动生成 5 章结构化文献综述：先规划章节，再用 Tavily 检索文献，并用 ChatGPT 生成带引用的综述草稿。 | community |
| [Form-Driven AI Research Agent with Airtable and PDF Output](https://www.youtube.com/watch?v=fcp19B5ur_w) | ⭐⭐⭐⭐ | — | 通过表单提交研究主题，触发多轮 AI 研究：自动规划章节、调用多个研究子 Agent，存储中间结果到 Airtable，并导出最终 PDF 报告。 | community |
| [Google SheetsHTTP RequestGoogle Drive+1Generate AI Videos with Google Veo3, Save… ⚠️](https://n8n.io/workflows/4846-generate-ai-videos-with-google-veo3-save-to-google-drive-and-upload-to-youtube/) | ⭐⭐⭐ | Google Sheets | 用Google Veo3生成视频并保存到谷歌云盘 | official |
| [HTTP RequestGoogle DriveTransform Old Photos into Animated Videos with FLUX & Kl…](https://n8n.io/workflows/5755-transform-old-photos-into-animated-videos-with-flux-and-kling-ai-for-social-media/) | ⭐⭐⭐ | — | 用AI把老照片转换成动画视频 | official |
| [HTTP RequestCodeAI Agent+1Transform Long Videos into Viral Shorts with AI and Sc… ⚠️](https://n8n.io/workflows/9867-transform-long-videos-into-viral-shorts-with-ai-and-schedule-to-social-media-using-whisper-and-gemini/) | ⭐⭐⭐ | — | 将长视频转换成病毒式短视频并发布到社媒 | official |
| [Google SheetsHTTP RequestGoogle Drive+2Automate AI Video Creation & Multi-Platfo… ⚠️](https://n8n.io/workflows/10358-automate-ai-video-creation-and-multi-platform-publishing-with-gpt-4-veo-31-and-blotato/) | ⭐⭐⭐ | Google Sheets | 自动生成AI视频并发布到多平台 | official |
| [Google SheetsHTTP RequestTelegram+7Automate & Publish Video Ad Campaigns with Na… ⚠️](https://n8n.io/workflows/9200-automate-and-publish-video-ad-campaigns-with-nanobanana-seedream-gpt-4o-veo-3/) | ⭐⭐⭐ | Telegram, Google Sheets | 自动生成并发布视频广告 | official |
| [HTTP RequestTelegramCode+5Create AI Viral Videos using NanoBanana 2 PRO & VEO3.1… ⚠️](https://n8n.io/workflows/11204-create-ai-viral-videos-using-nanobanana-2-pro-and-veo31-and-publish-via-blotato/) | ⭐⭐⭐ | Telegram | 用AI生成病毒视频并发布到博客 | official |
| [AI Builder with n8n Create Agents Voice Agents](https://github.com/M-F-Tushar/AI-Builder-with-n8n-Create-Agents-Voice-Agents) | ⭐⭐⭐ | — | 构建AI代理和语音AI工作流 | community |
| [ai video clipping tools ⚠️](https://github.com/fboucher/ai-video-clipping-tools) | ⭐⭐⭐ | — | 监听YouTube频道新视频并生成AI剪辑 | community |
| [n8n automation workflows ⚠️](https://github.com/swapnilmandloi312/n8n-automation-workflows) | ⭐⭐⭐ | — | 构建AI驱动的自动化工作流程集合 | community |
| [Content creation with N8N AI Agent ⚠️](https://github.com/shubhamnevgi/Content-creation-with-N8N-AI-Agent) | ⭐⭐⭐ | — | 帮我创建AI驱动的视频内容并发布到社交媒体 | community |
| [ai video automation ⚠️](https://github.com/tumuexe44/ai-video-automation) | ⭐⭐⭐ | — | 帮我生成短视频创意并自动化剪辑发布 | community |
| [n8n workflow project lists](https://github.com/Orekidesu/n8n-workflow-project-lists) | ⭐⭐⭐ | — | 收集模块化n8n工作流示例 | community |
| [I built a workflow to replicate ANY image style using Nano Banana Pro! And I’m l…](https://reddit.com/r/n8n/comments/1qwq4k6/i_built_a_workflow_to_replicate_any_image_style/) | ⭐⭐⭐ | — | 复制任意图像风格的工作流程 | community |
| [Agentic AI browsers are insane I mean just look at this](https://reddit.com/r/n8n/comments/1r286z1/agentic_ai_browsers_are_insane_i_mean_just_look/) | ⭐⭐⭐ | — | 用AI浏览器自动化爬取潜在客户信息 | community |
| [I Built an AI Construction Timelapse Video Generator (I Just Feed It Before &amp…](https://reddit.com/r/n8n/comments/1qwky0h/i_built_an_ai_construction_timelapse_video/) | ⭐⭐⭐ | — | 帮我用AI生成建筑工地延时摄影视频 | community |
| [my n8n AI agent burned $63 in API credits retrying the same failed node 800 time… ⚠️](https://reddit.com/r/n8n/comments/1qy9eyv/my_n8n_ai_agent_burned_63_in_api_credits_retrying/) | ⭐⭐⭐ | Openai | 优化AI agent重试机制避免API超支 | community |
| [I tried “vibe coding” a full SaaS with Claude + n8n — this surprised me](https://reddit.com/r/n8n/comments/1r6q5pb/i_tried_vibe_coding_a_full_saas_with_claude_n8n/) | ⭐⭐⭐ | Claude | 用Claude和n8n构建SaaS的最佳实践 | community |
| [Build agent-based apps in n8n without building an entire RAG pipeline](https://reddit.com/r/n8n/comments/1qv1bxp/build_agentbased_apps_in_n8n_without_building_an/) | ⭐⭐⭐ | — | 用Pinecone简化RAG管道构建智能体应用 | community |
| [Sharing a project I had built 4 months ago, so that it doesn't collect digital d…](https://reddit.com/r/n8n/comments/1r4nmyy/sharing_a_project_i_had_built_4_months_ago_so/) | ⭐⭐⭐ | — | 构建AI语音代理自动化工作流 | community |
| [Built a fully automated AI health video workflow with n8n + Veo 3 ⚠️](https://reddit.com/r/n8n/comments/1qx5564/built_a_fully_automated_ai_health_video_workflow/) | ⭐⭐⭐ | Google Sheets | 学习AI视频自动生成工作流设计 | community |
| [As promised, sharing my Restaurant AI Voice Agent + Table Booking Automation](https://reddit.com/r/n8n/comments/1r83qu1/as_promised_sharing_my_restaurant_ai_voice_agent/) | ⭐⭐⭐ | — | 构建餐厅AI语音客服和订位自动化 | community |
| [Create business docs and finds leads](https://reddit.com/r/n8n/comments/1rf8hyi/create_business_docs_and_finds_leads/) | ⭐⭐⭐ | — | 自动生成商业文档并寻找业务线索 | community |
| [I tried “vibe coding” a full SaaS with Claude + n8n — this surprised me](https://reddit.com/r/n8n/comments/1r9iazv/i_tried_vibe_coding_a_full_saas_with_claude_n8n/) | ⭐⭐⭐ | Claude | 用Claude和n8n快速构建SaaS应用 | community |
| [I added persistent memory to my n8n AI Agent — it now remembers users across ses…](https://reddit.com/r/n8n/comments/1rg56dy/i_added_persistent_memory_to_my_n8n_ai_agent_it/) | ⭐⭐⭐ | — | 帮我实现AI Agent的跨会话持久化记忆 | community |
| [Retrieve LLM Token Usage in AI Agents](https://community.n8n.io/t/retrieve-llm-token-usage-in-ai-agents/68714) | ⭐⭐⭐ | — | 在AI Agent中获取LLM token使用情况 | community |
| [How I Built a YouTube Automation That Creates Viral Long-Form Videos with AI](https://community.n8n.io/t/how-i-built-a-youtube-automation-that-creates-viral-long-form-videos-with-ai/105676) | ⭐⭐⭐ | — | 帮我分析YouTube自动化工作流架构 | community |
| [[Use Case] Built an AI Agent That Generates SEO + Emotionally Optimized Content …](https://community.n8n.io/t/use-case-built-an-ai-agent-that-generates-seo-emotionally-optimized-content-for-blog-social-newsletter-landing-pages-geo/119051) | ⭐⭐⭐ | — | 构建SEO内容优化的AI Agent工作流 | community |
| [Made an openai-compatible bridge for n8n workflows](https://community.n8n.io/t/made-an-openai-compatible-bridge-for-n8n-workflows/205640) | ⭐⭐⭐ | Openai | 帮我构建OpenAI兼容的n8n工作流桥接 | community |
| [Outbound Twilio Call using ElevenLabs Voice/Agent](https://community.n8n.io/t/outbound-twilio-call-using-elevenlabs-voice-agent/92117) | ⭐⭐⭐ | — | 帮我构建Twilio通话与ElevenLabs语音集成 | community |
| [Ocr with AI agent](https://community.n8n.io/t/ocr-with-ai-agent/114686) | ⭐⭐⭐ | — | 用AI Agent实现OCR识别工作流 | community |
| [WhatsApp Ai Agent for car rent company](https://community.n8n.io/t/whatsapp-ai-agent-for-car-rent-company/263919) | ⭐⭐⭐ | Whatsapp | 帮我构建WhatsApp AI智能客服用于租车业务 | community |
| [Criando agendamento com captação de lead no n8n usando IA](https://community.n8n.io/t/criando-agendamento-com-captacao-de-lead-no-n8n-usando-ia/261338) | ⭐⭐⭐ | — | 帮我构建AI驱动的客户预约及潜在客户捕获工作流 | community |
| [▶️ Full video guide: n8n AI chatbot with human takeover (free template)](https://community.n8n.io/t/full-video-guide-n8n-ai-chatbot-with-human-takeover-free-template/266732) | ⭐⭐⭐ | — | 帮我构建AI聊天机器人工作流 | community |
| [Telegram AI Chatbot with Human Takeover](https://community.n8n.io/t/telegram-ai-chatbot-with-human-takeover/265056) | ⭐⭐⭐ | Telegram | 帮我构建 Telegram AI 聊天机器人 | community |
| [n8n ai automations](https://github.com/lucaswalter/n8n-ai-automations) | ⭐⭐ | — | 帮我使用 n8n AI 自动化工作流处理 {任务} | community |
| [Telegram AI Agent ⚠️](https://reddit.com/r/n8n/comments/1r582pm/telegram_ai_agent/) | ⭐⭐ | Telegram | 搭建Telegram智能回复机器人 | community |
| [Automating Content Generation with n8n](https://reddit.com/r/n8n/comments/1qsp0m4/automating_content_generation_with_n8n/) | ⭐⭐ | — | 用AI节点生成内容草稿并优化 | community |
| [Automated Blog Publishing Workflow Using n8n – Need Help to Humanize AI Content](https://community.n8n.io/t/automated-blog-publishing-workflow-using-n8n-need-help-to-humanize-ai-content/118721) | ⭐⭐ | — | 帮我优化AI内容的人性化处理流程 | community |

## 🔌 MCP Server Integration


| Workflow | Difficulty | 🛠 Services | 🤖 OpenClaw | Source |
|----------|-----------|------------|------------|--------|
| [End to End Agentic Ai Automation Lab](https://github.com/MDalamin5/End-to-End-Agentic-Ai-Automation-Lab) | ⭐⭐⭐⭐ | — | 帮我运行端到端智能自动化工作流示例 | community |
| [RedisAI AgentOpenAI Chat Model+3Build your own N8N Workflows MCP ServerThis n8n …](https://n8n.io/workflows/3770-build-your-own-n8n-workflows-mcp-server/) | ⭐⭐⭐ | Openai, Redis | 帮我构建一个 n8n Workflows MCP Server | official |
| [project nova](https://github.com/dujonwalker/project-nova) | ⭐⭐⭐ | — | 帮我用 Project NOVA 的专家agent处理 {任务} | community |
| [n8n workflow builder mcp](https://github.com/ifmelate/n8n-workflow-builder-mcp) | ⭐⭐⭐ | — | 帮我用 n8n 构建一个 {业务流程} 工作流 | community |
| [n8n nodes agent2agent ⚠️](https://github.com/pjawz/n8n-nodes-agent2agent) | ⭐⭐⭐ | — | 帮我用 Agent2Agent 协议与 AI 智能体交互 | community |
| [n8n openai bridge](https://github.com/sveneisenschmidt/n8n-openai-bridge) | ⭐⭐⭐ | Openai | 帮我将 n8n workflow 接入 OpenAI 兼容 API | community |
| [n8n workflow builder](https://github.com/makafeli/n8n-workflow-builder) | ⭐⭐⭐ | Claude | 帮我用 Claude 创建并自动化 n8n 工作流 | community |
| [mcp n8n workflow builder](https://github.com/salacoste/mcp-n8n-workflow-builder) | ⭐⭐⭐ | Claude | 帮我用自然语言创建并管理 n8n workflow | community |
| [claude mcps and prompts](https://github.com/tiagolemos05/claude-mcps-and-prompts) | ⭐⭐⭐ | Claude | 帮我用Claude生成SEO博客文章并优化{关键词}排名 | community |
| [n8n workflow sdk mcp](https://github.com/octionic/n8n-workflow-sdk-mcp) | ⭐⭐⭐ | Claude | 帮我用 TypeScript 管理和更新 n8n workflow | community |
| [mcp n8n server](https://github.com/ahmadsoliman/mcp-n8n-server) | ⭐⭐⭐ | Claude | 帮我通过 MCP 服务器连接 Claude 到 n8n 工作流 | community |
| [I Replaced $100+/month in GEMINI API Costs with a €2000 eBay Mac Studio — Here i… ⚠️](https://reddit.com/r/n8n/comments/1ri8922/i_replaced_100month_in_gemini_api_costs_with_a/) | ⭐⭐⭐ | Telegram | 帮我用本地 Qwen 模型通过 Telegram 运行自托管 AI 智能体系统 | community |
| [I built n8n-mcp-lite: A token-optimized Model Context Protocol for Claude/AI age…](https://reddit.com/r/n8n/comments/1rgpbf6/i_built_n8nmcplite_a_tokenoptimized_model_context/) | ⭐⭐⭐ | Claude | 帮我用 n8n-mcp-lite 为 Claude 构建优化的工作流 | community |
| [n8n manager for ai agents](https://github.com/czlonkowski/n8n-manager-for-ai-agents) | ⭐⭐ | Claude | 帮我管理和执行 {workflow名称} 的 n8n 工作流 | community |
| [n8n deepseek](https://github.com/rubickecho/n8n-deepseek) | ⭐⭐ | Openai | 帮我用 DeepSeek AI 处理 {问题} | community |
| [I made a free MCP server to create short videos locally with n8n - 100% free, op…](https://reddit.com/r/n8n/comments/1k575uq/i_made_a_free_mcp_server_to_create_short_videos/) | ⭐⭐ | Github | 帮我用 MCP 服务器生成短视频 | community |

## 🧠 Memory & Long-term Context


| Workflow | Difficulty | 🛠 Services | 🤖 OpenClaw | Source |
|----------|-----------|------------|------------|--------|
| [I Built an AI Agent Army in n8n That Completely Replaced My Personal Assistant](https://reddit.com/r/n8n/comments/1mugdof/i_built_an_ai_agent_army_in_n8n_that_completely/) | ⭐⭐⭐⭐ | Github | 帮我加载个人助手 workflow 并执行记忆管理任务 | community |
| [AI AgentEmbeddings OpenAICalculator+4Evaluate tool usage accuracy in multi-agent…](https://n8n.io/workflows/5523-evaluate-tool-usage-accuracy-in-multi-agent-ai-workflows-using-evaluation-nodes/) | ⭐⭐⭐ | Openai | 帮我评估多Agent AI工作流中的工具使用准确性 | official |
| [AI AgentBasic LLM ChainAnthropic Chat Model+6AI Orchestrator: dynamically Select…](https://n8n.io/workflows/7004-ai-orchestrator-dynamically-selects-models-based-on-input-type/) | ⭐⭐⭐ | — | 帮我根据输入类型智能选择 AI 模型进行处理 | official |
| [n8n ai agents](https://github.com/GhufranBarcha/n8n_ai_agents) | ⭐⭐⭐ | — | 帮我查看 n8n AI agents 的记忆管理工作流 | community |
| [I Built a Personal AI Assistant That Runs My Life Through WhatsApp, Powered by n… ⚠️](https://reddit.com/r/n8n/comments/1mtv9re/i_built_a_personal_ai_assistant_that_runs_my_life/) | ⭐⭐⭐ | Whatsapp | 帮我通过 WhatsApp 建立个人 AI 助手管理日程 | community |
| [Anyone here using Human-in-the-Loop for AI agents in n8n? ⚠️](https://reddit.com/r/n8n/comments/1rhx3u4/anyone_here_using_humanintheloop_for_ai_agents_in/) | ⭐⭐⭐ | — | 帮我查询 n8n 中 Human-in-the-Loop 的内存管理方案 | community |
| [AI agent chat](https://n8n.io/workflows/1954-ai-agent-chat/) | ⭐⭐ | — | 帮我启动 AI agent 对话并保存记忆 | official |
| [Claude Project to n8n Workflow ⚠️](https://github.com/MobinMithun/Claude-Project-to-n8n-Workflow) | ⭐⭐ | Claude | 帮我用 Claude 处理用户查询并通过 n8n 自动响应 | community |

## 📚 RAG & Knowledge Base


| Workflow | Difficulty | 🛠 Services | 🤖 OpenClaw | Source |
|----------|-----------|------------|------------|--------|
| [chatwiki](https://github.com/zhimaAi/chatwiki) | ⭐⭐⭐ | — | 帮我用 ChatWiki 构建 {领域} 的 RAG 知识库 | community |
| [n8n automation 2025 AI Agent Suite ⚠️](https://github.com/tannu64/n8n-automation-2025-AI-Agent-Suite) | ⭐⭐⭐ | Telegram, Whatsapp, Gmail | 帮我用 RAG 系统处理 {文档} 并生成智能回复 | community |
| [n8n template and documentation for RAG](https://github.com/Kohnnn/n8n-template-and-documentation-for-RAG) | ⭐⭐⭐ | Claude | 帮我生成一个 RAG 的 n8n workflow 模板 | community |
| [Update: My RAG Agent is alive! From Google Drive ingestion to a working Chat int…](https://reddit.com/r/n8n/comments/1rhqxkb/update_my_rag_agent_is_alive_from_google_drive/) | ⭐⭐⭐ | — | 帮我构建 RAG 智能体从 Google Drive 获取数据并回答问题 | community |
| [I built a RAG pipeline using n8n that converts Google Drive documents into a sea…](https://reddit.com/r/n8n/comments/1rdadp2/i_built_a_rag_pipeline_using_n8n_that_converts/) | ⭐⭐⭐ | Telegram | 构建Google Drive文档RAG搜索管道 | community |
| [Scrape and summarize webpages with AI](https://n8n.io/workflows/1951-scrape-and-summarize-webpages-with-ai/) | ⭐⭐ | — | 帮我爬取 {网址} 并用 AI 总结 | official |
| [OpenConstructionEstimate DDC CWICR](https://github.com/datadrivenconstruction/OpenConstructionEstimate-DDC-CWICR) | ⭐⭐ | — | 帮我查询 {建筑项目} 的成本估算和资源信息 | community |
| [n8n nodes universal reranker](https://github.com/dalisys/n8n-nodes-universal-reranker) | ⭐⭐ | Openai | 帮我对文档进行 {查询词} 重排序 | community |

## 📱 Social Media Automation


| Workflow | Difficulty | 🛠 Services | 🤖 OpenClaw | Source |
|----------|-----------|------------|------------|--------|
| [Google SheetsHTTP RequestTelegram+3Auto-Create TikTok Videos with VEED.io AI Ava… ⚠️](https://n8n.io/workflows/10000-auto-create-tiktok-videos-with-veedio-ai-avatars-elevenlabs-and-gpt-4/) | ⭐⭐⭐⭐ | Telegram, Google Sheets | 自动生成TikTok视频，集成AI头像、配音、GPT内容 | official |
| [workflow n8n ⚠️](https://github.com/ojonatasquirino/workflow-n8n) | ⭐⭐⭐ | Openai, Whatsapp | 帮我用 WhatsApp 和 OpenAI 建立 n8n 自动化流程 | community |
| [Secretaria IA Automacao Atendimento WhatsApp n8n OpenAI ⚠️](https://github.com/Rayquazads/Secretaria-IA-Automacao-Atendimento-WhatsApp-n8n-OpenAI) | ⭐⭐⭐ | Openai, Whatsapp | 帮我用 WhatsApp 自动化诊所预约和患者回复 | community |
| [FaceBook Ad Manager System ⚠️](https://github.com/Awaisali36/FaceBook-Ad-Manager-System) | ⭐⭐⭐ | Claude | 帮我用 AI 生成 Facebook 广告文案和素材 | community |
| [Built my own AI-UGC automation since everyone else is gatekeeping — dropping it … ⚠️](https://reddit.com/r/n8n/comments/1p6g3py/built_my_own_aiugc_automation_since_everyone_else/) | ⭐⭐⭐ | — | 帮我用 AI 自动生成 UGC 视频内容 | community |
| [You can safely discard your 159 node n8n automation that created 500 AI shorts i… ⚠️](https://reddit.com/r/n8n/comments/1lvfz70/you_can_safely_discard_your_159_node_n8n/) | ⭐⭐⭐ | — | 帮我用 AI 快速生成 500 条社交媒体短视频 | community |
| [This Automation Took Me From 0 to 175k Followers in Under 12 Months ⚠️](https://reddit.com/r/n8n/comments/1oj8q69/this_automation_took_me_from_0_to_175k_followers/) | ⭐⭐⭐ | — | 帮我运行社交媒体增长自动化工作流到175k粉丝 | community |
| [My last SEO automation blew up to 200k views… and V2 fixes every limitation the … ⚠️](https://reddit.com/r/n8n/comments/1phf74d/my_last_seo_automation_blew_up_to_200k_views_and/) | ⭐⭐⭐ | — | 帮我运行 SEO 自动化 workflow 提升社交媒体浏览量 | community |
| [I rebuilt most of OpenClaw's core functionality in a single n8n workflow ⚠️](https://reddit.com/r/n8n/comments/1r24b7c/i_rebuilt_most_of_openclaws_core_functionality_in/) | ⭐⭐⭐ | Telegram, Whatsapp, Supabase | 帮我通过 {渠道} 发送多渠道消息并保持对话连贯 | community |
| [I built a 24/7 AI Receptionist with n8n so our local restaurant never misses a c…](https://reddit.com/r/n8n/comments/1nfx1uj/i_built_a_247_ai_receptionist_with_n8n_so_our/) | ⭐⭐⭐ | — | 帮我创建一个24小时AI接待员workflow接听餐厅电话 | community |
| [3M views in 3 months, all from this automation that snipes early trending storie… ⚠️](https://reddit.com/r/n8n/comments/1oncgwf/3m_views_in_3_months_all_from_this_automation/) | ⭐⭐⭐ | Openai | 帮我自动抓取 X 上的早期趋势故事并发布 | community |
| [I built an AI voice agent that replaced my entire marketing team (creates newsle…](https://reddit.com/r/n8n/comments/1mch7p6/i_built_an_ai_voice_agent_that_replaced_my_entire/) | ⭐⭐⭐ | — | 帮我用 AI 语音智能体创建营销内容并生成短视频 | community |
| [Built my own AI-UGC automation since everyone else is gatekeeping — dropping it … ⚠️](https://reddit.com/r/n8n/comments/1pyp6dp/built_my_own_aiugc_automation_since_everyone_else/) | ⭐⭐⭐ | — | 帮我用 AI-UGC 自动化生成社交媒体内容 | community |
| [I built a comprehensive Instagram + Messenger chatbot with n8n (with ZERO coding… ⚠️](https://reddit.com/r/n8n/comments/1k4u0c4/i_built_a_comprehensive_instagram_messenger/) | ⭐⭐⭐ | — | 帮我构建 Instagram 和 Messenger 的自动回复聊天机器人 | community |
| [I Built a Fully Automated Social Media Content Machine that You can Sell to Clie… ⚠️](https://reddit.com/r/n8n/comments/1jlf53k/i_built_a_fully_automated_social_media_content/) | ⭐⭐⭐ | Telegram | 帮我自动化社交媒体内容发布流程 | community |
| [I built a WhatsApp chatbot and AI Agent for hotels and the hospitality industry ⚠️](https://reddit.com/r/n8n/comments/1mr2vyq/i_built_a_whatsapp_chatbot_and_ai_agent_for/) | ⭐⭐⭐ | Whatsapp | 帮我构建酒店 WhatsApp 聊天机器人和 AI 智能体 | community |
| [Free workflow lets you automate video generation for TikTok, Reels, Shorts etc ⚠️](https://reddit.com/r/n8n/comments/1j91dkn/free_workflow_lets_you_automate_video_generation/) | ⭐⭐⭐ | Openai | 帮我用AI生成适配TikTok的短视频 | community |
| [I built a self-improving TikTok carousel workflow that learns from its own analy… ⚠️](https://reddit.com/r/n8n/comments/1rgi8ah/i_built_a_selfimproving_tiktok_carousel_workflow/) | ⭐⭐⭐ | — | 帮我创建自学习TikTok视频并优化投放效果 | community |
| [I build automations for businesses. Most of you are just scaling your own mess. ⚠️](https://reddit.com/r/n8n/comments/1rf8yyg/i_build_automations_for_businesses_most_of_you/) | ⭐⭐⭐ | Gmail | 帮我为 {内容} 生成社交媒体文案并自动发布 | community |
| [Google SheetsHTTP RequestLinkedIn Job Finder Automation using Bright Data API & …](https://n8n.io/workflows/4775-linkedin-job-finder-automation-using-bright-data-api-and-google-sheets/) | ⭐⭐⭐ | Google Sheets | 从LinkedIn爬取职位信息到Google Sheets | official |
| [Google SheetsHTTP RequestAI Agent+3Generate & Auto-post AI Videos to Social Medi… ⚠️](https://n8n.io/workflows/5035-generate-and-auto-post-ai-videos-to-social-media-with-veo3-and-blotato/) | ⭐⭐⭐ | Google Sheets | 自动生成AI视频并发布到社交媒体 | official |
| [Google SheetsHTTP RequestCode+4Generate AI Viral Videos with Seedance and Upload… ⚠️](https://n8n.io/workflows/5338-generate-ai-viral-videos-with-seedance-and-upload-to-tiktok-youtube-and-instagram/) | ⭐⭐⭐ | Google Sheets | 生成AI视频并上传到社交媒体 | official |
| [social story scraper ⚠️](https://github.com/sirlifehacker/social-story-scraper) | ⭐⭐⭐ | — | 帮我抓取Twitter趋势故事并生成病毒式内容创意 | community |
| [TwitterThreadCreator ⚠️](https://github.com/SohamXYZDev/TwitterThreadCreator) | ⭐⭐⭐ | — | 帮我用AI把YouTube视频转成Twitter线程 | community |
| [N8N Automation Suite ⚠️](https://github.com/KanishqGandharv219/N8N-Automation-Suite) | ⭐⭐⭐ | — | 帮我搭建LinkedIn自动化爬虫和销售线索认证流程 | community |
| [Linkedin Leadgen ⚠️](https://github.com/Shobhit-Mandal/Linkedin-Leadgen) | ⭐⭐⭐ | — | 帮我自动化LinkedIn潜在客户生成和外联 | community |
| [I built an n8n workflow that automates personalized LinkedIn outreach using AI —… ⚠️](https://reddit.com/r/n8n/comments/1r0stwn/i_built_an_n8n_workflow_that_automates/) | ⭐⭐⭐ | — | 帮我自动化LinkedIn开发客户流程 | community |
| [Built a fully automated Google Business Profile posting system with n8n - 625 im… ⚠️](https://reddit.com/r/n8n/comments/1r9718t/built_a_fully_automated_google_business_profile/) | ⭐⭐⭐ | Github | 自动化Google商业资料图片发布 | community |
| [I replaced a 3-person content pipeline with one n8n workflow. YouTube → LinkedIn… ⚠️](https://reddit.com/r/n8n/comments/1r6ui7z/i_replaced_a_3person_content_pipeline_with_one/) | ⭐⭐⭐ | — | 帮我构建YouTube到多渠道内容分发工作流 | community |
| [WhatsApp Cloud - Customer Service automation with Templates - How to handle What…](https://community.n8n.io/t/whatsapp-cloud-customer-service-automation-with-templates-how-to-handle-whatsapp-interactive-button-replies-in-n8n-without-restarting-the-trigger-flow/264125) | ⭐⭐⭐ | Whatsapp | 帮我构建WhatsApp客服自动化工作流 | community |
| [Telegram AI Chatbot ⚠️](https://n8n.io/workflows/1934-telegram-ai-chatbot/) | ⭐⭐ | Telegram | 帮我用 Telegram AI 机器人回复 {消息} | official |
| [audio chat n8n wasenderapi ⚠️](https://github.com/wasenderapi/audio-chat-n8n-wasenderapi) | ⭐⭐ | Openai | 帮我创建一个音频聊天机器人处理 Wasenderapi 消息 | community |
| [reddit content filter n8n ⚠️](https://github.com/kenandrewmiranda/reddit-content-filter-n8n) | ⭐⭐ | Openai, Slack | 帮我筛选 {subreddit} 的 Reddit 热门帖子并总结 | community |
| [I saw someone gatekeep their “Viral IG Script Generator” behind a paywall… so I … ⚠️](https://reddit.com/r/n8n/comments/1ox2api/i_saw_someone_gatekeep_their_viral_ig_script/) | ⭐⭐ | — | 帮我生成一个比付费版更好的 Instagram 短视频脚本 | community |
| [I built this AI Automation to write viral TikTok/IG video scripts (got over 1.8 … ⚠️](https://reddit.com/r/n8n/comments/1loafvx/i_built_this_ai_automation_to_write_viral/) | ⭐⭐ | — | 帮我生成 {话题} 的 TikTok/Instagram 病毒式脚本 | community |
| [n8n twitter thread fetcher](https://github.com/enescingoz/n8n-twitter-thread-fetcher) | ⭐⭐ | — | 帮我批量提取Twitter线程内容 | community |
| [Youtube to Discord Automation ⚠️](https://github.com/Baavanadhaz/Youtube-to-Discord-Automation) | ⭐⭐ | Discord | 帮我实现YouTube到Discord的自动通知 | community |
| [n8n nodes upload post ⚠️](https://github.com/Upload-Post/n8n-nodes-upload-post) | ⭐⭐ | — | 帮我将内容发布到多个社交媒体平台 | community |
| [n8n discord trigger bot](https://github.com/Jharilela/n8n_discord_trigger_bot) | ⭐⭐ | Discord | 搭建Discord机器人触发工作流 | community |
| [n8n discord automation templates ⚠️](https://github.com/nameershah/n8n-discord-automation-templates) | ⭐⭐ | Discord | 创建Discord自动化工作流模板 | community |
| [N8N Agent for discord ⚠️](https://github.com/Alfredd43/N8N-Agent-for-discord) | ⭐⭐ | Discord | 帮我自动化Discord服务器的消息和机器人交互 | community |
| [discord bot n8n ⚠️](https://github.com/MibzarGalarza/discord-bot-n8n) | ⭐⭐ | Discord | 搭建Discord机器人接收消息 | community |
| [whatsapp n8n bot ⚠️](https://github.com/Whapi-Cloud/whatsapp-n8n-bot) | ⭐⭐ | Whatsapp | 帮我搭建WhatsApp自动化机器人 | community |
| [I built a "comment → DM" autopilot for Instagram using n8n. Here's exactly how (… ⚠️](https://reddit.com/r/n8n/comments/1r3xj2t/i_built_a_comment_dm_autopilot_for_instagram/) | ⭐⭐ | Google Sheets | 帮我构建Instagram评论自动回复DM工作流 | community |
| [Auto reply on FB/IG with a DM if someone comments your post with a certain keywo…](https://community.n8n.io/t/auto-reply-on-fb-ig-with-a-dm-if-someone-comments-your-post-with-a-certain-keyword-they-add/269511) | ⭐⭐ | — | 帮我构建FB/IG评论自动回复工作流 | community |
| [微信公众号自动发布文章：mp-wechat publish articles automaticly](https://community.n8n.io/t/mp-wechat-publish-articles-automaticly/149748) | ⭐⭐ | — | 帮我构建微信公众号自动发布文章的n8n工作流 | community |
| [N8N x Social Media x Notion Content Management](https://community.n8n.io/t/n8n-x-social-media-x-notion-content-management/209862) | ⭐⭐ | Notion | 帮我分析这个社交媒体内容管理workflow | community |
| [How to get Discord messages in n8n](https://community.n8n.io/t/how-to-get-discord-messages-in-n8n/261862) | ⭐⭐ | Discord | 帮我构建Discord消息获取工作流 | community |
| [Auto reply on FB/IG with a DM if someone comments your post with a certain keywo…](https://community.n8n.io/t/auto-reply-on-fb-ig-with-a-dm-if-someone-comments-your-post-with-a-certain-keyword-they-add/269511) | ⭐⭐ | — | 帮我构建FB/IG评论自动回复工作流 | community |
| [I made my 1st working workflow and I never been so proud ⚠️](https://reddit.com/r/n8n/comments/1lsoams/i_made_my_1st_working_workflow_and_i_never_been/) | ⭐ | — | 帮我在妻子收到日期时发送提醒通知 | community |

## 📧 Email & Messaging


| Workflow | Difficulty | 🛠 Services | 🤖 OpenClaw | Source |
|----------|-----------|------------|------------|--------|
| [i automated the entire cold outreach process in n8n (sorry to whoever's job i ju… ⚠️](https://reddit.com/r/n8n/comments/1jgl5ek/i_automated_the_entire_cold_outreach_process_in/) | ⭐⭐⭐ | — | 帮我自动化冷邮件外联流程 | community |
| [UPDATE! - I automated the entire cold outreach process in n8n (sorry to whoever'… ⚠️](https://reddit.com/r/n8n/comments/1jm842j/update_i_automated_the_entire_cold_outreach/) | ⭐⭐⭐ | — | 帮我自动化冷邮件外联流程 | community |
| [I built an n8n workflow that automatically finds clients and made me my first $2… ⚠️](https://reddit.com/r/n8n/comments/1ndb2tf/i_built_an_n8n_workflow_that_automatically_finds/) | ⭐⭐ | — | 帮我运行自动找客户的 n8n workflow 并发送邮件报告 | community |
| [awesome n8n templates](https://github.com/enescingoz/awesome-n8n-templates) | ⭐⭐ | Telegram, Gmail, Slack | — | community |
| [n8n automation hub](https://github.com/abderrahimghazali/n8n-automation-hub) | ⭐⭐ | Telegram, Gmail, Google Sheets | — | community |
| [awesome n8n templates](https://github.com/Sudharshan2026/awesome-n8n-templates) | ⭐⭐ | Telegram, Gmail, Slack | — | community |
| [n8n workflows](https://github.com/scholarpeak/n8n-workflows) | ⭐⭐ | Telegram, Gmail, Slack | — | community |
| [Gmail automation ⚠️](https://github.com/Forgemind-git/Gmail-automation) | ⭐⭐ | Gmail | — | community |
| [awesome n8n workflows](https://github.com/pxw3504k-web/awesome-n8n-workflows) | ⭐⭐ | Gmail, Notion, Slack | — | community |
| [n8n rag automation chatbot ⚠️](https://github.com/Trinhvhao/n8n-rag-automation-chatbot) | ⭐⭐ | Telegram, Gmail | — | community |
| [N8N Workflow ⚠️](https://github.com/BilalMoazzam/N8N-Workflow) | ⭐⭐ | Whatsapp, Gmail | — | community |
| [n8n workflow duhops world ⚠️](https://github.com/sandeep27choudhary/n8n-workflow-duhops-world) | ⭐⭐ | Telegram, Whatsapp, Gmail | — | community |
| [sendur](https://github.com/walimorris/sendur) | ⭐⭐ | — | — | community |
| [Stop overpaying for email tools. Seriously.](https://reddit.com/r/n8n/comments/1rcvci4/stop_overpaying_for_email_tools_seriously/) | ⭐⭐ | — | 整合Tomba邮箱查询工具降低成本 | community |
| [Email Trigger (IMAP)](https://community.n8n.io/t/email-trigger-imap/90114) | ⭐⭐ | — | 帮我用IMAP构建邮件触发器 | community |
| [Extracting email addresses and names from entire email](https://community.n8n.io/t/extracting-email-addresses-and-names-from-entire-email/84145) | ⭐⭐ | — | 帮我从邮件中提取邮箱和名字 | community |
| [How to Build an n8n Workflow to Automatically Send Personalized PDFs to Differen…](https://community.n8n.io/t/how-to-build-an-n8n-workflow-to-automatically-send-personalized-pdfs-to-different-recipients/150600) | ⭐⭐ | — | 帮我构建自动生成并发送个性化PDF的工作流 | community |
| [Email Forwarding (Body + PDF) to Telegram fails with "undefined" error - Need JS… ⚠️](https://community.n8n.io/t/email-forwarding-body-pdf-to-telegram-fails-with-undefined-error-need-json-review/261784) | ⭐⭐ | Telegram | 帮我调试邮件转发到Telegram的workflow | community |

## 📊 Data Processing & Analytics


| Workflow | Difficulty | 🛠 Services | 🤖 OpenClaw | Source |
|----------|-----------|------------|------------|--------|
| [Automate Systematic Literature Reviews with Google Drive, GPT-4, Gemini, Qdrant,…](https://n8n.io/workflows/12827-automate-systematic-literature-reviews-with-google-drive-gpt-4-gemini-qdrant-and-airtable/) | ⭐⭐⭐⭐ | — | 帮我定期筛选 Google Drive 文件夹里的新论文，按纳入/排除标准打标签，并把 PRISMA 风格的决策日志同步到 Airtable，方便做系统综述和 meta-analysis。 | official |
| [n8n agent](https://github.com/kingler/n8n_agent) | ⭐⭐⭐ | — | 帮我用 AI Agent 生成 n8n 自动化工作流 | community |
| [N8N AI Agents Masterclass](https://github.com/ChinmayKaitade/N8N-AI-Agents-Masterclass) | ⭐⭐⭐ | Openai | 帮我用 AI Agents 构建 {任务名称} 的自动化工作流 | community |
| [seo auditor service](https://github.com/market-analyticx/seo-auditor-service) | ⭐⭐⭐ | Openai | 帮我对 {网站URL} 进行 SEO 审计分析 | community |
| [B2B SaaS Dashboard Generator Agent ⚠️](https://github.com/zachbaumgarten/B2B-SaaS-Dashboard-Generator-Agent) | ⭐⭐⭐ | Claude | 帮我为 {公司名} 生成 B2B 商业智能分析报告 | community |
| [I built an AI system that scrapes stories off the internet and generates a daily… ⚠️](https://reddit.com/r/n8n/comments/1l9pff8/i_built_an_ai_system_that_scrapes_stories_off_the/) | ⭐⭐⭐ | — | 帮我自动爬取AI新闻并生成每日通讯 | community |
| [Looks ugly but it is now managing my investments...](https://reddit.com/r/n8n/comments/1oc0mup/looks_ugly_but_it_is_now_managing_my_investments/) | ⭐⭐⭐ | — | 帮我分析加密货币市场并给出投资建议 | community |
| [He wouldn’t share his “AI SEO Blog Automation” so I took it personally and built… ⚠️](https://reddit.com/r/n8n/comments/1otjiub/he_wouldnt_share_his_ai_seo_blog_automation_so_i/) | ⭐⭐⭐ | — | 帮我用 AI 自动生成 {关键词} 的 SEO 博客文章 | community |
| [I didn’t think a “fine, I’ll build it myself” automation post would hit 170K+ vi… ⚠️](https://reddit.com/r/n8n/comments/1ozm3pi/i_didnt_think_a_fine_ill_build_it_myself/) | ⭐⭐⭐ | — | 帮我用 AI 生成 {主题} 的 SEO 博客文章 | community |
| [Friend lost his job, so instead of sympathy, I built him an automation.
It finds…](https://reddit.com/r/n8n/comments/1ov5lb6/friend_lost_his_job_so_instead_of_sympathy_i/) | ⭐⭐⭐ | — | 帮我从 LinkedIn 筛选匹配 {技能} 的职位并发送推荐 | community |
| [I built an AI automation that writes SEO-optimized articles using Deep Research …](https://reddit.com/r/n8n/comments/1l81jzd/i_built_an_ai_automation_that_writes_seooptimized/) | ⭐⭐⭐ | — | 帮我用深度研究报告生成SEO优化的{分类}工具综述文章 | community |
| [My father needed a simple video ad... agencies quoted $4,000. So I built him an …](https://reddit.com/r/n8n/comments/1po5xvy/my_father_needed_a_simple_video_ad_agencies/) | ⭐⭐⭐ | — | 帮我用 AI 为 {企业} 生成社交媒体视频广告 | community |
| [I made this n8n workflow. One  click (+ 4 days later)… and it turns a 1000+ page…](https://reddit.com/r/n8n/comments/1nk1tr3/i_made_this_n8n_workflow_one_click_4_days_later/) | ⭐⭐⭐ | — | 帮我将教科书转换成在线课程视频 | community |
| [I've had multiple clients hire me to build this simple automation. It finds new …](https://reddit.com/r/n8n/comments/1ocnoyj/ive_had_multiple_clients_hire_me_to_build_this/) | ⭐⭐⭐ | — | 帮我抓取LinkedIn职位并识别招聘经理 | community |
| [Finally got my first AI to Word document generator working - 40-100 pages from a…](https://reddit.com/r/n8n/comments/1pc37u4/finally_got_my_first_ai_to_word_document/) | ⭐⭐⭐ | — | 帮我用一句提示词生成40-100页Word文档 | community |
| [How We Built a News Automation System That Now Drives 10,000 Clicks a Month](https://reddit.com/r/n8n/comments/1p0z4yv/how_we_built_a_news_automation_system_that_now/) | ⭐⭐⭐ | — | 帮我构建新闻自动化系统并优化点击率 | community |
| [Built a Personal “Wealth Control Tower” Workflow to Monitor, Automate &amp; Stre…](https://reddit.com/r/n8n/comments/1rgy26a/built_a_personal_wealth_control_tower_workflow_to/) | ⭐⭐⭐ | — | 帮我构建个人财富监控系统实时跟踪高价值投资组合 | community |
| [I analysed 2,000+ n8n workflows and this is what I learned](https://reddit.com/r/n8n/comments/1l1f6n8/i_analysed_2000_n8n_workflows_and_this_is_what_i/) | ⭐⭐⭐ | Claude | 分析n8n workflow最佳实践 | community |
| [Just sync the calendar… not as easy as I thought](https://reddit.com/r/n8n/comments/1qyqj81/just_sync_the_calendar_not_as_easy_as_i_thought/) | ⭐⭐⭐ | — | 帮我同步Google日历到Airtable | community |
| [Workflow that gets a CSV of 2K rworkows and create a summary with insights and a…](https://community.n8n.io/t/workflow-that-gets-a-csv-of-2k-rworkows-and-create-a-summary-with-insights-and-actionable-items/266118) | ⭐⭐⭐ | — | 帮我构建CSV数据处理和AI摘要工作流 | community |
| [Generate a temporary URL for files along with binary data within a workflow](https://community.n8n.io/t/generate-a-temporary-url-for-files-along-with-binary-data-within-a-workflow/72315) | ⭐⭐⭐ | — | 帮我生成临时URL处理workflow中的二进制文件 | community |
| [Workflow that gets a CSV of 2K rworkows and create a summary with insights and a…](https://community.n8n.io/t/workflow-that-gets-a-csv-of-2k-rworkows-and-create-a-summary-with-insights-and-actionable-items/266118) | ⭐⭐⭐ | — | 批量处理CSV数据生成洞察总结 | community |
| [Automate Research Paper Collection with Bright Data and n8n](https://n8n.io/workflows/5221-automate-research-paper-collection-with-bright-data-and-n8n/) | ⭐⭐⭐ | Google Sheets | 从指定的学术网站抓取某个研究主题的新论文，用 Bright Data 抽取标题、作者、摘要和链接，并把结果追加到我的 Google Sheets 文献追踪表里。 | official |
| [Academic Research Agent: Scholar, arXiv, PubMed Monitoring and Summarization](https://www.linkedin.com/pulse/how-can-i-create-ai-agent-academic-research-using-n8n-ziyad-zubair-mbsqf) | ⭐⭐⭐ | — | 持续监控 Google Scholar 提醒、arXiv 和 PubMed 的新论文，为每篇生成结构化摘要（研究问题、方法、主要发现、局限），并带主题标签保存到我的研究知识库。 | community |
| [Joining different datasets](https://n8n.io/workflows/1747-joining-different-datasets/) | ⭐⭐ | — | 帮我合并不同来源的数据集 | official |
| [OpenAI GPT-3: Company Enrichment from website content](https://n8n.io/workflows/1862-openai-gpt-3-company-enrichment-from-website-content/) | ⭐⭐ | Openai | 帮我从 {网站} 内容中提取公司信息 | official |
| [Pulling data from services that n8n doesn’t have a pre-built integration for](https://n8n.io/workflows/1748-pulling-data-from-services-that-n8n-doesnt-have-a-pre-built-integration-for/) | ⭐⭐ | — | 帮我从 {服务名称} 拉取数据到 n8n | official |
| [Basic LLM ChainStructured Output ParserOpenRouter Chat ModelAuto Generate Descri…](https://n8n.io/workflows/10889-auto-generate-descriptive-node-names-with-ai-for-workflow-readability/) | ⭐⭐ | — | 帮我用 AI 自动生成 workflow 节点的描述性名称 | official |
| [Google SheetsAI AgentAnthropic Chat Model+3Track AI Agent token usage and estima… ⚠️](https://n8n.io/workflows/5541-track-ai-agent-token-usage-and-estimate-costs-in-google-sheets/) | ⭐⭐ | Google Sheets | 帮我追踪 AI Agent 的 token 使用情况并在 Google Sheets 中估算成本 | official |
| [HTTP RequestTelegramHubSpot+1Design scalable sync workflows with Data Tables, Pr… ⚠️](https://n8n.io/workflows/13536-design-scalable-sync-workflows-with-data-tables-prospectpro-and-hubspot/) | ⭐⭐ | Telegram | 帮我设计可扩展的 {数据源} 与 HubSpot 同步工作流 | official |
| [cad2data Revit IFC DWG DGN](https://github.com/datadrivenconstruction/cad2data-Revit-IFC-DWG-DGN) | ⭐⭐ | — | 帮我转换 {文件} 为 IFC、DWG 或 DGN 格式 | community |
| [ai automation jsons](https://github.com/simealdana/ai-automation-jsons) | ⭐⭐ | — | 帮我导入 {workflow_id} 的 AI 自动化工作流 | community |
| [n8n intelligence](https://github.com/Yukaii/n8n-intelligence) | ⭐⭐ | — | 帮我用 AI 生成一个 n8n 工作流程 | community |
| [n8n cyber intel](https://github.com/Ilesnat/n8n_cyber_intel) | ⭐⭐ | — | 帮我获取最新的网络安全情报信息 | community |
| [srt llm translator](https://github.com/alejandrosnz/srt-llm-translator) | ⭐⭐ | — | 帮我用 AI 翻译 {srt字幕文件} | community |
| [I know there are 100 receipt parsers, but I built one that actually runs for $0 … ⚠️](https://reddit.com/r/n8n/comments/1pg8fsj/i_know_there_are_100_receipt_parsers_but_i_built/) | ⭐⭐ | Telegram | 帮我用 Gemini 识别并整理 {图片} 中的收据信息 | community |
| [After learning this, my AI workflows now cost me 30x less](https://reddit.com/r/n8n/comments/1oplxlb/after_learning_this_my_ai_workflows_now_cost_me/) | ⭐⭐ | — | 帮我构建一个成本优化的 AI 工作流系统 | community |
| [I built this in 2 hours - something Adobe still can’t do after 4+ years.](https://reddit.com/r/n8n/comments/1o5iuj2/i_built_this_in_2_hours_something_adobe_still/) | ⭐⭐ | Openai | 帮我用 Whisper 为 {视频文件} 自动生成字幕 | community |
| [Your n8n Learning Journey Just Got Easier - I Built a Complete YouTube Video Dir…](https://reddit.com/r/n8n/comments/1jm0vfb/your_n8n_learning_journey_just_got_easier_i_built/) | ⭐⭐ | — | 帮我按难度和主题整理 YouTube 视频目录 | community |
| [This n8n workflow scrapes any business URL and writes a full analysis report for…](https://reddit.com/r/n8n/comments/1oksstl/this_n8n_workflow_scrapes_any_business_url_and/) | ⭐⭐ | — | 帮我抓取 {网址} 并生成商业分析报告 | community |
| [😎 Actually making $200/month by selling this workflow as a service. Saving hours… ⚠️](https://reddit.com/r/n8n/comments/1jku65u/actually_making_200month_by_selling_this_workflow/) | ⭐⭐ | — | 帮我处理保险公司数据并自动化工作流程 | community |
| [This workflow generates pencil sketch](https://reddit.com/r/n8n/comments/1rgdw9p/this_workflow_generates_pencil_sketch/) | ⭐⭐ | — | 帮我把 {图片} 转换成铅笔素描 | community |
| [Built an OCR automation pipeline using Sarvam Vision + n8n (messy scans → struct…](https://reddit.com/r/n8n/comments/1rf1sf0/built_an_ocr_automation_pipeline_using_sarvam/) | ⭐⭐ | — | 帮我用 Sarvam Vision 识别 {扫描文件} 并提取结构化数据 | community |
| [HTML🧑‍🎓 Test Your Data Access Techniques with Progressive Expression ChallengesH…](https://n8n.io/workflows/6236-test-your-data-access-techniques-with-progressive-expression-challenges/) | ⭐⭐ | — | 学习数据访问表达式技巧 | official |
| [news pipeline n8n](https://github.com/jeremylongshore/news-pipeline-n8n) | ⭐⭐ | — | 帮我构建每日新闻监控和主题分析流程 | community |
| [Lead Scraping Automation No Code AI ](https://github.com/Sonwa127/Lead-Scraping-Automation-No-Code-AI-) | ⭐⭐ | Gmail, Google Sheets | 帮我从谷歌地图爬取业务数据并保存到表格 | community |
| [n8n workflow](https://github.com/samirsaci/n8n_workflow) | ⭐⭐ | — | 收集YouTube教程中的n8n工作流示例 | community |
| [automatic course certificate generation](https://reddit.com/r/n8n/comments/1qumkw9/automatic_course_certificate_generation/) | ⭐⭐ | Google Sheets | 帮我自动生成课程证书并保存到云盘 | community |
| [HELP I WANT TO SEND IT TO CLIENT TOMORROW!](https://reddit.com/r/n8n/comments/1r5do5l/help_i_want_to_send_it_to_client_tomorrow/) | ⭐⭐ | — | 用SerpAPI爬取谷歌地图商业leads | community |
| [NEW DAY NEW ERROR😅](https://reddit.com/r/n8n/comments/1r88gzd/new_day_new_error/) | ⭐⭐ | — | 解决n8n分页和数据处理问题 | community |
| [This is my workflow. Despite having 74 news items, only one news story keeps rep…](https://community.n8n.io/t/this-is-my-workflow-despite-having-74-news-items-only-one-news-story-keeps-repeating-if-there-are-74-news-stories-they-should-all-appear-differently-but-the-same-one-keeps-recurring-additionally-hinglish-news-appears-in-between-whereas-i-need-the/268441) | ⭐⭐ | — | 修复新闻重复问题 | community |
| [Conversation Initiation Client Data Webhook n8n example](https://community.n8n.io/t/conversation-initiation-client-data-webhook-n8n-example/269321) | ⭐⭐ | — | 帮我构建webhook对话流程 | community |
| [How to read all sheets from an Excel file (.xls/.xlsx) and split them into separ…](https://community.n8n.io/t/how-to-read-all-sheets-from-an-excel-file-xls-xlsx-and-split-them-into-separate-files-in-n8n/186816) | ⭐⭐ | — | 帮我读取Excel所有工作表并拆分成单独文件 | community |
| [Convert JSON to an Excel file](https://n8n.io/workflows/1435-convert-json-to-an-excel-file/) | ⭐ | — | 帮我把 {JSON文件} 转换成 Excel 文件 | official |

## 👥 HR & Recruitment


| Workflow | Difficulty | 🛠 Services | 🤖 OpenClaw | Source |
|----------|-----------|------------|------------|--------|
| [Google SheetsHTTP RequestWhatsApp Business Cloud+10Automated HR Service System w… ⚠️](https://n8n.io/workflows/4975-automated-hr-service-system-with-whatsapp-gpt-4-classification-and-google-workspace/) | ⭐⭐⭐ | Whatsapp, Google Sheets | 用WhatsApp和GPT-4构建HR服务系统 | official |
| [Google SheetsGoogle DriveSummarization Chain+4Resume Screening & Evaluation Syst…](https://n8n.io/workflows/5453-resume-screening-and-evaluation-system-with-gemini-ai-google-sheets-and-drive-for-hr/) | ⭐⭐⭐ | Google Sheets | 帮我筛选和评估简历 | official |
| [Google CalendarGmailCode+3Interview Scheduling Automation with Google Sheets, Ca… ⚠️](https://n8n.io/workflows/5001-interview-scheduling-automation-with-google-sheets-calendar-gmail-and-gpt-4o/) | ⭐⭐⭐ | Gmail, Google Sheets | 自动化面试日程安排和邮件通知 | official |
| [Google SheetsGmailCode+1Generate and Email PDF Payslips from Google Sheets with … ⚠️](https://n8n.io/workflows/10650-generate-and-email-pdf-payslips-from-google-sheets-with-gmail/) | ⭐⭐⭐ | Gmail, Google Sheets | 帮我从Google Sheets生成工资单PDF并发送 | official |
| [Google SheetsHTTP RequestTelegram+5AI Candidate Screening Pipeline: LinkedIn to … ⚠️](https://n8n.io/workflows/10045-ai-candidate-screening-pipeline-linkedin-to-telegram-with-gemini-and-apify/) | ⭐⭐⭐ | Telegram, Google Sheets | 从LinkedIn筛选候选人并推送至Telegram | official |
| [Google DriveGmailGoogle DocsAutomated New Hire Appointment Letters with Google D… ⚠️](https://n8n.io/workflows/5879-automated-new-hire-appointment-letters-with-google-docs-hr-approval-and-gmail/) | ⭐⭐⭐ | Gmail | 帮我自动生成新员工任职信并发送审批 | official |
| [Google SheetsGoogle DriveSummarization Chain+4AI Automated HR Workflow for CV An…](https://n8n.io/workflows/2860-ai-automated-hr-workflow-for-cv-analysis-and-candidate-evaluation/) | ⭐⭐⭐ | Google Sheets | 自动分析简历并评估候选人 | official |
| [This automation scrapes LinkedIn jobs, customizes my resume for each of them and…](https://reddit.com/r/n8n/comments/1qsz9qj/this_automation_scrapes_linkedin_jobs_customizes/) | ⭐⭐⭐ | — | 帮我自动爬取职位并定制简历 | community |
| [I built a fully automated job application pipeline in n8n — daily scheduling, AI…](https://reddit.com/r/n8n/comments/1r95t1k/i_built_a_fully_automated_job_application/) | ⭐⭐⭐ | — | 自动化招聘流程和智能求职信生成 | community |
| [How 8 n8n workflows replaced our entire staff scheduling system](https://reddit.com/r/n8n/comments/1rb4rbs/how_8_n8n_workflows_replaced_our_entire_staff/) | ⭐⭐⭐ | — | 帮我自动化员工排班系统 | community |
| [Google SheetsBasic LLM ChainStructured Output Parser+2🤖 Automate CV Screening wi…](https://n8n.io/workflows/7456-automate-cv-screening-with-ai-candidate-analysis/) | ⭐⭐ | Google Sheets | 自动化简历筛选和候选人分析 | official |
| [TelegramCodeAutomate Job Application Processing from Forms to Telegram for HR Te… ⚠️](https://n8n.io/workflows/5713-automate-job-application-processing-from-forms-to-telegram-for-hr-teams/) | ⭐⭐ | Telegram | 自动处理招聘申请表并发送到Telegram | official |

## 🛒 E-commerce & Sales


| Workflow | Difficulty | 🛠 Services | 🤖 OpenClaw | Source |
|----------|-----------|------------|------------|--------|
| [I built an AI automation that converts static product images into animated demo …](https://reddit.com/r/n8n/comments/1odi3hf/i_built_an_ai_automation_that_converts_static/) | ⭐⭐⭐ | — | 帮我将 {产品图片URL} 转换成动画演示视频 | community |
| [I recreated a dentist voice agent making $24K/yr using ElevenLabs. Handles after… ⚠️](https://reddit.com/r/n8n/comments/1m37l5z/i_recreated_a_dentist_voice_agent_making_24kyr/) | ⭐⭐⭐ | — | 帮我用 ElevenLabs 创建牙医语音智能体处理预约 | community |
| [I built a UGC video ad generator that analyzes any product image, generates an i…](https://reddit.com/r/n8n/comments/1o39gpf/i_built_a_ugc_video_ad_generator_that_analyzes/) | ⭐⭐⭐ | Openai | 帮我用 Sora 2 根据 {产品图片} 生成 UGC 视频广告 | community |
| [Built a WhatsApp AI Bot for Nail Salons ⚠️](https://reddit.com/r/n8n/comments/1l8v8jy/built_a_whatsapp_ai_bot_for_nail_salons/) | ⭐⭐⭐ | Whatsapp, Redis | 帮我构建WhatsApp AI机器人管理美甲店预约 | community |
| [I built an AI automation that generates unlimited consistent character UGC ads f…](https://reddit.com/r/n8n/comments/1or1gwi/i_built_an_ai_automation_that_generates_unlimited/) | ⭐⭐⭐ | — | 帮我用 Sora 2 生成电商品牌的一致性角色广告视频 | community |
| [I swear I didn’t mean to automate the hardest part of our content workflow… but …](https://reddit.com/r/n8n/comments/1p7bytg/i_swear_i_didnt_mean_to_automate_the_hardest_part/) | ⭐⭐⭐ | — | 帮我将 {产品图片} 批量转换成商品视频 | community |
| [n8n whatsapp automation ⚠️](https://github.com/mubashir-786/n8n-whatsapp-automation) | ⭐⭐⭐ | Whatsapp | 搭建WhatsApp订单自动化处理系统 | community |

## 💰 Finance & Trading


| Workflow | Difficulty | 🛠 Services | 🤖 OpenClaw | Source |
|----------|-----------|------------|------------|--------|
| [Built an AI-Powered Personal Finance Tracker in n8n (Telegram + LLM + MongoDB)](https://reddit.com/r/n8n/comments/1r4eycg/built_an_aipowered_personal_finance_tracker_in/) | ⭐⭐⭐ | Telegram | 构建AI财务追踪工作流 | community |

## 🔧 DevOps & Engineering


| Workflow | Difficulty | 🛠 Services | 🤖 OpenClaw | Source |
|----------|-----------|------------|------------|--------|
| [nanobrowser](https://github.com/nanobrowser/nanobrowser) | ⭐⭐⭐ | Openai | 帮我用nanobrowser自动化浏览 {网址} 并执行任务 | community |
| [bytechef](https://github.com/bytechefhq/bytechef) | ⭐⭐⭐ | — | 帮我用 bytechef 编排 {系统名} 的 API 工作流 | community |
| [openclaw n8n stack](https://github.com/caprihan/openclaw-n8n-stack) | ⭐⭐⭐ | — | 帮我用 OpenClaw AI 智能代理自动化执行 {工作流任务} | community |
| [n8n skills](https://github.com/czlonkowski/n8n-skills) | ⭐⭐⭐ | Claude | 帮我使用 n8n skills 构建一个完美的工作流 | community |
| [n8n claude code guide](https://github.com/theNetworkChuck/n8n-claude-code-guide) | ⭐⭐⭐ | Claude | 帮我连接 n8n 到 Claude Code 实现自动化工作流 | community |
| [antigravity n8n skills](https://github.com/WilkoMarketing/antigravity-n8n-skills) | ⭐⭐⭐ | Claude | 帮我配置 n8n workflow 的 {节点名} 节点 | community |
| [I Crushed My AI Video Costs to $0. Here is the Fully Self-Hosted "YouTube Factor…](https://reddit.com/r/n8n/comments/1ptqtbp/i_crushed_my_ai_video_costs_to_0_here_is_the/) | ⭐⭐⭐ | — | 帮我搭建自托管的无脸视频生成工作流降低成本 | community |
| [self hosted video starter kit](https://github.com/jaypetersdotdev/self-hosted-video-starter-kit) | ⭐⭐⭐ | — | 搭建本地视频自动化处理栈 | community |
| [n8n CyberSecurity Workflows ⚠️](https://github.com/mahaishu/n8n-CyberSecurity-Workflows) | ⭐⭐⭐ | — | 自动化网络安全任务 | community |
| [What I’ve learned scaling n8n from a $6 droplet to 400k+ executions/month](https://reddit.com/r/n8n/comments/1kfmifs/what_ive_learned_scaling_n8n_from_a_6_droplet_to/) | ⭐⭐⭐ | Redis | 学习n8n生产环境扩展方案 | community |
| [I got tired of managing my n8n workflows from mobile… so I built this.](https://reddit.com/r/n8n/comments/1r8e7m4/i_got_tired_of_managing_my_n8n_workflows_from/) | ⭐⭐⭐ | — | 构建移动端n8n工作流管理系统 | community |
| [Controlling mobile devices (real and virtual) from n8n workflow. Self-healing mo…](https://reddit.com/r/n8n/comments/1r7d7gt/controlling_mobile_devices_real_and_virtual_from/) | ⭐⭐⭐ | — | 学习移动设备自动化控制和自愈流程 | community |
| [I've transformed the way I manage my agents for Software Dev using a local N8N+K…](https://reddit.com/r/n8n/comments/1rdvfr5/ive_transformed_the_way_i_manage_my_agents_for/) | ⭐⭐⭐ | Claude, Github | 用N8N+Kanban管理软件开发代理 | community |
| [Did you know you can scale n8n by running separate n8n processes?](https://reddit.com/r/n8n/comments/1r07dkw/did_you_know_you_can_scale_n8n_by_running/) | ⭐⭐⭐ | — | 帮我搭建n8n分布式部署架构 | community |
| [N8n-claw: OpenClaw in n8n](https://community.n8n.io/t/n8n-claw-openclaw-in-n8n/271756) | ⭐⭐⭐ | — | 集成 OpenClaw 进行自动化编排 | community |
| [N8n + Grafana Full Node.js Metrics Dashboard (JSON Example Included!)](https://community.n8n.io/t/n8n-grafana-full-node-js-metrics-dashboard-json-example-included/115366) | ⭐⭐⭐ | — | 帮我构建N8n与Grafana的监控仪表板 | community |
| [Back Up Your n8n Workflows To Github](https://n8n.io/workflows/1534-back-up-your-n8n-workflows-to-github/) | ⭐⭐ | Github | 帮我备份 n8n workflow 到 {GitHub仓库} | official |
| [SupabaseLearn Secure Webhook APIs with Authentication and Supabase IntegrationTh…](https://n8n.io/workflows/8258-learn-secure-webhook-apis-with-authentication-and-supabase-integration/) | ⭐⭐ | Supabase | 帮我配置 Supabase Webhook 认证和安全集成 | official |
| [build ai agents and automate workflows with n8n 5437042](https://github.com/LinkedInLearning/build-ai-agents-and-automate-workflows-with-n8n-5437042) | ⭐⭐ | — | 帮我搭建 AI agent 并自动化 n8n workflow | community |
| [FlowMetr](https://github.com/FlowMetr/FlowMetr) | ⭐⭐ | — | 帮我查看 FlowMetr 的 workflow 监控指标 | community |
| [n8n Workflow Builder Ai](https://github.com/farhansrambiyan/n8n-Workflow-Builder-Ai) | ⭐⭐ | Openai | 帮我用 AI 生成 n8n workflow 的 JSON 配置 | community |
| [n8n nodes openai langfuse](https://github.com/rorubyy/n8n-nodes-openai-langfuse) | ⭐⭐ | Openai | 帮我集成 Langfuse 监控 OpenAI 对话流程 | community |
| [n8n skills](https://github.com/haunchen/n8n-skills) | ⭐⭐ | — | 帮我用 n8n 自动化执行 {devops任务} | community |
| [awesome claude plugins](https://github.com/quemsah/awesome-claude-plugins) | ⭐⭐ | Claude, Github | 帮我收集 {GitHub仓库} 的Claude插件采用指标 | community |
| [claude workflow generator](https://github.com/Kookylo/claude_workflow_generator) | ⭐⭐ | Claude | 帮我生成一个专业的 n8n DevOps 自动化工作流 | community |
| [20+ Useful, Focused Tools That Work Seamlessly with n8n](https://reddit.com/r/n8n/comments/1kp05jl/20_useful_focused_tools_that_work_seamlessly_with/) | ⭐⭐ | Notion | 帮我查看与 n8n 集成的 {工具名称} 及其 DevOps 工作流 | community |
| [I THINK I JUST CRACKED IT!! An n8n Workflow generator! ⚠️](https://reddit.com/r/n8n/comments/1kthlcf/i_think_i_just_cracked_it_an_n8n_workflow/) | ⭐⭐ | Slack | 帮我根据 {需求描述} 生成可导入的 n8n workflow | community |
| [Creating an API endpoint](https://n8n.io/workflows/1750-creating-an-api-endpoint/) | ⭐⭐ | — | 帮我创建一个API接口 | official |
| [I built a free tool to analyze and audit n8n workflows - would love your feedbac…](https://reddit.com/r/n8n/comments/1qvpan3/i_built_a_free_tool_to_analyze_and_audit_n8n/) | ⭐⭐ | — | 分析n8n工作流问题和最佳实践 | community |
| [Determine version of currently running n8n (introspection)](https://community.n8n.io/t/determine-version-of-currently-running-n8n-introspection/138096) | ⭐⭐ | — | 获取n8n实例版本信息的workflow方案 | community |
| [Very quick quickstart](https://n8n.io/workflows/1700-very-quick-quickstart/) | ⭐ | — | 快速了解n8n工作流基础 | official |
| [n8nworkflows.xyz: All n8n Workflows Now Available on GitHub](https://reddit.com/r/n8n/comments/1owt1z5/n8nworkflowsxyz_all_n8n_workflows_now_available/) | ⭐ | Github | 查找n8n工作流模板和示例 | community |
| [A simple file upload workflow](https://community.n8n.io/t/a-simple-file-upload-workflow/93189) | ⭐ | — | 帮我构建一个简单的文件上传工作流 | community |

## 🎧 Customer Support


| Workflow | Difficulty | 🛠 Services | 🤖 OpenClaw | Source |
|----------|-----------|------------|------------|--------|
| [customer support ai agent](https://github.com/Muneeb20019/customer-support-ai-agent) | ⭐⭐⭐ | — | 构建AI客服机器人工作流 | community |
| [n8n advanced telegram support ticket management workflow ⚠️](https://github.com/Automations-Project/n8n-advanced-telegram-support-ticket-management-workflow) | ⭐⭐⭐ | Telegram | 搭建Telegram客服工单管理系统 | community |
| [Automating Labor Law Client Intake via WhatsApp with AI and Automation Tools](https://community.n8n.io/t/automating-labor-law-client-intake-via-whatsapp-with-ai-and-automation-tools/108750) | ⭐⭐⭐ | Whatsapp | 帮我搭建WhatsApp客户咨询自动化流程 | community |
| [Built a Chatbot Inbox for n8n - Am I the Only One with This Problem?](https://community.n8n.io/t/built-a-chatbot-inbox-for-n8n-am-i-the-only-one-with-this-problem/223234) | ⭐⭐⭐ | — | 帮我构建聊天机器人收件箱工作流 | community |
| [someone tried selling me an ai automation for $6,000 and i ended up building it …](https://reddit.com/r/n8n/comments/1qx08uu/someone_tried_selling_me_an_ai_automation_for/) | ⭐⭐ | — | 帮我构建客户入站流程自动化 | community |
| [How I helped a local massage studio reclaim 6 hours a week with a simple AI appo…](https://reddit.com/r/n8n/comments/1ri5ts8/how_i_helped_a_local_massage_studio_reclaim_6/) | ⭐⭐ | — | 自动化按摩工作室的预约提醒流程 | community |
| [How to create a webhook triggered workflow with Wait on Form Submit and Respond …](https://community.n8n.io/t/how-to-create-a-webhook-triggered-workflow-with-wait-on-form-submit-and-respond-to-webhook/192098) | ⭐⭐ | — | 帮我创建webhook触发的表单提交工作流 | community |

## Contributing

Contributions welcome! Please read CONTRIBUTING.md first.

## Data Sources

n8n official template library · GitHub · Reddit r/n8n · n8n Community Forum

Last updated: 2026-03-02

## License

MIT
