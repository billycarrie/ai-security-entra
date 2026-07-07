# Big Win #2: Block Unapproved AI "Shadow IT"
## Turn Off Default User Consent for Third-Party AI Apps

### Why This Matters
Employees love productivity shortcuts. If they find a cool new AI tool online (like a PDF summarizer, an AI email writer, or a grammar plugin), they will often click *"Sign in with Microsoft"*. 

By default, clicking "Accept" can grant that unverified, third-party AI company full permission to read their employee profile, access their mailbox, and scan files in their OneDrive. This is how corporate data silently leaks out to unapproved third parties.

---

### The Goal
Block employees from automatically giving outside AI apps access to your company’s internal data, and replace it with a "Request Permission" button. Now, these requests will be sent to the designated IT Admin or Business Owner for approval.

---

### Step-by-Step Configuration Guide

#### Step 1: Disable Automatic Third-Party Approvals
1. Log into the **[Microsoft Entra Admin Center](https://entra.microsoft.com/)**.
2. On the left menu, click **Identity** > **Applications** > **Enterprise applications**.
3. Under the Manage section, click **Consent and permissions**.
4. Click on **User consent settings**.
5. Select the option: **Do not allow user consent**. 
6. Click **Save** at the top.

*INSERT_SCREENSHOT_HERE: Screenshot of User consent settings set to "Do not allow user consent"*

#### Step 2: Turn on the "Request Permission" Button
1. In that same menu on the left, click **Admin consent settings**.
2. Under **Admin consent requests**, change the toggle for *"Users can request admin consent to apps they are unable to consent to"* to **Yes**.
3. Under **Who can review admin consent requests**, select your main IT admin or business owner account.
4. Set email notifications to **Yes** so you get an alert when an employee wants to use a tool.
5. Click **Save**.

*INSERT_SCREENSHOT_HERE: Screenshot of Admin consent requests workflow enabled with designated reviewers*

---

### Business Impact
The next time an employee tries to connect a random AI website/ app to their work account, they will see a message saying *"Approval Required."* They can type a brief note explaining why they want it. Your business data stays completely safe until an admin reviews and approves the tool.

### Note
This will impact all third party applications that users try to sign into using their company credentials. Not just AI specific tools. Best practice for a change such as this will be to communicate out to end users at least two weeks before change is live of what's coming. Be sure to create a standard workflow of how requests will be processed from intake (Emails routed to Ticketing System) to request decision of approval/ denial (From IT Admin/ Business Owner). 