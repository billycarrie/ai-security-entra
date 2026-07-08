# Microsoft AI Security for SMBs: Entra ID Big Wins

This is a high-impact guide designed specifically for Small and Medium-Sized Businesses (SMBs).

When your business deploys AI tools, those AI technologies automatically inherits the access rights of the employee using it. If your identity security does not have a strong foundation, neither will your AI security. 

This repository breaks down **3 High-Value "Big Wins"** you can implement today using **Microsoft Entra ID** to drastically reduce your risk, reduce "Shadow IT" AI apps, and protect your data without needing a massive IT team.

---

## The 3 Big Wins

Click into any of the guides below for step-by-step instructions:

1. [Big Win #1: Stop the "Data-Mining" Entry Point (Phishing-Resistant MFA)](https://github.com/billycarrie/ai-security-entra/blob/main/big-win-1-mfa.md)

* The Problem: Standard passwords and SMS codes are easily hacked. If a hacker gets in, they can use your managed AI tools to instantly search and steal your company's private records.
* The Fix: Force the use of phishing resistant login methods (like Windows Hello or Security Keys) for your most critical setups.
* OWASP Importance: Aligns with **LLM06 (Sensitive Data Disclosure)** — hardware-backed MFA on admin identities stops an outside attacker from turning your own AI deployment into a tool for mining your company's data.

2. [Big Win #2: Block Unapproved AI "Shadow IT" (App Consent)](https://github.com/billycarrie/ai-security-entra/blob/main/big-win-2-app-consent.md)

* The Problem: Employees often sign up for random third-party AI web apps or browser extensions using their corporate emails, accidentally giving outside platforms permission to read your company's internal data.
* The Fix: Shut off automatic approval and set up a "Request Permission" button so an admin can check out an AI tool before it connects to your data.
* OWASP Importance: Aligns with **LLM08 (Excessive Agency)** — unreviewed AI apps requesting broad data-access scopes are a textbook case of an integration being granted more permission than it needs.

3. [Big Win #3: Shrink the AI "Blast Radius" (Dynamic Cleanup)](https://github.com/billycarrie/ai-security-entra/blob/main/big-win-3-dynamic-cleanup.md)

* The Problem: "Permission Creep." If an employee shouldn't see a confidential file but has old access permissions to it, an AI tool will instantly surface it to them if asked.
* The Fix: Use automated rules to clean up group access so people only see exactly what they need for their current role.
* OWASP Importance: Aligns with **LLM06 (Sensitive Data Disclosure)** — shrinking what each identity can reach limits how much an AI tool (or a compromised account) can surface, even if something else fails.

---

## Prerequisites
To use these guides, your business needs at least one of these standard Microsoft packages:
* **Microsoft 365 Business Premium**
* **Microsoft 365 E3**
*(Both include **Microsoft Entra ID P1**, which gives you all the tools required for these fixes.)*
