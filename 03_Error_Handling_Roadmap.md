# Error-Handling & AI Governance Roadmap

To ensure non-technical startup founders never make financial decisions based on hallucinated numbers or flawed metric definitions, the **Natural Language Data Concierge** enforces three core governance guardrails:

| Failure Mode | Real-World Founder Prompt Example | How the Concierge Prevents Errors |
| :--- | :--- | :--- |
| **1. Hidden Metric Trap** | *"What is our total MRR by industry?"* (Founder forgets to exclude churned accounts). | **Enforced Business Rule:** System instructions hardcode `Account_Status == 'Active'` into every MRR query and explicitly disclose the filter in the Verification Footer. |
| **2. Out-of-Schema Hallucination** | *"What is our Gross Profit Margin by Plan Tier?"* | **Graceful Refusal:** Instead of guessing or inventing profit margins, the AI checks the Database Schema Map, sees `COGS/Margin` does not exist, and triggers the `⚠️ Schema Limitation` refusal alert. |
| **3. Ambiguous / Broad Request** | *"Show me our best customers."* | **Guided Disambiguation:** Instead of guessing what "best" means, the AI asks the founder whether they define "best" by **Highest Active MRR**, **Lowest CAC Payback Period**, or **Lowest Support Ticket Volume**. |
