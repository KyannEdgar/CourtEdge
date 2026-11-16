<div align="center">
  <img src="https://github.com/user-attachments/assets/50da3727-0829-4a0e-b947-df658130567a" width="250" alt="CourtEdge Logo" />
  
  # CourtEdge: Automated NBA Intelligence & Probabilistic Betting Projections
  **Developer:** Kian Edgar V. Abustan
</div>

> **Note to Readers:** The source code for CourtEdge operates securely within a private Amazon Web Services (AWS) environment. This README serves as the official technical documentation and architectural overview of the project.

## 📌 Project Overview
CourtEdge is an automated cloud application designed to aggregate live sports data, analyze it using artificial intelligence, and deliver formatted analytical briefings. Positioned as a SaaS (Software as a Service) quantitative data provider, it offers mathematical edges to sports bettors rather than operating as a traditional pick-selling service. The platform functions seamlessly through a highly automated Discord community.

## ⚙️ How It Works: The Dual-Pipeline System
The system operates entirely hands-off on a two-part daily lifecycle:

*   **Pre-Game Generation Pipeline:** Prior to tip-off, an automated scheduler wakes the system up. It queries public sports APIs to gather schedules, standings, injuries, and odds. This data is fed into an AI model (Claude 3 Opus) to perform deep mathematical reasoning and format the predictions into three tiers: Conservative, Standard, and Aggressive. These insights are then securely routed to distinct Discord channels based on a user's subscription level.
*   **Post-Game Grading Pipeline:** The following day, the system automatically pulls its previous predictions and fetches the actual final game scores. The AI evaluates its own performance, grading every prediction strictly as a WIN, LOSS, or PUSH. It calculates win percentages and compiles a comprehensive CSV log. To maintain absolute business transparency, a daily performance summary and the raw CSV file are automatically published to the community.

## 🛠️ Technology Stack & Infrastructure
CourtEdge combines a 100% serverless cloud backend with a dynamic community frontend. 

**Backend Infrastructure (Amazon Web Services):**
*   **Compute & Automation:** AWS Lambda executes the core scripts, while Amazon EventBridge schedules the daily tasks, ensuring resources remain completely idle until execution.
*   **AI Integration:** Amazon Bedrock powers the system's logic, utilizing the Claude 3 Opus model for advanced reasoning.
*   **Storage:** Amazon DynamoDB acts as the central database connecting the pipelines, and Amazon S3 provides secure storage for the daily transparency logs.
*   **Security:** AWS Secrets Manager encrypts routing URLs, and AWS IAM enforces strict least-privilege security between all cloud services.

**Frontend Ecosystem (Discord):**
*   **Data Delivery:** Custom Discord Webhooks distribute the AI's textual analysis and data files directly to specific channels.
*   **Monetization & Access:** Upgrade.chat acts as the business storefront, processing payments and instantly managing VIP access based on active subscriptions.
*   **User Experience Bots:** The server integrates specialized tools to handle security, live NBA score updates, and deep player statistics.

## 📈 Business Model & Efficiency
The architecture was strategically designed to eliminate traditional fixed-cost overhead, such as monthly web hosting or proprietary app maintenance. 

*   **Cost-Effective Scalability:** By utilizing pay-per-request serverless infrastructure and Discord as a zero-cost frontend, operational expenses are tied strictly to AI execution volume.
*   **High-Margin Economics:** Because backend infrastructure costs are kept virtually non-existent, the business operates at an estimated 85%+ gross profit margin per active subscriber.
