# Big Win #3: Shrink the AI "Blast Radius"
## Clean Up Stale Access with Dynamic Groups & Access Reviews

### Why This Matters
Most businesses have "Permission Creep." An employee moves teams, finishes a project, or gets promoted, but the old file share, SharePoint site, or Teams channel access from their previous role never gets removed. For years, that stale access was mostly harmless; nobody was manually digging through thousands of old folders looking for something they technically had rights to.

AI tools change that math completely. An employee doesn't need to know a confidential file exists or remember where it's stored. They just ask their AI assistant a question, and it will instantly surface anything they technically have permission to see, including access nobody meant for them to still have.

The fix isn't more AI restrictions. It's shrinking the pool of data any single identity can reach in the first place, so that if the AI (or the account itself) is ever misused, there's simply less to find.

---

### The Goal
1. **Automate Access Assignment:** Use Dynamic Groups so access to files, Teams, and SharePoint sites is automatically tied to attributes like department, job title, or role, not manual, one-off additions that get forgotten.
2. **Force Regular Cleanup:** Use Access Reviews so stale permissions are automatically flagged and removed on a recurring schedule instead of accumulating forever.

---

### Step-by-Step Configuration Guide

#### Step 1: Create a Dynamic Group Tied to Role Attributes
1. Log into the **[Microsoft Entra Admin Center](https://entra.microsoft.com/)**.
2. On the left menu, expand **Entra ID** and click **Groups**.
3. Click **New group**.
4. Set **Group type** to **Security**.
5. Give it a clear name, e.g., `SG-Finance-TeamAccess`.
6. Under **Membership type**, select **Dynamic User**.
7. Click **Add dynamic query**.
8. Build a rule based on a clean attribute, for example:
   * `department Equals "Finance"`
9. Click **Save**, then **Create**.

*INSERT_SCREENSHOT_HERE: Screenshot of the Dynamic membership rule builder in Entra ID*

   Best Practice: Connect this dynamic group (not individual users) to the SharePoint site, Teams channel, or file share that AI tools like Copilot will index/ reference. When someone changes departments in HR, their access updates automatically, no ticket required.

---

#### Step 2: Set Up a Recurring Access Review
1. On the left menu, expand **Identity Governance** and click **Access reviews**.
2. Click **New access review**.
3. Under **Select what to review**, choose **Teams + Groups** and select the groups tied to sensitive data (start with the ones connected to AI tools first).
4. Under **Review scope**, choose **Guest and member users** or narrow to **Guest users only**, depending on your risk priority.
5. Under **Frequency**, set:
   * **Recurrence:** Quarterly (Recommended starting point)
   * **Duration:** 14 days
6. Under **Reviewers**, select:
   * **Group owners**, or
   * A specific manager/security reviewer if the group has no clear owner.
7. Under **Upon completion settings**:
   * Set **Auto apply results to resource** to **Enable**.
   * Set **If reviewers don't respond** to **Remove access**.
8. Click **Start**.

*INSERT_SCREENSHOT_HERE: Screenshot of the Access Reviews configuration panel showing recurrence and auto-apply settings*

Best Practice: Start with your highest risk groups (finance, HR, executive) rather than trying to review everything at once. Expand the program once the first cycle runs cleanly.

---

### Framework Alignment/ Business Impact:
OWASP LLM Top 10 Alignment: LLM06 (Sensitive Data Disclosure)

The Standard: This category focuses on the unauthorized preview or extraction of proprietary information. An AI tool is only as safe as the access boundaries of the account asking it questions. By automating access assignment and forcing regular cleanup of stale permissions, you shrink the amount of sensitive data any single compromised or overprivileged identity, and by extension any AI tool acting on their behalf, can surface.