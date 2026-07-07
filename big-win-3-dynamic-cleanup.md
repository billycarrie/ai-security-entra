# Big Win #3: Shrink the AI "Blast Radius"
## Clean Up Access Automatically Using Dynamic Security Groups

### Why This Matters
Generative AI tools can only find files that an employee already has permission to see. The problem? Over time, businesses suffer from "permission creep" where employees get added to folders or email groups for temporary projects and are never removed. 

If an administrative assistant or standard staff member accidentally has access to an old folder containing corporate tax documents or payroll spreadsheets, **an internal AI tool will proudly show them that data if they ask it a related question.**

---

### The Goal
Clean up group permissions automatically based on an employee's actual job title or department, ensuring your AI tool doesn't accidentally reveal sensitive data to the wrong users.

---

### Step-by-Step Configuration Guide

#### Step 1: Ensure User Profiles are Clean
*Before building rules, make sure your employees have the correct **Department** and **Job Title** listed in their Microsoft profiles under the Users menu.*

#### Step 2: Build a Dynamic Group for Sensitive Access
1. Log into the **[Microsoft Entra Admin Center](https://entra.microsoft.com/)**.
2. On the left menu, go to **Identity** > **Groups** > **All groups**.
3. Click **New group**.
4. Set **Group type** to **Security**.
5. Give it a clear name (e.g., `[Access] Finance Department - Automated Group`).
6. Change **Membership type** from *Assigned* to **Dynamic User**.
7. Under **Dynamic user members**, click **Add dynamic query**.
8. Set up the simple rule:
   * **Property:** `department`
   * **Operator:** `Equals`
   * **Value:** `Finance` (or whichever team you are targeting)
9. Click **Save** at the top, and then click **Create**.

*INSERT_SCREENSHOT_HERE: Screenshot showing Dynamic User query creation with department Equals Finance*

#### Step 3: Link the Group to Your Sensitive Folders
1. Use this new group to control access to your sensitive SharePoint sites, Teams channels, or shared drives. 

---

### Business Impact
If an employee moves from the Finance team to the Sales team, updating their department in Microsoft automatically strips them of their Finance access. The internal AI instantly forgets they ever had permission, drastically shrinking your internal data exposure risk.