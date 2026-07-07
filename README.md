# Microsoft AI Security for SMBs: Entra ID Big Wins

This is a high-impact guide designed specifically for Small and Medium-Sized Businesses (SMBs).

When your business deploys AI tools, those AI technologies automatically inherits the access rights of the employee using it. If your identity security does not have a strong foundation, neither will your AI security. 

This repository breaks down **3 High-Value "Big Wins"** you can implement today using **Microsoft Entra ID** to drastically reduce your risk, reduce "Shadow IT" AI apps, and protect your data without needing a massive IT team.

---

## The 3 Big Wins

Click into any of the guides below for step-by-step instructions:

### 1. [Big Win #1: Stop the "Data-Mining" Entry Point (Phishing-Resistant MFA)](./big-win-1-mfa.md)
* **The Problem:** Standard passwords and SMS codes are easily hacked. If a hacker gets in, they can use your managede AI tools to instantly search and steal your company's private records.
* **The Fix:** Force the use of phishing resistant login methods (like Windows Hello or Security Keys) for your most critical setups.

### 2. [Big Win #2: Block Unapproved AI "Shadow IT" (App Consent)](./big-win-2-app-consent.md)
* **The Problem:** Employees often sign up for random third-party AI web apps or browser extensions using their corporate emails, accidentally giving outside platforms permission to read your company's internal data.
* **The Fix:** Shut off automatic approval and set up a "Request Permission" button so an admin can check out an AI tool before it connects to your data.

### 3. [Big Win #3: Shrink the AI "Blast Radius" (Dynamic Cleanup)](./big-win-3-dynamic-cleanup.md)
* **The Problem:** "Permission Creep." If an employee shouldn't see a confidential file but has old access permissions to it, an AI tool will instantly surface it to them if asked.
* **The Fix:** Use automated rules to clean up group access so people only see exactly what they need for their current role.

---

## Prerequisites
To use these guides, your business needs at least one of these standard Microsoft packages:
* **Microsoft 365 Business Premium**
* **Microsoft 365 E3**
*(Both include **Microsoft Entra ID P1**, which gives you all the tools required for these fixes.)*
