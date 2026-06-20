# n8n Automation Portfolio

**30 production-grade n8n automation workflows** — AI agents, RAG pipelines, and multi-step automations spanning IoT, AWS cloud, e-commerce, video production, research, and business operations.

Built and maintained by **[Tahir Riaz Malik](https://github.com/triaz-malik)** · [trmtelcocloudai.com](https://trmtelcocloudai.com)

---

Most workflows are fully agentic — LLM reasoning + vector-store retrieval + conversation memory — wired to real production integrations. Every project folder contains:

- **`workflow.json`** — import directly into n8n via Workflows → Import from File
- **`PDF case study`** — architecture diagram, step-by-step breakdown, sample input/output, and credentials guide

> API keys and credentials are stripped from all exported JSON files. Reconnect your own before running.

**Models used:** OpenAI GPT-4 · Anthropic Claude · Google Gemini · Mistral · Cohere · HuggingFace  
**Vector stores:** Pinecone · Qdrant · Supabase pgvector · Weaviate · Redis

---

## 📡 IoT & Industrial Monitoring

### 01. Predictive Maintenance Alert System
Ingests equipment sensor telemetry via webhook, semantically matches it against a historical failure signature library (RAG), and predicts failure windows with confidence scores before breakdown occurs. Fires alerts to Slack and logs to Google Sheets.

**Stack:** OpenAI · Weaviate vector store · Window buffer memory · Google Sheets  
📄 [Case study PDF](01_iot_predictive_maintenance/) · ⚙️ [workflow.json](01_iot_predictive_maintenance/workflow.json)

---

### 02. Sensor Fault Detector
Detects faulty sensor readings in real time — stuck values, dead sensors, calibration drift — by comparing incoming readings against known-good patterns in a Supabase vector store. Dispatches work orders automatically.

**Stack:** HuggingFace LLM · Supabase vector store · Google Sheets  
📄 [Case study PDF](02_iot_sensor_fault_detector/) · ⚙️ [workflow.json](02_iot_sensor_fault_detector/workflow.json)

---

### 03. Smart Home Energy Saver Agent
Analyses smart plug consumption data, identifies waste patterns such as AC running with no occupancy, sends control commands to Home Assistant via HTTP, and delivers weekly savings reports.

**Stack:** Cohere embeddings · Supabase vector store · Home Assistant · Google Sheets  
📄 [Case study PDF](03_iot_smart_energy_agent/) · ⚙️ [workflow.json](03_iot_smart_energy_agent/workflow.json)

---

### 13. Machine Downtime Predictor
A Claude-powered agent that ingests SCADA telemetry every 15 minutes, matches readings against a Weaviate library of historical failure signatures, and predicts downtime windows hours in advance so production can plan around them.

**Stack:** Anthropic Claude · OpenAI embeddings · Weaviate · Google Sheets  
📄 [Case study PDF](13_ml_machine_downtime/) · ⚙️ [workflow.json](13_ml_machine_downtime/workflow.json)

---

### 14. Quality Defect Classifier
Processes production line camera images in real time, classifies defect type and severity against a Redis-cached defect knowledge base, routes rejections instantly, and tracks defect rates by shift.

**Stack:** Anthropic Claude · OpenAI embeddings · Redis vector store · Google Sheets  
📄 [Case study PDF](14_ml_quality_defect_classifier/) · ⚙️ [workflow.json](14_ml_quality_defect_classifier/workflow.json)

---

### 27. Solar Output Forecaster
Fetches next-day weather forecasts, matches the weather profile against similar historical generation days using vector search, and delivers a 24-hour hourly kWh forecast with confidence bounds for automated grid scheduling.

**Stack:** Anthropic Claude · HuggingFace embeddings · Supabase · Google Sheets  
📄 [Case study PDF](27_energy_solar_forecaster/) · ⚙️ [workflow.json](27_energy_solar_forecaster/workflow.json)

---

## ☁️ AWS Cloud Pipelines

### 04. AWS Rekognition Image Intelligence Pipeline
Sends images through AWS Rekognition for object, label, and text detection at scale. Applies business logic routing by label type and logs confidence-scored results to Google Sheets.

**Stack:** AWS Rekognition · HTTP Request · Set · Function · Google Sheets  
📄 [Case study PDF](04_aws_rekognition_pipeline/) · ⚙️ [workflow.json](04_aws_rekognition_pipeline/workflow.json)

---

### 05. AWS Textract Document Extraction Agent
Accepts invoice photos sent to a Telegram bot, uploads them to S3, runs AWS Textract to extract all key-value pairs (vendor, amount, date, PO number), and stores structured records in Airtable — zero manual data entry.

**Stack:** AWS Textract · AWS S3 · Telegram · Airtable  
📄 [Case study PDF](05_aws_textract_doc_agent/) · ⚙️ [workflow.json](05_aws_textract_doc_agent/workflow.json)

---

### 06. AWS S3 ↔ Google Drive Sync
Watches Google Drive for new or modified files and mirrors them to the correct AWS S3 bucket path automatically, routing by folder and file type.

**Stack:** Google Drive Trigger · AWS S3 · Merge  
📄 [Case study PDF](06_aws_s3_drive_sync/) · ⚙️ [workflow.json](06_aws_s3_drive_sync/workflow.json)

---

## 📚 RAG & Document Intelligence

### 07. Financial Documents RAG Assistant
Watches a folder for new financial PDFs, auto-ingests them into Qdrant with Mistral embeddings, and enables natural language Q&A with exact page citations. Answers in seconds rather than hours of manual reading.

**Stack:** Mistral Cloud embeddings · Qdrant · Retrieval-QA chain  
📄 [Case study PDF](07_rag_financial_documents/) · ⚙️ [workflow.json](07_rag_financial_documents/workflow.json)

---

### 08. Company Knowledge RAG Chatbot
Auto-indexes Google Drive into Pinecone on file create or update, then answers employee questions with exact document and page citations. Re-indexes automatically when files change.

**Stack:** Google Gemini embeddings · Pinecone · Google Drive · Window buffer memory  
📄 [Case study PDF](08_rag_company_knowledge_bot/) · ⚙️ [workflow.json](08_rag_company_knowledge_bot/workflow.json)

---

### 09. Stock Earnings Report Analysis
Batch-ingests quarterly earnings PDFs into Pinecone, enables cross-company Q&A using Gemini and GPT-4, and auto-saves full research reports to Google Docs.

**Stack:** Google Gemini · OpenAI GPT-4 · Pinecone · Google Docs  
📄 [Case study PDF](09_rag_stock_earnings/) · ⚙️ [workflow.json](09_rag_stock_earnings/workflow.json)

---

### 20. Customer Insights Engine
Scrapes reviews and support tickets, embeds and clusters them in Qdrant, and produces a weekly insight report with themes, sentiment scores, and representative quotes — from thousands of comments to a one-page summary.

**Stack:** OpenAI · Qdrant · k-means clustering · Google Sheets  
📄 [Case study PDF](20_ml_customer_insights/) · ⚙️ [workflow.json](20_ml_customer_insights/workflow.json)

---

### 22. AI Fundamental Stock Analysis Crew
Ingests financial filings into Qdrant and answers natural language questions with exact page citations. Full fundamental analysis — revenue, margins, guidance, risks — in minutes rather than hours.

**Stack:** OpenAI GPT-4 · Qdrant · Retrieval-QA chain · Google Drive  
📄 [Case study PDF](22_finance_stock_analysis_crew/) · ⚙️ [workflow.json](22_finance_stock_analysis_crew/workflow.json)

---

## 🛒 E-Commerce & Retail

### 10. Abandoned Cart Recovery Email Automation
Fires 1 hour after cart abandonment, retrieves customer purchase history from Supabase to write a genuinely personalised recovery email, and applies intelligent discount logic based on abandonment history.

**Stack:** Cohere embeddings · Supabase · OpenAI · Slack  
📄 [Case study PDF](10_ecommerce_abandoned_cart/) · ⚙️ [workflow.json](10_ecommerce_abandoned_cart/workflow.json)

---

### 11. AI-Powered WooCommerce Support Agent
A 31-node conversational support agent that fetches live WooCommerce order data and real DHL tracking, resolves order queries autonomously, and only escalates genuinely complex cases.

**Stack:** OpenAI · WooCommerce REST API · DHL Tracking API · Sub-workflow tools  
📄 [Case study PDF](11_ecommerce_woo_support_agent/) · ⚙️ [workflow.json](11_ecommerce_woo_support_agent/workflow.json)

---

### 12. Inventory Slack Alert System
Monitors every SKU continuously, computes days-to-stockout from real sales velocity, and fires tiered Slack alerts with supplier contacts and recommended reorder quantities — catching problems 2 weeks before a stock-out.

**Stack:** Cohere embeddings · Pinecone · OpenAI · Slack · Google Sheets  
📄 [Case study PDF](12_ecommerce_inventory_alerts/) · ⚙️ [workflow.json](12_ecommerce_inventory_alerts/workflow.json)

---

### 26. Competitor Price Scraper and Alert
Scrapes competitor pricing pages daily at 06:00, detects changes using vector semantic diff rather than brittle HTML selectors, and delivers a structured change brief — including a strategic read — via Slack within minutes.

**Stack:** Anthropic Claude · OpenAI embeddings · Supabase · Slack  
📄 [Case study PDF](26_data_competitor_price_monitor/) · ⚙️ [workflow.json](26_data_competitor_price_monitor/workflow.json)

---

## 🎬 Video & Content Creation

### 15. Hacker News to Video Content Pipeline
Monitors Hacker News for trending stories, writes a 75-second script with GPT-4, generates scene images with Leonardo AI, animates them with Runway Gen-2, and uploads the finished video to S3 — fully automated daily.

**Stack:** OpenAI · Leonardo AI · Runway ML · AWS S3 · Hacker News API  
📄 [Case study PDF](15_video_hn_to_video/) · ⚙️ [workflow.json](15_video_hn_to_video/workflow.json)

---

### 16. Multimodal Video Narration Agent
Downloads any video, extracts frames at 1fps, sends batches to GPT-4 Vision, and assembles a chronological timestamped narration script — turning silent footage into ready-to-record narration in minutes.

**Stack:** OpenAI GPT-4 Vision · ffmpeg · Google Drive  
📄 [Case study PDF](16_video_multimodal_narrator/) · ⚙️ [workflow.json](16_video_multimodal_narrator/workflow.json)

---

### 17. YouTube Comment Insight Extractor
Ingests up to 10,000 YouTube comments, clusters them by theme using vector embeddings, runs sentiment analysis, and produces a structured insight report with representative quotes per theme.

**Stack:** OpenAI · Pinecone · Slack · Google Sheets  
📄 [Case study PDF](17_video_youtube_insights/) · ⚙️ [workflow.json](17_video_youtube_insights/workflow.json)

---

### 23. Social Media Content Amplifier
Monitors Hacker News on a schedule, repurposes top stories into LinkedIn posts and tweets using GPT-4, deduplicates against Airtable history, and publishes automatically — zero human involvement required.

**Stack:** OpenAI · LinkedIn API · Twitter/X API · Airtable  
📄 [Case study PDF](23_content_social_amplifier/) · ⚙️ [workflow.json](23_content_social_amplifier/workflow.json)

---

### 24. Brand-Consistent 9:16 AI Image Generator
Reads brand guidelines and SEO keywords from Airtable, generates optimised DALL-E 3 prompts enforcing brand colours and no-text rules, and delivers 5 ready-to-post 9:16 portrait image variants.

**Stack:** OpenAI DALL-E 3 · Airtable · Google Drive  
📄 [Case study PDF](24_content_brand_image_generator/) · ⚙️ [workflow.json](24_content_brand_image_generator/workflow.json)

---

## 🔬 Research & Data Intelligence

### 18. AI Deep Research Agent
A 132-node autonomous research agent: decomposes a research question into sub-queries, crawls multiple web sources, synthesises findings using OpenAI and Gemini, and writes a sourced report to Notion — fully orchestrated via sub-workflows.

**Stack:** OpenAI · Google Gemini · Web crawling · Notion · Sub-workflows  
📄 [Case study PDF](18_research_deep_agent/) · ⚙️ [workflow.json](18_research_deep_agent/workflow.json)

---

### 19. Vector DB Anomaly Detector
Uses Qdrant vector clustering with Scipy DBSCAN to find genuine anomalies in logs, metrics, and transactions — detecting novel failure patterns that no threshold-based rule would catch. Near-zero false positive rate.

**Stack:** Qdrant · Scipy · HTTP · Custom code  
📄 [Case study PDF](19_data_vector_anomaly_detection/) · ⚙️ [workflow.json](19_data_vector_anomaly_detection/workflow.json)

---

### 25. Autonomous AI Web Crawler
A self-directing agent that visits company homepages, extracts all external links using sub-workflow tools, identifies social platform profiles, and builds complete digital footprint records in Supabase — processes 100 companies overnight.

**Stack:** OpenAI · Supabase · Sub-workflow tools (Text scraper + URL scraper)  
📄 [Case study PDF](25_research_autonomous_crawler/) · ⚙️ [workflow.json](25_research_autonomous_crawler/workflow.json)

---

## 🏢 Business Operations

### 21. AI HR Recruitment and Candidate Evaluation
Handles end-to-end recruitment: form intake, CV upload to Drive, PDF text extraction, AI scoring against a role requirements matrix, shortlist/reject routing, personalised email outreach, and interview scheduling via Google Calendar — all tracked in Airtable.

**Stack:** OpenAI · Airtable · Google Drive · Google Calendar · Structured output parser  
📄 [Case study PDF](21_hr_ai_recruitment/) · ⚙️ [workflow.json](21_hr_ai_recruitment/workflow.json)

---

### 28. NDA Risk Detector
Parses any NDA at clause level, scores each clause Red/Amber/Green against a company playbook stored in Redis, suggests specific redline language for flagged clauses, and delivers a one-page risk brief in under 2 minutes.

**Stack:** OpenAI GPT-4 · HuggingFace embeddings · Redis vector store · Google Sheets  
📄 [Case study PDF](28_legal_nda_risk_detector/) · ⚙️ [workflow.json](28_legal_nda_risk_detector/workflow.json)

---

### 29. Healthcare Appointment Notification Agent
Sends personalised WhatsApp appointment reminders 24h and 2h before appointments, handles patient replies (Confirm / Cancel / Reschedule) autonomously, and updates the HMS in real time. Slack alert fires if no response by T-4h.

**Stack:** OpenAI · Supabase · WhatsApp Business API · Slack  
📄 [Case study PDF](29_healthcare_whatsapp_agent/) · ⚙️ [workflow.json](29_healthcare_whatsapp_agent/workflow.json)

---

### 30. Podcast Transcription and Auto-Publishing
Processes raw audio with Whisper, generates show notes, an SEO blog post, a LinkedIn post, a Twitter thread, and timestamped chapter markers using Claude — then publishes to WordPress, updates RSS, and notifies the team via Slack. Full episode post-production in 15 minutes.

**Stack:** Anthropic Claude · OpenAI Whisper · Cohere · Pinecone · WordPress · Slack  
📄 [Case study PDF](30_media_podcast_production/) · ⚙️ [workflow.json](30_media_podcast_production/workflow.json)

---

## How to use

1. Open n8n → **Workflows** → **Import from File** → select any `workflow.json`
2. Reconnect credentials for the services that workflow uses
3. Update Google Sheet / Drive / Airtable IDs and webhook URLs to match your environment
4. Each PDF case study documents the exact input format, output format, and credential setup

---

## Author

**Tahir Riaz Malik**  
AWS ML Specialty · AWS SAP-C02 · Azure DP-100 · PMP · PMI-ACP  
[github.com/triaz-malik](https://github.com/triaz-malik) · [trmtelcocloudai.com](https://trmtelcocloudai.com)
