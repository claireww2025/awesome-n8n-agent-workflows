# awesome-n8n-agent-workflows [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of n8n workflows for AI Agents — with OpenClaw/MCP integration guides and safety labels for irreversible operations.

![workflows](https://img.shields.io/badge/workflows-250-blue)
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

- [🤖 AI Agents](#ai-agents) (39 workflows)
- [🔌 MCP Server Integration](#mcp-server-integration) (16 workflows)
- [🧠 Memory & Long-term Context](#memory--long-term-context) (8 workflows)
- [📚 RAG & Knowledge Base](#rag--knowledge-base) (8 workflows)
- [📱 Social Media Automation](#social-media-automation) (50 workflows)
- [📧 Email & Messaging](#email--messaging) (18 workflows)
- [📊 Data Processing & Analytics](#data-processing--analytics) (51 workflows)
- [👥 HR & Recruitment](#hr--recruitment) (12 workflows)
- [🛒 E-commerce & Sales](#e-commerce--sales) (7 workflows)
- [💰 Finance & Trading](#finance--trading) (1 workflows)
- [🔧 DevOps & Engineering](#devops--engineering) (33 workflows)
- [🎧 Customer Support](#customer-support) (7 workflows)


## 🤖 AI Agents


| Workflow | Difficulty | 🛠 Services | 🤖 OpenClaw | Source |
|----------|-----------|------------|------------|--------|
| [Google SheetsHTTP RequestTelegram+7Create & Upload AI-Generated ASMR YouTube Sho… ⚠️](https://n8n.io/workflows/5110-create-and-upload-ai-generated-asmr-youtube-shorts-with-seedance-fal-ai-and-gpt-4/) | ⭐⭐⭐⭐ | Telegram, Google Sheets | Video automation | official |
| [Google SheetsHTTP RequestGoogle Drive+1Generate AI Videos with Google Veo3, Save… ⚠️](https://n8n.io/workflows/4846-generate-ai-videos-with-google-veo3-save-to-google-drive-and-upload-to-youtube/) | ⭐⭐⭐ | Google Sheets | Video automation | official |
| [HTTP RequestGoogle DriveTransform Old Photos into Animated Videos with FLUX & Kl…](https://n8n.io/workflows/5755-transform-old-photos-into-animated-videos-with-flux-and-kling-ai-for-social-media/) | ⭐⭐⭐ | — | Video automation | official |
| [HTTP RequestCodeAI Agent+1Transform Long Videos into Viral Shorts with AI and Sc… ⚠️](https://n8n.io/workflows/9867-transform-long-videos-into-viral-shorts-with-ai-and-schedule-to-social-media-using-whisper-and-gemini/) | ⭐⭐⭐ | — | Video automation | official |
| [Google SheetsHTTP RequestGoogle Drive+2Automate AI Video Creation & Multi-Platfo… ⚠️](https://n8n.io/workflows/10358-automate-ai-video-creation-and-multi-platform-publishing-with-gpt-4-veo-31-and-blotato/) | ⭐⭐⭐ | Google Sheets | Video automation | official |
| [Google SheetsHTTP RequestTelegram+7Automate & Publish Video Ad Campaigns with Na… ⚠️](https://n8n.io/workflows/9200-automate-and-publish-video-ad-campaigns-with-nanobanana-seedream-gpt-4o-veo-3/) | ⭐⭐⭐ | Telegram, Google Sheets | Video automation | official |
| [HTTP RequestTelegramCode+5Create AI Viral Videos using NanoBanana 2 PRO & VEO3.1… ⚠️](https://n8n.io/workflows/11204-create-ai-viral-videos-using-nanobanana-2-pro-and-veo31-and-publish-via-blotato/) | ⭐⭐⭐ | Telegram | Video automation | official |
| [AI Builder with n8n Create Agents Voice Agents](https://github.com/M-F-Tushar/AI-Builder-with-n8n-Create-Agents-Voice-Agents) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [ai video clipping tools ⚠️](https://github.com/fboucher/ai-video-clipping-tools) | ⭐⭐⭐ | — | Video automation | community |
| [n8n automation workflows ⚠️](https://github.com/swapnilmandloi312/n8n-automation-workflows) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [Content creation with N8N AI Agent ⚠️](https://github.com/shubhamnevgi/Content-creation-with-N8N-AI-Agent) | ⭐⭐⭐ | — | Video automation | community |
| [ai video automation ⚠️](https://github.com/tumuexe44/ai-video-automation) | ⭐⭐⭐ | — | Video automation | community |
| [n8n workflow project lists](https://github.com/Orekidesu/n8n-workflow-project-lists) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [I built a workflow to replicate ANY image style using Nano Banana Pro! And I’m l…](https://reddit.com/r/n8n/comments/1qwq4k6/i_built_a_workflow_to_replicate_any_image_style/) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [Agentic AI browsers are insane I mean just look at this](https://reddit.com/r/n8n/comments/1r286z1/agentic_ai_browsers_are_insane_i_mean_just_look/) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [I Built an AI Construction Timelapse Video Generator (I Just Feed It Before &amp…](https://reddit.com/r/n8n/comments/1qwky0h/i_built_an_ai_construction_timelapse_video/) | ⭐⭐⭐ | — | Video automation | community |
| [my n8n AI agent burned $63 in API credits retrying the same failed node 800 time… ⚠️](https://reddit.com/r/n8n/comments/1qy9eyv/my_n8n_ai_agent_burned_63_in_api_credits_retrying/) | ⭐⭐⭐ | Openai | Use with OpenClaw | community |
| [I tried “vibe coding” a full SaaS with Claude + n8n — this surprised me](https://reddit.com/r/n8n/comments/1r6q5pb/i_tried_vibe_coding_a_full_saas_with_claude_n8n/) | ⭐⭐⭐ | Claude | Use with OpenClaw | community |
| [Build agent-based apps in n8n without building an entire RAG pipeline](https://reddit.com/r/n8n/comments/1qv1bxp/build_agentbased_apps_in_n8n_without_building_an/) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [Sharing a project I had built 4 months ago, so that it doesn't collect digital d…](https://reddit.com/r/n8n/comments/1r4nmyy/sharing_a_project_i_had_built_4_months_ago_so/) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [Built a fully automated AI health video workflow with n8n + Veo 3 ⚠️](https://reddit.com/r/n8n/comments/1qx5564/built_a_fully_automated_ai_health_video_workflow/) | ⭐⭐⭐ | Google Sheets | Video automation | community |
| [As promised, sharing my Restaurant AI Voice Agent + Table Booking Automation](https://reddit.com/r/n8n/comments/1r83qu1/as_promised_sharing_my_restaurant_ai_voice_agent/) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [Create business docs and finds leads](https://reddit.com/r/n8n/comments/1rf8hyi/create_business_docs_and_finds_leads/) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [I tried “vibe coding” a full SaaS with Claude + n8n — this surprised me](https://reddit.com/r/n8n/comments/1r9iazv/i_tried_vibe_coding_a_full_saas_with_claude_n8n/) | ⭐⭐⭐ | Claude | Use with OpenClaw | community |
| [I added persistent memory to my n8n AI Agent — it now remembers users across ses…](https://reddit.com/r/n8n/comments/1rg56dy/i_added_persistent_memory_to_my_n8n_ai_agent_it/) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [Retrieve LLM Token Usage in AI Agents](https://community.n8n.io/t/retrieve-llm-token-usage-in-ai-agents/68714) | ⭐⭐⭐ | — | Token & cost tracking | community |
| [How I Built a YouTube Automation That Creates Viral Long-Form Videos with AI](https://community.n8n.io/t/how-i-built-a-youtube-automation-that-creates-viral-long-form-videos-with-ai/105676) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [[Use Case] Built an AI Agent That Generates SEO + Emotionally Optimized Content …](https://community.n8n.io/t/use-case-built-an-ai-agent-that-generates-seo-emotionally-optimized-content-for-blog-social-newsletter-landing-pages-geo/119051) | ⭐⭐⭐ | — | SEO content | community |
| [Made an openai-compatible bridge for n8n workflows](https://community.n8n.io/t/made-an-openai-compatible-bridge-for-n8n-workflows/205640) | ⭐⭐⭐ | Openai | Use with OpenClaw | community |
| [Outbound Twilio Call using ElevenLabs Voice/Agent](https://community.n8n.io/t/outbound-twilio-call-using-elevenlabs-voice-agent/92117) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [Ocr with AI agent](https://community.n8n.io/t/ocr-with-ai-agent/114686) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [WhatsApp Ai Agent for car rent company](https://community.n8n.io/t/whatsapp-ai-agent-for-car-rent-company/263919) | ⭐⭐⭐ | Whatsapp | Use with OpenClaw | community |
| [Criando agendamento com captação de lead no n8n usando IA](https://community.n8n.io/t/criando-agendamento-com-captacao-de-lead-no-n8n-usando-ia/261338) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [▶️ Full video guide: n8n AI chatbot with human takeover (free template)](https://community.n8n.io/t/full-video-guide-n8n-ai-chatbot-with-human-takeover-free-template/266732) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [Telegram AI Chatbot with Human Takeover](https://community.n8n.io/t/telegram-ai-chatbot-with-human-takeover/265056) | ⭐⭐⭐ | Telegram | Use with OpenClaw | community |
| [n8n ai automations](https://github.com/lucaswalter/n8n-ai-automations) | ⭐⭐ | — | Use with OpenClaw | community |
| [Telegram AI Agent ⚠️](https://reddit.com/r/n8n/comments/1r582pm/telegram_ai_agent/) | ⭐⭐ | Telegram | Use with OpenClaw | community |
| [Automating Content Generation with n8n](https://reddit.com/r/n8n/comments/1qsp0m4/automating_content_generation_with_n8n/) | ⭐⭐ | — | Use with OpenClaw | community |
| [Automated Blog Publishing Workflow Using n8n – Need Help to Humanize AI Content](https://community.n8n.io/t/automated-blog-publishing-workflow-using-n8n-need-help-to-humanize-ai-content/118721) | ⭐⭐ | — | Use with OpenClaw | community |

## 🔌 MCP Server Integration


| Workflow | Difficulty | 🛠 Services | 🤖 OpenClaw | Source |
|----------|-----------|------------|------------|--------|
| [End to End Agentic Ai Automation Lab](https://github.com/MDalamin5/End-to-End-Agentic-Ai-Automation-Lab) | ⭐⭐⭐⭐ | — | Use with OpenClaw | community |
| [RedisAI AgentOpenAI Chat Model+3Build your own N8N Workflows MCP ServerThis n8n …](https://n8n.io/workflows/3770-build-your-own-n8n-workflows-mcp-server/) | ⭐⭐⭐ | Openai, Redis | Use with OpenClaw | official |
| [project nova](https://github.com/dujonwalker/project-nova) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [n8n workflow builder mcp](https://github.com/ifmelate/n8n-workflow-builder-mcp) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [n8n nodes agent2agent ⚠️](https://github.com/pjawz/n8n-nodes-agent2agent) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [n8n openai bridge](https://github.com/sveneisenschmidt/n8n-openai-bridge) | ⭐⭐⭐ | Openai | Use with OpenClaw | community |
| [n8n workflow builder](https://github.com/makafeli/n8n-workflow-builder) | ⭐⭐⭐ | Claude | Use with OpenClaw | community |
| [mcp n8n workflow builder](https://github.com/salacoste/mcp-n8n-workflow-builder) | ⭐⭐⭐ | Claude | Use with OpenClaw | community |
| [claude mcps and prompts](https://github.com/tiagolemos05/claude-mcps-and-prompts) | ⭐⭐⭐ | Claude | SEO content | community |
| [n8n workflow sdk mcp](https://github.com/octionic/n8n-workflow-sdk-mcp) | ⭐⭐⭐ | Claude | Use with OpenClaw | community |
| [mcp n8n server](https://github.com/ahmadsoliman/mcp-n8n-server) | ⭐⭐⭐ | Claude | Use with OpenClaw | community |
| [I Replaced $100+/month in GEMINI API Costs with a €2000 eBay Mac Studio — Here i… ⚠️](https://reddit.com/r/n8n/comments/1ri8922/i_replaced_100month_in_gemini_api_costs_with_a/) | ⭐⭐⭐ | Telegram | Use with OpenClaw | community |
| [I built n8n-mcp-lite: A token-optimized Model Context Protocol for Claude/AI age…](https://reddit.com/r/n8n/comments/1rgpbf6/i_built_n8nmcplite_a_tokenoptimized_model_context/) | ⭐⭐⭐ | Claude | Use with OpenClaw | community |
| [n8n manager for ai agents](https://github.com/czlonkowski/n8n-manager-for-ai-agents) | ⭐⭐ | Claude | Use with OpenClaw | community |
| [n8n deepseek](https://github.com/rubickecho/n8n-deepseek) | ⭐⭐ | Openai | Use with OpenClaw | community |
| [I made a free MCP server to create short videos locally with n8n - 100% free, op…](https://reddit.com/r/n8n/comments/1k575uq/i_made_a_free_mcp_server_to_create_short_videos/) | ⭐⭐ | Github | Video automation | community |

## 🧠 Memory & Long-term Context


| Workflow | Difficulty | 🛠 Services | 🤖 OpenClaw | Source |
|----------|-----------|------------|------------|--------|
| [I Built an AI Agent Army in n8n That Completely Replaced My Personal Assistant](https://reddit.com/r/n8n/comments/1mugdof/i_built_an_ai_agent_army_in_n8n_that_completely/) | ⭐⭐⭐⭐ | Github | Use with OpenClaw | community |
| [AI AgentEmbeddings OpenAICalculator+4Evaluate tool usage accuracy in multi-agent…](https://n8n.io/workflows/5523-evaluate-tool-usage-accuracy-in-multi-agent-ai-workflows-using-evaluation-nodes/) | ⭐⭐⭐ | Openai | Use with OpenClaw | official |
| [AI AgentBasic LLM ChainAnthropic Chat Model+6AI Orchestrator: dynamically Select…](https://n8n.io/workflows/7004-ai-orchestrator-dynamically-selects-models-based-on-input-type/) | ⭐⭐⭐ | — | Use with OpenClaw | official |
| [n8n ai agents](https://github.com/GhufranBarcha/n8n_ai_agents) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [I Built a Personal AI Assistant That Runs My Life Through WhatsApp, Powered by n… ⚠️](https://reddit.com/r/n8n/comments/1mtv9re/i_built_a_personal_ai_assistant_that_runs_my_life/) | ⭐⭐⭐ | Whatsapp | Use with OpenClaw | community |
| [Anyone here using Human-in-the-Loop for AI agents in n8n? ⚠️](https://reddit.com/r/n8n/comments/1rhx3u4/anyone_here_using_humanintheloop_for_ai_agents_in/) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [AI agent chat](https://n8n.io/workflows/1954-ai-agent-chat/) | ⭐⭐ | — | Use with OpenClaw | official |
| [Claude Project to n8n Workflow ⚠️](https://github.com/MobinMithun/Claude-Project-to-n8n-Workflow) | ⭐⭐ | Claude | Use with OpenClaw | community |

## 📚 RAG & Knowledge Base


| Workflow | Difficulty | 🛠 Services | 🤖 OpenClaw | Source |
|----------|-----------|------------|------------|--------|
| [chatwiki](https://github.com/zhimaAi/chatwiki) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [n8n automation 2025 AI Agent Suite ⚠️](https://github.com/tannu64/n8n-automation-2025-AI-Agent-Suite) | ⭐⭐⭐ | Telegram, Whatsapp, Gmail | Use with OpenClaw | community |
| [n8n template and documentation for RAG](https://github.com/Kohnnn/n8n-template-and-documentation-for-RAG) | ⭐⭐⭐ | Claude | Use with OpenClaw | community |
| [Update: My RAG Agent is alive! From Google Drive ingestion to a working Chat int…](https://reddit.com/r/n8n/comments/1rhqxkb/update_my_rag_agent_is_alive_from_google_drive/) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [I built a RAG pipeline using n8n that converts Google Drive documents into a sea…](https://reddit.com/r/n8n/comments/1rdadp2/i_built_a_rag_pipeline_using_n8n_that_converts/) | ⭐⭐⭐ | Telegram | Use with OpenClaw | community |
| [Scrape and summarize webpages with AI](https://n8n.io/workflows/1951-scrape-and-summarize-webpages-with-ai/) | ⭐⭐ | — | Use with OpenClaw | official |
| [OpenConstructionEstimate DDC CWICR](https://github.com/datadrivenconstruction/OpenConstructionEstimate-DDC-CWICR) | ⭐⭐ | — | Use with OpenClaw | community |
| [n8n nodes universal reranker](https://github.com/dalisys/n8n-nodes-universal-reranker) | ⭐⭐ | Openai | Use with OpenClaw | community |

## 📱 Social Media Automation


| Workflow | Difficulty | 🛠 Services | 🤖 OpenClaw | Source |
|----------|-----------|------------|------------|--------|
| [Google SheetsHTTP RequestTelegram+3Auto-Create TikTok Videos with VEED.io AI Ava… ⚠️](https://n8n.io/workflows/10000-auto-create-tiktok-videos-with-veedio-ai-avatars-elevenlabs-and-gpt-4/) | ⭐⭐⭐⭐ | Telegram, Google Sheets | Video automation | official |
| [workflow n8n ⚠️](https://github.com/ojonatasquirino/workflow-n8n) | ⭐⭐⭐ | Openai, Whatsapp | Use with OpenClaw | community |
| [Secretaria IA Automacao Atendimento WhatsApp n8n OpenAI ⚠️](https://github.com/Rayquazads/Secretaria-IA-Automacao-Atendimento-WhatsApp-n8n-OpenAI) | ⭐⭐⭐ | Openai, Whatsapp | Use with OpenClaw | community |
| [FaceBook Ad Manager System ⚠️](https://github.com/Awaisali36/FaceBook-Ad-Manager-System) | ⭐⭐⭐ | Claude | Use with OpenClaw | community |
| [Built my own AI-UGC automation since everyone else is gatekeeping — dropping it … ⚠️](https://reddit.com/r/n8n/comments/1p6g3py/built_my_own_aiugc_automation_since_everyone_else/) | ⭐⭐⭐ | — | Video automation | community |
| [You can safely discard your 159 node n8n automation that created 500 AI shorts i… ⚠️](https://reddit.com/r/n8n/comments/1lvfz70/you_can_safely_discard_your_159_node_n8n/) | ⭐⭐⭐ | — | Video automation | community |
| [This Automation Took Me From 0 to 175k Followers in Under 12 Months ⚠️](https://reddit.com/r/n8n/comments/1oj8q69/this_automation_took_me_from_0_to_175k_followers/) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [My last SEO automation blew up to 200k views… and V2 fixes every limitation the … ⚠️](https://reddit.com/r/n8n/comments/1phf74d/my_last_seo_automation_blew_up_to_200k_views_and/) | ⭐⭐⭐ | — | SEO content | community |
| [I rebuilt most of OpenClaw's core functionality in a single n8n workflow ⚠️](https://reddit.com/r/n8n/comments/1r24b7c/i_rebuilt_most_of_openclaws_core_functionality_in/) | ⭐⭐⭐ | Telegram, Whatsapp, Supabase | Use with OpenClaw | community |
| [I built a 24/7 AI Receptionist with n8n so our local restaurant never misses a c…](https://reddit.com/r/n8n/comments/1nfx1uj/i_built_a_247_ai_receptionist_with_n8n_so_our/) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [3M views in 3 months, all from this automation that snipes early trending storie… ⚠️](https://reddit.com/r/n8n/comments/1oncgwf/3m_views_in_3_months_all_from_this_automation/) | ⭐⭐⭐ | Openai | Use with OpenClaw | community |
| [I built an AI voice agent that replaced my entire marketing team (creates newsle…](https://reddit.com/r/n8n/comments/1mch7p6/i_built_an_ai_voice_agent_that_replaced_my_entire/) | ⭐⭐⭐ | — | Video automation | community |
| [Built my own AI-UGC automation since everyone else is gatekeeping — dropping it … ⚠️](https://reddit.com/r/n8n/comments/1pyp6dp/built_my_own_aiugc_automation_since_everyone_else/) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [I built a comprehensive Instagram + Messenger chatbot with n8n (with ZERO coding… ⚠️](https://reddit.com/r/n8n/comments/1k4u0c4/i_built_a_comprehensive_instagram_messenger/) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [I Built a Fully Automated Social Media Content Machine that You can Sell to Clie… ⚠️](https://reddit.com/r/n8n/comments/1jlf53k/i_built_a_fully_automated_social_media_content/) | ⭐⭐⭐ | Telegram | Use with OpenClaw | community |
| [I built a WhatsApp chatbot and AI Agent for hotels and the hospitality industry ⚠️](https://reddit.com/r/n8n/comments/1mr2vyq/i_built_a_whatsapp_chatbot_and_ai_agent_for/) | ⭐⭐⭐ | Whatsapp | Use with OpenClaw | community |
| [Free workflow lets you automate video generation for TikTok, Reels, Shorts etc ⚠️](https://reddit.com/r/n8n/comments/1j91dkn/free_workflow_lets_you_automate_video_generation/) | ⭐⭐⭐ | Openai | Video automation | community |
| [I built a self-improving TikTok carousel workflow that learns from its own analy… ⚠️](https://reddit.com/r/n8n/comments/1rgi8ah/i_built_a_selfimproving_tiktok_carousel_workflow/) | ⭐⭐⭐ | — | Video automation | community |
| [I build automations for businesses. Most of you are just scaling your own mess. ⚠️](https://reddit.com/r/n8n/comments/1rf8yyg/i_build_automations_for_businesses_most_of_you/) | ⭐⭐⭐ | Gmail | Use with OpenClaw | community |
| [Google SheetsHTTP RequestLinkedIn Job Finder Automation using Bright Data API & …](https://n8n.io/workflows/4775-linkedin-job-finder-automation-using-bright-data-api-and-google-sheets/) | ⭐⭐⭐ | Google Sheets | Jobs / recruiting | official |
| [Google SheetsHTTP RequestAI Agent+3Generate & Auto-post AI Videos to Social Medi… ⚠️](https://n8n.io/workflows/5035-generate-and-auto-post-ai-videos-to-social-media-with-veo3-and-blotato/) | ⭐⭐⭐ | Google Sheets | Video automation | official |
| [Google SheetsHTTP RequestCode+4Generate AI Viral Videos with Seedance and Upload… ⚠️](https://n8n.io/workflows/5338-generate-ai-viral-videos-with-seedance-and-upload-to-tiktok-youtube-and-instagram/) | ⭐⭐⭐ | Google Sheets | Video automation | official |
| [social story scraper ⚠️](https://github.com/sirlifehacker/social-story-scraper) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [TwitterThreadCreator ⚠️](https://github.com/SohamXYZDev/TwitterThreadCreator) | ⭐⭐⭐ | — | Video automation | community |
| [N8N Automation Suite ⚠️](https://github.com/KanishqGandharv219/N8N-Automation-Suite) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [Linkedin Leadgen ⚠️](https://github.com/Shobhit-Mandal/Linkedin-Leadgen) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [I built an n8n workflow that automates personalized LinkedIn outreach using AI —… ⚠️](https://reddit.com/r/n8n/comments/1r0stwn/i_built_an_n8n_workflow_that_automates/) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [Built a fully automated Google Business Profile posting system with n8n - 625 im… ⚠️](https://reddit.com/r/n8n/comments/1r9718t/built_a_fully_automated_google_business_profile/) | ⭐⭐⭐ | Github | Use with OpenClaw | community |
| [I replaced a 3-person content pipeline with one n8n workflow. YouTube → LinkedIn… ⚠️](https://reddit.com/r/n8n/comments/1r6ui7z/i_replaced_a_3person_content_pipeline_with_one/) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [WhatsApp Cloud - Customer Service automation with Templates - How to handle What…](https://community.n8n.io/t/whatsapp-cloud-customer-service-automation-with-templates-how-to-handle-whatsapp-interactive-button-replies-in-n8n-without-restarting-the-trigger-flow/264125) | ⭐⭐⭐ | Whatsapp | Use with OpenClaw | community |
| [Telegram AI Chatbot ⚠️](https://n8n.io/workflows/1934-telegram-ai-chatbot/) | ⭐⭐ | Telegram | Use with OpenClaw | official |
| [audio chat n8n wasenderapi ⚠️](https://github.com/wasenderapi/audio-chat-n8n-wasenderapi) | ⭐⭐ | Openai | Use with OpenClaw | community |
| [reddit content filter n8n ⚠️](https://github.com/kenandrewmiranda/reddit-content-filter-n8n) | ⭐⭐ | Openai, Slack | Use with OpenClaw | community |
| [I saw someone gatekeep their “Viral IG Script Generator” behind a paywall… so I … ⚠️](https://reddit.com/r/n8n/comments/1ox2api/i_saw_someone_gatekeep_their_viral_ig_script/) | ⭐⭐ | — | Video automation | community |
| [I built this AI Automation to write viral TikTok/IG video scripts (got over 1.8 … ⚠️](https://reddit.com/r/n8n/comments/1loafvx/i_built_this_ai_automation_to_write_viral/) | ⭐⭐ | — | Use with OpenClaw | community |
| [n8n twitter thread fetcher](https://github.com/enescingoz/n8n-twitter-thread-fetcher) | ⭐⭐ | — | Use with OpenClaw | community |
| [Youtube to Discord Automation ⚠️](https://github.com/Baavanadhaz/Youtube-to-Discord-Automation) | ⭐⭐ | Discord | Use with OpenClaw | community |
| [n8n nodes upload post ⚠️](https://github.com/Upload-Post/n8n-nodes-upload-post) | ⭐⭐ | — | Use with OpenClaw | community |
| [n8n discord trigger bot](https://github.com/Jharilela/n8n_discord_trigger_bot) | ⭐⭐ | Discord | Use with OpenClaw | community |
| [n8n discord automation templates ⚠️](https://github.com/nameershah/n8n-discord-automation-templates) | ⭐⭐ | Discord | Use with OpenClaw | community |
| [N8N Agent for discord ⚠️](https://github.com/Alfredd43/N8N-Agent-for-discord) | ⭐⭐ | Discord | Use with OpenClaw | community |
| [discord bot n8n ⚠️](https://github.com/MibzarGalarza/discord-bot-n8n) | ⭐⭐ | Discord | Use with OpenClaw | community |
| [whatsapp n8n bot ⚠️](https://github.com/Whapi-Cloud/whatsapp-n8n-bot) | ⭐⭐ | Whatsapp | Use with OpenClaw | community |
| [I built a "comment → DM" autopilot for Instagram using n8n. Here's exactly how (… ⚠️](https://reddit.com/r/n8n/comments/1r3xj2t/i_built_a_comment_dm_autopilot_for_instagram/) | ⭐⭐ | Google Sheets | Use with OpenClaw | community |
| [Auto reply on FB/IG with a DM if someone comments your post with a certain keywo…](https://community.n8n.io/t/auto-reply-on-fb-ig-with-a-dm-if-someone-comments-your-post-with-a-certain-keyword-they-add/269511) | ⭐⭐ | — | Use with OpenClaw | community |
| [微信公众号自动发布文章：mp-wechat publish articles automaticly](https://community.n8n.io/t/mp-wechat-publish-articles-automaticly/149748) | ⭐⭐ | — | Use with OpenClaw | community |
| [N8N x Social Media x Notion Content Management](https://community.n8n.io/t/n8n-x-social-media-x-notion-content-management/209862) | ⭐⭐ | Notion | Use with OpenClaw | community |
| [How to get Discord messages in n8n](https://community.n8n.io/t/how-to-get-discord-messages-in-n8n/261862) | ⭐⭐ | Discord | Use with OpenClaw | community |
| [Auto reply on FB/IG with a DM if someone comments your post with a certain keywo…](https://community.n8n.io/t/auto-reply-on-fb-ig-with-a-dm-if-someone-comments-your-post-with-a-certain-keyword-they-add/269511) | ⭐⭐ | — | Use with OpenClaw | community |
| [I made my 1st working workflow and I never been so proud ⚠️](https://reddit.com/r/n8n/comments/1lsoams/i_made_my_1st_working_workflow_and_i_never_been/) | ⭐ | — | Use with OpenClaw | community |

## 📧 Email & Messaging


| Workflow | Difficulty | 🛠 Services | 🤖 OpenClaw | Source |
|----------|-----------|------------|------------|--------|
| [i automated the entire cold outreach process in n8n (sorry to whoever's job i ju… ⚠️](https://reddit.com/r/n8n/comments/1jgl5ek/i_automated_the_entire_cold_outreach_process_in/) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [UPDATE! - I automated the entire cold outreach process in n8n (sorry to whoever'… ⚠️](https://reddit.com/r/n8n/comments/1jm842j/update_i_automated_the_entire_cold_outreach/) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [I built an n8n workflow that automatically finds clients and made me my first $2… ⚠️](https://reddit.com/r/n8n/comments/1ndb2tf/i_built_an_n8n_workflow_that_automatically_finds/) | ⭐⭐ | — | Use with OpenClaw | community |
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
| [Stop overpaying for email tools. Seriously.](https://reddit.com/r/n8n/comments/1rcvci4/stop_overpaying_for_email_tools_seriously/) | ⭐⭐ | — | Use with OpenClaw | community |
| [Email Trigger (IMAP)](https://community.n8n.io/t/email-trigger-imap/90114) | ⭐⭐ | — | Use with OpenClaw | community |
| [Extracting email addresses and names from entire email](https://community.n8n.io/t/extracting-email-addresses-and-names-from-entire-email/84145) | ⭐⭐ | — | Use with OpenClaw | community |
| [How to Build an n8n Workflow to Automatically Send Personalized PDFs to Differen…](https://community.n8n.io/t/how-to-build-an-n8n-workflow-to-automatically-send-personalized-pdfs-to-different-recipients/150600) | ⭐⭐ | — | Use with OpenClaw | community |
| [Email Forwarding (Body + PDF) to Telegram fails with "undefined" error - Need JS… ⚠️](https://community.n8n.io/t/email-forwarding-body-pdf-to-telegram-fails-with-undefined-error-need-json-review/261784) | ⭐⭐ | Telegram | Use with OpenClaw | community |

## 📊 Data Processing & Analytics


| Workflow | Difficulty | 🛠 Services | 🤖 OpenClaw | Source |
|----------|-----------|------------|------------|--------|
| [n8n agent](https://github.com/kingler/n8n_agent) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [N8N AI Agents Masterclass](https://github.com/ChinmayKaitade/N8N-AI-Agents-Masterclass) | ⭐⭐⭐ | Openai | Use with OpenClaw | community |
| [seo auditor service](https://github.com/market-analyticx/seo-auditor-service) | ⭐⭐⭐ | Openai | SEO content | community |
| [B2B SaaS Dashboard Generator Agent ⚠️](https://github.com/zachbaumgarten/B2B-SaaS-Dashboard-Generator-Agent) | ⭐⭐⭐ | Claude | Use with OpenClaw | community |
| [I built an AI system that scrapes stories off the internet and generates a daily… ⚠️](https://reddit.com/r/n8n/comments/1l9pff8/i_built_an_ai_system_that_scrapes_stories_off_the/) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [Looks ugly but it is now managing my investments...](https://reddit.com/r/n8n/comments/1oc0mup/looks_ugly_but_it_is_now_managing_my_investments/) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [He wouldn’t share his “AI SEO Blog Automation” so I took it personally and built… ⚠️](https://reddit.com/r/n8n/comments/1otjiub/he_wouldnt_share_his_ai_seo_blog_automation_so_i/) | ⭐⭐⭐ | — | SEO content | community |
| [I didn’t think a “fine, I’ll build it myself” automation post would hit 170K+ vi… ⚠️](https://reddit.com/r/n8n/comments/1ozm3pi/i_didnt_think_a_fine_ill_build_it_myself/) | ⭐⭐⭐ | — | SEO content | community |
| [Friend lost his job, so instead of sympathy, I built him an automation.
It finds…](https://reddit.com/r/n8n/comments/1ov5lb6/friend_lost_his_job_so_instead_of_sympathy_i/) | ⭐⭐⭐ | — | Jobs / recruiting | community |
| [I built an AI automation that writes SEO-optimized articles using Deep Research …](https://reddit.com/r/n8n/comments/1l81jzd/i_built_an_ai_automation_that_writes_seooptimized/) | ⭐⭐⭐ | — | SEO content | community |
| [My father needed a simple video ad... agencies quoted $4,000. So I built him an …](https://reddit.com/r/n8n/comments/1po5xvy/my_father_needed_a_simple_video_ad_agencies/) | ⭐⭐⭐ | — | Video automation | community |
| [I made this n8n workflow. One  click (+ 4 days later)… and it turns a 1000+ page…](https://reddit.com/r/n8n/comments/1nk1tr3/i_made_this_n8n_workflow_one_click_4_days_later/) | ⭐⭐⭐ | — | Video automation | community |
| [I've had multiple clients hire me to build this simple automation. It finds new …](https://reddit.com/r/n8n/comments/1ocnoyj/ive_had_multiple_clients_hire_me_to_build_this/) | ⭐⭐⭐ | — | Jobs / recruiting | community |
| [Finally got my first AI to Word document generator working - 40-100 pages from a…](https://reddit.com/r/n8n/comments/1pc37u4/finally_got_my_first_ai_to_word_document/) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [How We Built a News Automation System That Now Drives 10,000 Clicks a Month](https://reddit.com/r/n8n/comments/1p0z4yv/how_we_built_a_news_automation_system_that_now/) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [Built a Personal “Wealth Control Tower” Workflow to Monitor, Automate &amp; Stre…](https://reddit.com/r/n8n/comments/1rgy26a/built_a_personal_wealth_control_tower_workflow_to/) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [I analysed 2,000+ n8n workflows and this is what I learned](https://reddit.com/r/n8n/comments/1l1f6n8/i_analysed_2000_n8n_workflows_and_this_is_what_i/) | ⭐⭐⭐ | Claude | Use with OpenClaw | community |
| [Just sync the calendar… not as easy as I thought](https://reddit.com/r/n8n/comments/1qyqj81/just_sync_the_calendar_not_as_easy_as_i_thought/) | ⭐⭐⭐ | — | Calendar sync | community |
| [Workflow that gets a CSV of 2K rworkows and create a summary with insights and a…](https://community.n8n.io/t/workflow-that-gets-a-csv-of-2k-rworkows-and-create-a-summary-with-insights-and-actionable-items/266118) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [Generate a temporary URL for files along with binary data within a workflow](https://community.n8n.io/t/generate-a-temporary-url-for-files-along-with-binary-data-within-a-workflow/72315) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [Workflow that gets a CSV of 2K rworkows and create a summary with insights and a…](https://community.n8n.io/t/workflow-that-gets-a-csv-of-2k-rworkows-and-create-a-summary-with-insights-and-actionable-items/266118) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [Joining different datasets](https://n8n.io/workflows/1747-joining-different-datasets/) | ⭐⭐ | — | Use with OpenClaw | official |
| [OpenAI GPT-3: Company Enrichment from website content](https://n8n.io/workflows/1862-openai-gpt-3-company-enrichment-from-website-content/) | ⭐⭐ | Openai | Use with OpenClaw | official |
| [Pulling data from services that n8n doesn’t have a pre-built integration for](https://n8n.io/workflows/1748-pulling-data-from-services-that-n8n-doesnt-have-a-pre-built-integration-for/) | ⭐⭐ | — | Use with OpenClaw | official |
| [Basic LLM ChainStructured Output ParserOpenRouter Chat ModelAuto Generate Descri…](https://n8n.io/workflows/10889-auto-generate-descriptive-node-names-with-ai-for-workflow-readability/) | ⭐⭐ | — | Use with OpenClaw | official |
| [Google SheetsAI AgentAnthropic Chat Model+3Track AI Agent token usage and estima… ⚠️](https://n8n.io/workflows/5541-track-ai-agent-token-usage-and-estimate-costs-in-google-sheets/) | ⭐⭐ | Google Sheets | Token & cost tracking | official |
| [HTTP RequestTelegramHubSpot+1Design scalable sync workflows with Data Tables, Pr… ⚠️](https://n8n.io/workflows/13536-design-scalable-sync-workflows-with-data-tables-prospectpro-and-hubspot/) | ⭐⭐ | Telegram | Use with OpenClaw | official |
| [cad2data Revit IFC DWG DGN](https://github.com/datadrivenconstruction/cad2data-Revit-IFC-DWG-DGN) | ⭐⭐ | — | Use with OpenClaw | community |
| [ai automation jsons](https://github.com/simealdana/ai-automation-jsons) | ⭐⭐ | — | Use with OpenClaw | community |
| [n8n intelligence](https://github.com/Yukaii/n8n-intelligence) | ⭐⭐ | — | Use with OpenClaw | community |
| [n8n cyber intel](https://github.com/Ilesnat/n8n_cyber_intel) | ⭐⭐ | — | Use with OpenClaw | community |
| [srt llm translator](https://github.com/alejandrosnz/srt-llm-translator) | ⭐⭐ | — | Use with OpenClaw | community |
| [I know there are 100 receipt parsers, but I built one that actually runs for $0 … ⚠️](https://reddit.com/r/n8n/comments/1pg8fsj/i_know_there_are_100_receipt_parsers_but_i_built/) | ⭐⭐ | Telegram | Use with OpenClaw | community |
| [After learning this, my AI workflows now cost me 30x less](https://reddit.com/r/n8n/comments/1oplxlb/after_learning_this_my_ai_workflows_now_cost_me/) | ⭐⭐ | — | Use with OpenClaw | community |
| [I built this in 2 hours - something Adobe still can’t do after 4+ years.](https://reddit.com/r/n8n/comments/1o5iuj2/i_built_this_in_2_hours_something_adobe_still/) | ⭐⭐ | Openai | Video automation | community |
| [Your n8n Learning Journey Just Got Easier - I Built a Complete YouTube Video Dir…](https://reddit.com/r/n8n/comments/1jm0vfb/your_n8n_learning_journey_just_got_easier_i_built/) | ⭐⭐ | — | Video automation | community |
| [This n8n workflow scrapes any business URL and writes a full analysis report for…](https://reddit.com/r/n8n/comments/1oksstl/this_n8n_workflow_scrapes_any_business_url_and/) | ⭐⭐ | — | Use with OpenClaw | community |
| [😎 Actually making $200/month by selling this workflow as a service. Saving hours… ⚠️](https://reddit.com/r/n8n/comments/1jku65u/actually_making_200month_by_selling_this_workflow/) | ⭐⭐ | — | Use with OpenClaw | community |
| [This workflow generates pencil sketch](https://reddit.com/r/n8n/comments/1rgdw9p/this_workflow_generates_pencil_sketch/) | ⭐⭐ | — | Use with OpenClaw | community |
| [Built an OCR automation pipeline using Sarvam Vision + n8n (messy scans → struct…](https://reddit.com/r/n8n/comments/1rf1sf0/built_an_ocr_automation_pipeline_using_sarvam/) | ⭐⭐ | — | Use with OpenClaw | community |
| [HTML🧑‍🎓 Test Your Data Access Techniques with Progressive Expression ChallengesH…](https://n8n.io/workflows/6236-test-your-data-access-techniques-with-progressive-expression-challenges/) | ⭐⭐ | — | Use with OpenClaw | official |
| [news pipeline n8n](https://github.com/jeremylongshore/news-pipeline-n8n) | ⭐⭐ | — | Use with OpenClaw | community |
| [Lead Scraping Automation No Code AI ](https://github.com/Sonwa127/Lead-Scraping-Automation-No-Code-AI-) | ⭐⭐ | Gmail, Google Sheets | Use with OpenClaw | community |
| [n8n workflow](https://github.com/samirsaci/n8n_workflow) | ⭐⭐ | — | Use with OpenClaw | community |
| [automatic course certificate generation](https://reddit.com/r/n8n/comments/1qumkw9/automatic_course_certificate_generation/) | ⭐⭐ | Google Sheets | Use with OpenClaw | community |
| [HELP I WANT TO SEND IT TO CLIENT TOMORROW!](https://reddit.com/r/n8n/comments/1r5do5l/help_i_want_to_send_it_to_client_tomorrow/) | ⭐⭐ | — | Use with OpenClaw | community |
| [NEW DAY NEW ERROR😅](https://reddit.com/r/n8n/comments/1r88gzd/new_day_new_error/) | ⭐⭐ | — | Use with OpenClaw | community |
| [This is my workflow. Despite having 74 news items, only one news story keeps rep…](https://community.n8n.io/t/this-is-my-workflow-despite-having-74-news-items-only-one-news-story-keeps-repeating-if-there-are-74-news-stories-they-should-all-appear-differently-but-the-same-one-keeps-recurring-additionally-hinglish-news-appears-in-between-whereas-i-need-the/268441) | ⭐⭐ | — | Use with OpenClaw | community |
| [Conversation Initiation Client Data Webhook n8n example](https://community.n8n.io/t/conversation-initiation-client-data-webhook-n8n-example/269321) | ⭐⭐ | — | Use with OpenClaw | community |
| [How to read all sheets from an Excel file (.xls/.xlsx) and split them into separ…](https://community.n8n.io/t/how-to-read-all-sheets-from-an-excel-file-xls-xlsx-and-split-them-into-separate-files-in-n8n/186816) | ⭐⭐ | — | Use with OpenClaw | community |
| [Convert JSON to an Excel file](https://n8n.io/workflows/1435-convert-json-to-an-excel-file/) | ⭐ | — | Use with OpenClaw | official |

## 👥 HR & Recruitment


| Workflow | Difficulty | 🛠 Services | 🤖 OpenClaw | Source |
|----------|-----------|------------|------------|--------|
| [Google SheetsHTTP RequestWhatsApp Business Cloud+10Automated HR Service System w… ⚠️](https://n8n.io/workflows/4975-automated-hr-service-system-with-whatsapp-gpt-4-classification-and-google-workspace/) | ⭐⭐⭐ | Whatsapp, Google Sheets | Use with OpenClaw | official |
| [Google SheetsGoogle DriveSummarization Chain+4Resume Screening & Evaluation Syst…](https://n8n.io/workflows/5453-resume-screening-and-evaluation-system-with-gemini-ai-google-sheets-and-drive-for-hr/) | ⭐⭐⭐ | Google Sheets | Use with OpenClaw | official |
| [Google CalendarGmailCode+3Interview Scheduling Automation with Google Sheets, Ca… ⚠️](https://n8n.io/workflows/5001-interview-scheduling-automation-with-google-sheets-calendar-gmail-and-gpt-4o/) | ⭐⭐⭐ | Gmail, Google Sheets | Use with OpenClaw | official |
| [Google SheetsGmailCode+1Generate and Email PDF Payslips from Google Sheets with … ⚠️](https://n8n.io/workflows/10650-generate-and-email-pdf-payslips-from-google-sheets-with-gmail/) | ⭐⭐⭐ | Gmail, Google Sheets | Use with OpenClaw | official |
| [Google SheetsHTTP RequestTelegram+5AI Candidate Screening Pipeline: LinkedIn to … ⚠️](https://n8n.io/workflows/10045-ai-candidate-screening-pipeline-linkedin-to-telegram-with-gemini-and-apify/) | ⭐⭐⭐ | Telegram, Google Sheets | Use with OpenClaw | official |
| [Google DriveGmailGoogle DocsAutomated New Hire Appointment Letters with Google D… ⚠️](https://n8n.io/workflows/5879-automated-new-hire-appointment-letters-with-google-docs-hr-approval-and-gmail/) | ⭐⭐⭐ | Gmail | Use with OpenClaw | official |
| [Google SheetsGoogle DriveSummarization Chain+4AI Automated HR Workflow for CV An…](https://n8n.io/workflows/2860-ai-automated-hr-workflow-for-cv-analysis-and-candidate-evaluation/) | ⭐⭐⭐ | Google Sheets | Use with OpenClaw | official |
| [This automation scrapes LinkedIn jobs, customizes my resume for each of them and…](https://reddit.com/r/n8n/comments/1qsz9qj/this_automation_scrapes_linkedin_jobs_customizes/) | ⭐⭐⭐ | — | Jobs / recruiting | community |
| [I built a fully automated job application pipeline in n8n — daily scheduling, AI…](https://reddit.com/r/n8n/comments/1r95t1k/i_built_a_fully_automated_job_application/) | ⭐⭐⭐ | — | Jobs / recruiting | community |
| [How 8 n8n workflows replaced our entire staff scheduling system](https://reddit.com/r/n8n/comments/1rb4rbs/how_8_n8n_workflows_replaced_our_entire_staff/) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [Google SheetsBasic LLM ChainStructured Output Parser+2🤖 Automate CV Screening wi…](https://n8n.io/workflows/7456-automate-cv-screening-with-ai-candidate-analysis/) | ⭐⭐ | Google Sheets | Use with OpenClaw | official |
| [TelegramCodeAutomate Job Application Processing from Forms to Telegram for HR Te… ⚠️](https://n8n.io/workflows/5713-automate-job-application-processing-from-forms-to-telegram-for-hr-teams/) | ⭐⭐ | Telegram | Jobs / recruiting | official |

## 🛒 E-commerce & Sales


| Workflow | Difficulty | 🛠 Services | 🤖 OpenClaw | Source |
|----------|-----------|------------|------------|--------|
| [I built an AI automation that converts static product images into animated demo …](https://reddit.com/r/n8n/comments/1odi3hf/i_built_an_ai_automation_that_converts_static/) | ⭐⭐⭐ | — | Video automation | community |
| [I recreated a dentist voice agent making $24K/yr using ElevenLabs. Handles after… ⚠️](https://reddit.com/r/n8n/comments/1m37l5z/i_recreated_a_dentist_voice_agent_making_24kyr/) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [I built a UGC video ad generator that analyzes any product image, generates an i…](https://reddit.com/r/n8n/comments/1o39gpf/i_built_a_ugc_video_ad_generator_that_analyzes/) | ⭐⭐⭐ | Openai | Video automation | community |
| [Built a WhatsApp AI Bot for Nail Salons ⚠️](https://reddit.com/r/n8n/comments/1l8v8jy/built_a_whatsapp_ai_bot_for_nail_salons/) | ⭐⭐⭐ | Whatsapp, Redis | Use with OpenClaw | community |
| [I built an AI automation that generates unlimited consistent character UGC ads f…](https://reddit.com/r/n8n/comments/1or1gwi/i_built_an_ai_automation_that_generates_unlimited/) | ⭐⭐⭐ | — | Video automation | community |
| [I swear I didn’t mean to automate the hardest part of our content workflow… but …](https://reddit.com/r/n8n/comments/1p7bytg/i_swear_i_didnt_mean_to_automate_the_hardest_part/) | ⭐⭐⭐ | — | Video automation | community |
| [n8n whatsapp automation ⚠️](https://github.com/mubashir-786/n8n-whatsapp-automation) | ⭐⭐⭐ | Whatsapp | Use with OpenClaw | community |

## 💰 Finance & Trading


| Workflow | Difficulty | 🛠 Services | 🤖 OpenClaw | Source |
|----------|-----------|------------|------------|--------|
| [Built an AI-Powered Personal Finance Tracker in n8n (Telegram + LLM + MongoDB)](https://reddit.com/r/n8n/comments/1r4eycg/built_an_aipowered_personal_finance_tracker_in/) | ⭐⭐⭐ | Telegram | Use with OpenClaw | community |

## 🔧 DevOps & Engineering


| Workflow | Difficulty | 🛠 Services | 🤖 OpenClaw | Source |
|----------|-----------|------------|------------|--------|
| [nanobrowser](https://github.com/nanobrowser/nanobrowser) | ⭐⭐⭐ | Openai | Use with OpenClaw | community |
| [bytechef](https://github.com/bytechefhq/bytechef) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [openclaw n8n stack](https://github.com/caprihan/openclaw-n8n-stack) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [n8n skills](https://github.com/czlonkowski/n8n-skills) | ⭐⭐⭐ | Claude | Use with OpenClaw | community |
| [n8n claude code guide](https://github.com/theNetworkChuck/n8n-claude-code-guide) | ⭐⭐⭐ | Claude | Use with OpenClaw | community |
| [antigravity n8n skills](https://github.com/WilkoMarketing/antigravity-n8n-skills) | ⭐⭐⭐ | Claude | Use with OpenClaw | community |
| [I Crushed My AI Video Costs to $0. Here is the Fully Self-Hosted "YouTube Factor…](https://reddit.com/r/n8n/comments/1ptqtbp/i_crushed_my_ai_video_costs_to_0_here_is_the/) | ⭐⭐⭐ | — | Video automation | community |
| [self hosted video starter kit](https://github.com/jaypetersdotdev/self-hosted-video-starter-kit) | ⭐⭐⭐ | — | Video automation | community |
| [n8n CyberSecurity Workflows ⚠️](https://github.com/mahaishu/n8n-CyberSecurity-Workflows) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [What I’ve learned scaling n8n from a $6 droplet to 400k+ executions/month](https://reddit.com/r/n8n/comments/1kfmifs/what_ive_learned_scaling_n8n_from_a_6_droplet_to/) | ⭐⭐⭐ | Redis | Use with OpenClaw | community |
| [I got tired of managing my n8n workflows from mobile… so I built this.](https://reddit.com/r/n8n/comments/1r8e7m4/i_got_tired_of_managing_my_n8n_workflows_from/) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [Controlling mobile devices (real and virtual) from n8n workflow. Self-healing mo…](https://reddit.com/r/n8n/comments/1r7d7gt/controlling_mobile_devices_real_and_virtual_from/) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [I've transformed the way I manage my agents for Software Dev using a local N8N+K…](https://reddit.com/r/n8n/comments/1rdvfr5/ive_transformed_the_way_i_manage_my_agents_for/) | ⭐⭐⭐ | Claude, Github | Use with OpenClaw | community |
| [Did you know you can scale n8n by running separate n8n processes?](https://reddit.com/r/n8n/comments/1r07dkw/did_you_know_you_can_scale_n8n_by_running/) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [N8n-claw: OpenClaw in n8n](https://community.n8n.io/t/n8n-claw-openclaw-in-n8n/271756) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [N8n + Grafana Full Node.js Metrics Dashboard (JSON Example Included!)](https://community.n8n.io/t/n8n-grafana-full-node-js-metrics-dashboard-json-example-included/115366) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [Back Up Your n8n Workflows To Github](https://n8n.io/workflows/1534-back-up-your-n8n-workflows-to-github/) | ⭐⭐ | Github | Use with OpenClaw | official |
| [SupabaseLearn Secure Webhook APIs with Authentication and Supabase IntegrationTh…](https://n8n.io/workflows/8258-learn-secure-webhook-apis-with-authentication-and-supabase-integration/) | ⭐⭐ | Supabase | Use with OpenClaw | official |
| [build ai agents and automate workflows with n8n 5437042](https://github.com/LinkedInLearning/build-ai-agents-and-automate-workflows-with-n8n-5437042) | ⭐⭐ | — | Use with OpenClaw | community |
| [FlowMetr](https://github.com/FlowMetr/FlowMetr) | ⭐⭐ | — | Use with OpenClaw | community |
| [n8n Workflow Builder Ai](https://github.com/farhansrambiyan/n8n-Workflow-Builder-Ai) | ⭐⭐ | Openai | Use with OpenClaw | community |
| [n8n nodes openai langfuse](https://github.com/rorubyy/n8n-nodes-openai-langfuse) | ⭐⭐ | Openai | Use with OpenClaw | community |
| [n8n skills](https://github.com/haunchen/n8n-skills) | ⭐⭐ | — | Use with OpenClaw | community |
| [awesome claude plugins](https://github.com/quemsah/awesome-claude-plugins) | ⭐⭐ | Claude, Github | Use with OpenClaw | community |
| [claude workflow generator](https://github.com/Kookylo/claude_workflow_generator) | ⭐⭐ | Claude | Use with OpenClaw | community |
| [20+ Useful, Focused Tools That Work Seamlessly with n8n](https://reddit.com/r/n8n/comments/1kp05jl/20_useful_focused_tools_that_work_seamlessly_with/) | ⭐⭐ | Notion | Use with OpenClaw | community |
| [I THINK I JUST CRACKED IT!! An n8n Workflow generator! ⚠️](https://reddit.com/r/n8n/comments/1kthlcf/i_think_i_just_cracked_it_an_n8n_workflow/) | ⭐⭐ | Slack | Use with OpenClaw | community |
| [Creating an API endpoint](https://n8n.io/workflows/1750-creating-an-api-endpoint/) | ⭐⭐ | — | Use with OpenClaw | official |
| [I built a free tool to analyze and audit n8n workflows - would love your feedbac…](https://reddit.com/r/n8n/comments/1qvpan3/i_built_a_free_tool_to_analyze_and_audit_n8n/) | ⭐⭐ | — | Use with OpenClaw | community |
| [Determine version of currently running n8n (introspection)](https://community.n8n.io/t/determine-version-of-currently-running-n8n-introspection/138096) | ⭐⭐ | — | Use with OpenClaw | community |
| [Very quick quickstart](https://n8n.io/workflows/1700-very-quick-quickstart/) | ⭐ | — | Use with OpenClaw | official |
| [n8nworkflows.xyz: All n8n Workflows Now Available on GitHub](https://reddit.com/r/n8n/comments/1owt1z5/n8nworkflowsxyz_all_n8n_workflows_now_available/) | ⭐ | Github | Use with OpenClaw | community |
| [A simple file upload workflow](https://community.n8n.io/t/a-simple-file-upload-workflow/93189) | ⭐ | — | Use with OpenClaw | community |

## 🎧 Customer Support


| Workflow | Difficulty | 🛠 Services | 🤖 OpenClaw | Source |
|----------|-----------|------------|------------|--------|
| [customer support ai agent](https://github.com/Muneeb20019/customer-support-ai-agent) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [n8n advanced telegram support ticket management workflow ⚠️](https://github.com/Automations-Project/n8n-advanced-telegram-support-ticket-management-workflow) | ⭐⭐⭐ | Telegram | Use with OpenClaw | community |
| [Automating Labor Law Client Intake via WhatsApp with AI and Automation Tools](https://community.n8n.io/t/automating-labor-law-client-intake-via-whatsapp-with-ai-and-automation-tools/108750) | ⭐⭐⭐ | Whatsapp | Use with OpenClaw | community |
| [Built a Chatbot Inbox for n8n - Am I the Only One with This Problem?](https://community.n8n.io/t/built-a-chatbot-inbox-for-n8n-am-i-the-only-one-with-this-problem/223234) | ⭐⭐⭐ | — | Use with OpenClaw | community |
| [someone tried selling me an ai automation for $6,000 and i ended up building it …](https://reddit.com/r/n8n/comments/1qx08uu/someone_tried_selling_me_an_ai_automation_for/) | ⭐⭐ | — | Use with OpenClaw | community |
| [How I helped a local massage studio reclaim 6 hours a week with a simple AI appo…](https://reddit.com/r/n8n/comments/1ri5ts8/how_i_helped_a_local_massage_studio_reclaim_6/) | ⭐⭐ | — | Use with OpenClaw | community |
| [How to create a webhook triggered workflow with Wait on Form Submit and Respond …](https://community.n8n.io/t/how-to-create-a-webhook-triggered-workflow-with-wait-on-form-submit-and-respond-to-webhook/192098) | ⭐⭐ | — | Use with OpenClaw | community |

## Contributing

Contributions welcome! Please read CONTRIBUTING.md first.

## Data Sources

n8n official template library · GitHub · Reddit r/n8n · n8n Community Forum

Last updated: 2026-03-02

## License

MIT
