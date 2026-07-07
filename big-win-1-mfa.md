# Big Win #1: Stop the "Data-Mining" Entry Point
## Enforce Phishing-Resistant Multi-Factor Authentication (MFA)

### Why This Matters
When you add AI tools to your business, those tools can search through files and emails at lightning speed. If a hacker compromises an employee’s account via a phishing attack, they don't just get into that inbox, they can now use your own AI technology to instantly mine and summarize your entire company’s history, financial files, and client data.

Standard text-message (SMS) codes and basic phone prompts are no longer enough. We need to lock the front door with a key that hackers cannot duplicate.

---

### The Goal
Enforce stronger authentication methods for all your users, or at minimum to start, your high risk accounts and managers. This means enforcing **Phishing-Resistant MFA** (like Windows Hello for Business, Face ID/Fingerprints via Microsoft Authenticator, or physical FIDO2 security keys) when accessing company data.

---

### Step-by-Step Configuration Guide

#### Step 1: Check Your Authentication Strengths
1. Log into the **[Microsoft Entra Admin Center](https://entra.microsoft.com/)**.
2. On the left menu, expand **Entra ID** and click **Authentication methods**.
3. Under this section, look at **Authentication strengths** on the left menu. You will see a built-in option called **Phishing-resistant MFA**. This is what we will use.

*INSERT_SCREENSHOT_HERE: Screenshot showing Authentication methods > Authentication strengths in Entra ID*

#### Step 2: Build the Safety Rule (Conditional Access Policy)
1. On the left menu, go to **Protection** > **Conditional Access**.
2. Click **Create new policy**.
3. Give it a clear name: `[Security] Enforce Phishing-Resistant MFA for AI Use`.
4. Under **Assignments**, choose **Users**. Select *All Users* (or start with a small pilot group of management/admin staff first to test).
5. Under **Target resources**, select **All cloud apps**.
6. Under **Grant** (located under *Access controls*):
   * Select **Grant access**.
   * Check the box for **Require authentication strength**.
   * Choose **Phishing-resistant MFA** from the dropdown.
7. Set the **Enable policy** toggle at the bottom to **Report-only** (Recommended to test without locking anyone out) or **On** if you are ready to turn on now.
8. Click **Create**.

*INSERT_SCREENSHOT_HERE: Screenshot of the Conditional Access Policy configuration panel selecting Phishing-resistant MFA*

---

#### Business Impact:
Because internal AI tools can instantly search and surface your entire company history, this layer of protection ensures that only authorized company hardware that's been's validated with Phishing-resistant MFA can ever interact with your AI data.