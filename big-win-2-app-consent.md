# Big Win #2: Block Unapproved AI "Shadow IT"
## Restrict User App Consent & Require Admin Review

### Why This Matters
Employees don't need IT's permission to try a new AI tool. They just click "Sign in with Microsoft" on a random AI writing assistant, note-taker, or browser extension, and grant it access using their corporate credentials. In that one click, they may be handing an unvetted third-party app permission to read their mailbox, browse their files, or access their calendar, permanently, and completely outside of IT's visibility.

This is the "Shadow IT" problem: AI tools your business never approved, quietly connected to your business data. Once that consent is granted, the app doesn't need to hack anyone. It already has the keys.

By default, Entra ID allows every user to consent to these permissions on their own. We need to close that door and put a human in the loop.

---

### The Goal
1. **Turn Off Blanket User Consent:** Stop end users from being able to grant data access permissions to third-party apps on their own.
2. **Stand Up an Admin Consent Workflow:** Give employees a legitimate, low-friction way to request a new AI tool, so IT/Security can review the permissions being requested before access is granted.

---

### Step-by-Step Configuration Guide

#### Step 1: Restrict User Consent for Applications
1. Log into the **[Microsoft Entra Admin Center](https://entra.microsoft.com/)**.
2. On the left menu, expand **Entra ID** and click **Enterprise applications**.
3. Under **Security**, click **Consent and permissions**.
4. Click **User consent settings**.
5. Under **User consent for applications**, select:
   * **Do not allow user consent** (Recommended for full lockdown), or
   * **Allow user consent for apps from verified publishers, for selected permissions** (Recommended if you want a lighter-touch starting point).
6. Click **Save**.

*INSERT_SCREENSHOT_HERE: Screenshot of the User consent settings panel in Entra ID*

Best Practice: If you're not ready to fully lock this down, start with the "verified publishers" option first, then tighten to "Do not allow" once your admin consent workflow (Step 2) is live and employees know how to request access.

---

#### Step 2: Set Up the Admin Consent Request Workflow
1. Staying under **Consent and permissions**, click **Admin consent settings**.
2. Set **Users can request admin consent to apps they are unable to consent to** to **Yes**.
3. Under **Select users to review admin consent requests**, add the reviewers:
   * Recommended reviewers:
     - Named individuals with the Roles assigned of "Applications Administrator" or "AI Administrator" for clear ownership (avoid a single point of failure)
4. Set the **email notifications** and **reminder** toggles to **Yes**, so requests don't sit unnoticed.
5. Click **Save**.

*INSERT_SCREENSHOT_HERE: Screenshot of the Admin consent settings panel showing reviewers configured*

6. Communicate the new process to employees: "If you need a new AI tool connected to your Microsoft account, you'll now see a 'Request approval' option instead of a consent screen. IT will review and respond."

---

### Framework Alignment/ Business Impact:
OWASP LLM Top 10 Alignment: LLM08 (Excessive Agency)

The Standard: This category addresses the risk of granting an AI system, or a plugin/tool connected to it, more permission or autonomy than necessary to do its job. An unreviewed third-party AI app requesting broad Graph API scopes (mail, files, directory data) is a textbook case of excessive agency being granted by default. Requiring admin review before consent ensures every AI integration is scoped to only what it actually needs, and that someone is accountable for approving it.