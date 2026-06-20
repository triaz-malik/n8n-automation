# n8n Automation Portfolio

**30 production-grade [n8n](https://n8n.io) automation workflows** — AI agents, RAG systems, and multi-step pipelines spanning IoT, AWS, e-commerce, video, research, and business operations.

Most workflows are **agentic** (LLM + vector-store retrieval + memory) and built around real integrations. Each project folder ships with:
- **`workflow.json`** — import directly into n8n (Workflows → Import from File)
- **A PDF case study** — what it does, the architecture, and the value

> 🔑 API keys/credentials are stripped from the exported JSON — connect your own to run.

**Models used across the set:** OpenAI, Anthropic Claude, Google Gemini, Mistral, Cohere, HuggingFace · **Vector stores:** Pinecone, Qdrant, Supabase, Weaviate, Redis

---

## 📡 IoT & Industrial Monitoring

### 01. Predictive Maintenance Alert
An AI agent that ingests equipment telemetry via webhook and predicts likely failures before they happen, grounding its reasoning in historical maintenance records (RAG) and logging alerts to Google Sheets.

**Stack:** OpenAI, Weaviate vector store, conversational memory, Google Sheets  
[📄 Case study (PDF)](01_iot_predictive_maintenance/01_iot_predictive_maintenance_PRO.pdf)  &nbsp;·&nbsp;  [⚙️ workflow.json](01_iot_predictive_maintenance/workflow.json)

### 02. Sensor Fault Detector
Flags anomalous or faulty sensor readings in real time using a retrieval-augmented AI agent that compares incoming values against known-good patterns, then records flagged events.

**Stack:** HuggingFace LLM, Supabase vector store, Google Sheets  
[📄 Case study (PDF)](02_iot_sensor_fault_detector/02_iot_sensor_fault_detector.pdf)  &nbsp;·&nbsp;  [⚙️ workflow.json](02_iot_sensor_fault_detector/workflow.json)

### 03. Smart Home Energy Saver
An agent that analyses energy-usage data and recommends savings actions, using a Cohere-embedded knowledge base of efficiency strategies.

**Stack:** Cohere embeddings, Supabase vector store, Google Sheets  
[📄 Case study (PDF)](03_iot_smart_energy_agent/03_iot_smart_energy_agent.pdf)  &nbsp;·&nbsp;  [⚙️ workflow.json](03_iot_smart_energy_agent/workflow.json)

### 13. Machine Downtime Predictor
A Claude-powered agent that predicts machine downtime risk from operational data, grounded in historical incident records.

**Stack:** Anthropic Claude, Weaviate, Google Sheets  
[📄 Case study (PDF)](13_ml_machine_downtime/13_ml_machine_downtime.pdf)  &nbsp;·&nbsp;  [⚙️ workflow.json](13_ml_machine_downtime/workflow.json)

### 14. Quality Defect Classifier
Classifies manufacturing defects from inspection inputs using a Claude RAG agent backed by a Redis vector store.

**Stack:** Anthropic Claude, Redis vector store, Google Sheets  
[📄 Case study (PDF)](14_ml_quality_defect_classifier/14_ml_quality_defect_classifier.pdf)  &nbsp;·&nbsp;  [⚙️ workflow.json](14_ml_quality_defect_classifier/workflow.json)

### 27. Solar Output Forecaster
Forecasts solar energy output from input conditions using a Claude RAG agent, logging predictions to Google Sheets.

**Stack:** Anthropic Claude, HuggingFace embeddings, Google Sheets  
[📄 Case study (PDF)](27_energy_solar_forecaster/27_energy_solar_forecaster.pdf)  &nbsp;·&nbsp;  [⚙️ workflow.json](27_energy_solar_forecaster/workflow.json)

---

## ☁️ AWS Cloud Pipelines

### 04. AWS Rekognition Image Pipeline
Runs images through AWS Rekognition for object/label detection, enriches the results, and catalogs them to Google Sheets — useful for moderation or asset tagging.

**Stack:** AWS Rekognition, HTTP, Google Sheets  
[📄 Case study (PDF)](04_aws_rekognition_pipeline/04_aws_rekognition_pipeline.pdf)  &nbsp;·&nbsp;  [⚙️ workflow.json](04_aws_rekognition_pipeline/workflow.json)

### 05. AWS Textract Document Agent
Documents submitted via Telegram are OCR-processed with AWS Textract, then the extracted structured data is stored in Airtable and archived to S3.

**Stack:** AWS Textract, AWS S3, Telegram, Airtable  
[📄 Case study (PDF)](05_aws_textract_doc_agent/05_aws_textract_doc_agent.pdf)  &nbsp;·&nbsp;  [⚙️ workflow.json](05_aws_textract_doc_agent/workflow.json)

### 06. AWS S3 ⇄ Google Drive Sync
Watches Google Drive for new files and mirrors them to an AWS S3 bucket automatically — a lightweight cloud backup/sync pipeline.

**Stack:** Google Drive trigger, AWS S3  
[📄 Case study (PDF)](06_aws_s3_drive_sync/06_aws_s3_drive_sync.pdf)  &nbsp;·&nbsp;  [⚙️ workflow.json](06_aws_s3_drive_sync/workflow.json)

---

## 📚 RAG & Document Intelligence

### 07. RAG over Financial Documents
A full retrieval-QA system over financial PDFs: documents are chunked, embedded with Mistral, and stored in Qdrant; a chat interface answers questions grounded in the source files.

**Stack:** Mistral Cloud, Qdrant, retrieval-QA chain  
[📄 Case study (PDF)](07_rag_financial_documents/07_rag_financial_documents.pdf)  &nbsp;·&nbsp;  [⚙️ workflow.json](07_rag_financial_documents/workflow.json)

### 08. Company Knowledge Bot
A chat agent that answers employee questions from company documents in Google Drive, auto-indexing new files via a Drive trigger into Pinecone.

**Stack:** Google Gemini, Pinecone, Google Drive, memory  
[📄 Case study (PDF)](08_rag_company_knowledge_bot/08_rag_company_knowledge_bot.pdf)  &nbsp;·&nbsp;  [⚙️ workflow.json](08_rag_company_knowledge_bot/workflow.json)

### 09. Stock Earnings Report Analysis
Ingests earnings reports and lets an AI agent analyse them with RAG, writing structured findings to Google Docs/Sheets.

**Stack:** Gemini + OpenAI, Pinecone, Google Docs/Sheets  
[📄 Case study (PDF)](09_rag_stock_earnings/09_rag_stock_earnings.pdf)  &nbsp;·&nbsp;  [⚙️ workflow.json](09_rag_stock_earnings/workflow.json)

### 20. Customer Insights Extractor
Extracts structured insights from customer data using an information-extractor over a Qdrant RAG store, outputting to Google Sheets.

**Stack:** OpenAI, Qdrant, information extractor, Google Sheets  
[📄 Case study (PDF)](20_ml_customer_insights/20_ml_customer_insights.pdf)  &nbsp;·&nbsp;  [⚙️ workflow.json](20_ml_customer_insights/workflow.json)

### 22. Stock Q&A Assistant
A chat assistant that answers questions over financial/stock PDFs using a Qdrant-backed retrieval-QA chain.

**Stack:** OpenAI, Qdrant, retrieval-QA  
[📄 Case study (PDF)](22_finance_stock_analysis_crew/22_finance_stock_analysis_crew.pdf)  &nbsp;·&nbsp;  [⚙️ workflow.json](22_finance_stock_analysis_crew/workflow.json)

---

## 🛒 E-Commerce & Retail

### 10. Abandoned Cart Recovery
An agent that drafts personalised cart-recovery emails based on customer/product context and notifies the team via Slack.

**Stack:** OpenAI, Supabase vector store, Slack  
[📄 Case study (PDF)](10_ecommerce_abandoned_cart/10_ecommerce_abandoned_cart.pdf)  &nbsp;·&nbsp;  [⚙️ workflow.json](10_ecommerce_abandoned_cart/workflow.json)

### 11. WooCommerce Support Agent
A 31-node conversational support agent for WooCommerce: looks up orders, fetches live DHL tracking, and answers customers through a chat interface using sub-workflow tools.

**Stack:** OpenAI, WooCommerce, DHL, sub-workflow tools, chat trigger  
[📄 Case study (PDF)](11_ecommerce_woo_support_agent/11_ecommerce_woo_support_agent.pdf)  &nbsp;·&nbsp;  [⚙️ workflow.json](11_ecommerce_woo_support_agent/workflow.json)

### 12. Inventory Slack Alerts
Monitors stock levels and raises intelligent low-inventory alerts to Slack, with a RAG knowledge base for reorder context.

**Stack:** OpenAI, Pinecone, Slack, Google Sheets  
[📄 Case study (PDF)](12_ecommerce_inventory_alerts/12_ecommerce_inventory_alerts.pdf)  &nbsp;·&nbsp;  [⚙️ workflow.json](12_ecommerce_inventory_alerts/workflow.json)

### 26. Competitor Price Monitor
Scrapes competitor pricing and analyses changes with a Claude RAG agent, alerting via Slack.

**Stack:** Anthropic Claude, Supabase, Slack  
[📄 Case study (PDF)](26_data_competitor_price_monitor/26_data_competitor_price_monitor.pdf)  &nbsp;·&nbsp;  [⚙️ workflow.json](26_data_competitor_price_monitor/workflow.json)

---

## 🎬 Video & Content Creation

### 15. Hacker News to Video
Turns top Hacker News stories into narrated videos and publishes them across YouTube, Twitter, LinkedIn, Dropbox, OneDrive and Drive. 39 nodes, fully automated.

**Stack:** OpenAI, AWS S3, YouTube, Twitter, LinkedIn, Dropbox, OneDrive  
[📄 Case study (PDF)](15_video_hn_to_video/15_video_hn_to_video.pdf)  &nbsp;·&nbsp;  [⚙️ workflow.json](15_video_hn_to_video/workflow.json)

### 16. Multimodal Video Narrator
Generates narrated visual content end-to-end — LLM script, OpenAI image generation, image editing and assembly — saving the result to Google Drive.

**Stack:** OpenAI (text + image), image editing, Google Drive  
[📄 Case study (PDF)](16_video_multimodal_narrator/16_video_multimodal_narrator.pdf)  &nbsp;·&nbsp;  [⚙️ workflow.json](16_video_multimodal_narrator/workflow.json)

### 17. YouTube Comment Summarizer
Summarizes and extracts themes from YouTube comments with a RAG agent and posts the insights digest to Slack.

**Stack:** OpenAI, Pinecone, Slack, Google Sheets  
[📄 Case study (PDF)](17_video_youtube_insights/17_video_youtube_insights.pdf)  &nbsp;·&nbsp;  [⚙️ workflow.json](17_video_youtube_insights/workflow.json)

### 23. Social Media AI Agent
A Telegram-driven content agent that generates and publishes posts to LinkedIn and Twitter on a schedule, with Airtable as the content store.

**Stack:** OpenAI, Telegram, LinkedIn, Twitter, Airtable  
[📄 Case study (PDF)](23_content_social_amplifier/23_content_social_amplifier.pdf)  &nbsp;·&nbsp;  [⚙️ workflow.json](23_content_social_amplifier/workflow.json)

### 24. Brand Image Generator (9:16)
Generates branded 9:16 images from content briefs using OpenAI image generation, enriched with a Wikipedia research tool and managed in Airtable.

**Stack:** OpenAI images, Wikipedia tool, Airtable  
[📄 Case study (PDF)](24_content_brand_image_generator/24_content_brand_image_generator.pdf)  &nbsp;·&nbsp;  [⚙️ workflow.json](24_content_brand_image_generator/workflow.json)

---

## 🔬 Research & Data Agents

### 18. Self-Hosted Deep Research Agent
A 132-node autonomous research agent (the flagship): plans sub-queries, crawls the web, synthesises with Gemini + OpenAI, and writes a sourced report to Notion. Form-triggered with orchestrated sub-workflows.

**Stack:** OpenAI + Gemini, web crawling, Notion, sub-workflows  
[📄 Case study (PDF)](18_research_deep_agent/18_research_deep_agent.pdf)  &nbsp;·&nbsp;  [⚙️ workflow.json](18_research_deep_agent/workflow.json)

### 25. Autonomous Research Crawler
An autonomous agent that crawls the web, deduplicates and structures findings, and persists them to Supabase — a self-directed research pipeline.

**Stack:** OpenAI, web crawling, Supabase, sub-workflow tools  
[📄 Case study (PDF)](25_research_autonomous_crawler/25_research_autonomous_crawler.pdf)  &nbsp;·&nbsp;  [⚙️ workflow.json](25_research_autonomous_crawler/workflow.json)

### 19. Vector Anomaly Detection
Implements medoid-based anomaly detection over a dataset (crops example) with a pure HTTP + code pipeline — an ML technique demo without external AI APIs.

**Stack:** HTTP, custom code, vector math  
[📄 Case study (PDF)](19_data_vector_anomaly_detection/19_data_vector_anomaly_detection.pdf)  &nbsp;·&nbsp;  [⚙️ workflow.json](19_data_vector_anomaly_detection/workflow.json)

---

## 🏢 Business Operations (HR · Legal · Healthcare · Media)

### 21. AI Recruitment & Job Evaluation
Handles job posting and candidate evaluation: form intake, résumé parsing, AI scoring against criteria, interview scheduling via Calendar, all tracked in Airtable.

**Stack:** OpenAI, Airtable, Google Calendar, form intake  
[📄 Case study (PDF)](21_hr_ai_recruitment/21_hr_ai_recruitment.pdf)  &nbsp;·&nbsp;  [⚙️ workflow.json](21_hr_ai_recruitment/workflow.json)

### 28. NDA Risk Detector
Reviews NDA text and flags risky clauses using a RAG agent grounded in a clause-risk knowledge base.

**Stack:** OpenAI, Redis vector store, Google Sheets  
[📄 Case study (PDF)](28_legal_nda_risk_detector/28_legal_nda_risk_detector.pdf)  &nbsp;·&nbsp;  [⚙️ workflow.json](28_legal_nda_risk_detector/workflow.json)

### 29. Healthcare Appointment Agent
Sends appointment notifications and answers patient questions through a RAG agent, with Slack/WhatsApp delivery.

**Stack:** OpenAI, Supabase, Slack/WhatsApp  
[📄 Case study (PDF)](29_healthcare_whatsapp_agent/29_healthcare_whatsapp_agent.pdf)  &nbsp;·&nbsp;  [⚙️ workflow.json](29_healthcare_whatsapp_agent/workflow.json)

### 30. Podcast Transcribe & Publish
Transcribes podcast audio and publishes show notes/summaries via a Claude RAG agent, notifying through Slack.

**Stack:** Anthropic Claude, Pinecone, Slack  
[📄 Case study (PDF)](30_media_podcast_production/30_media_podcast_production.pdf)  &nbsp;·&nbsp;  [⚙️ workflow.json](30_media_podcast_production/workflow.json)

---

### How to use
1. Open n8n → **Workflows → Import from File** → pick any `workflow.json`.
2. Reconnect credentials for the services that workflow uses.
3. Adjust Google Sheet / Drive / Airtable IDs and triggers to your environment.

_30 workflows · agentic AI + automation · documented with per-project PDF case studies._

