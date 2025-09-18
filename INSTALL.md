# INSTALL — Admin Directions (Organization Files *or* Course Files)

This guide is for **Brightspace admins** (or course designers with Manage Files permissions). You have two options:
- **A. Organization Files** (one central copy for all courses) — recommended for multi-course use.
- **B. Course Files** (per course copy) — simple and self-contained.

> The app is a single, self-contained `index.html` file (no dependencies).

---

## A) Deploy to **Organization Files** (Global)
1. Go to **Admin Tools (gear) → Manage Files** (Organization-level).
2. Create a folder, e.g.:
   ```
   org-tools/field-grades
   ```
3. **Upload** `index.html` into that folder.
4. **Get the file URL**:
   - In Manage Files, open the action menu for `index.html` and choose **Open** (or **View**).
   - Copy the browser URL you see (this is the direct link used in Step 6 below).
5. (Optional) If your org uses a public/static hosting area, you may use that URL instead.
6. **Create a link for instructors** (two common options):
   - **Content Link (global):**
     - Go to Admin Tools
     - External Links
     - New Link
     - Then click on the External Links page at top
     - Find the new link you create
     - Click the link to open in a new tab
     - Copy URL to webapp
   - **Content Link (per course):**
     - In the target course, go to **Content → +Add Existing → Create a Link** (or *New → Create a Link*).
     - Title: **Field Grades (Mobile)**
     - URL: **paste the Organization Files URL** from step 4.
     - Enable **Open as External Resource** (new tab) if desired.
   - **Navbar Link (global, via Org Navbar):**
     - Go to **Admin Tools → Navigation & Themes**.
     - Edit the navbar used by your courses → **Add Link → Create Custom Link**.
     - Name: **Field Grades (Mobile)**
     - URL: **paste the Organization Files URL** from step 4.
     - Save, then **Apply** the updated navbar to the desired org units.

**Pros:** One central file for all courses.  
**Cons:** You must ensure all courses/roles can access the Organization Files resource URL (standard in most setups).

---

## B) Deploy to **Course Files** (Per Course)
1. In the target course, go to **Course Admin → Manage Files**.
2. Create a folder, e.g.:
   ```
   content/api-apps/field-grades
   ```
3. **Upload** `index.html` into that folder.
4. **Link it in the course** (two common options):
   - **Content Link (simple):**
     - Go to **Content → +Add Existing → Create a Link** (or *New → Create a Link*).
     - Title: **Field Grades (Mobile)**
     - URL: `/content/api-apps/field-grades/index.html`
     - Enable **Open as External Resource** (optional).
   - **External Learning Tool (LTI) link**: *Not required for this app.* This app runs under the instructor’s current session and does not need LTI. Prefer the simple **Create a Link** route above.

**Pros:** Self-contained per course; no global dependencies.  
**Cons:** You’ll manage multiple copies if many courses use it.

---

## Permissions & Roles
- Instructors (or graders) need permissions to **view classlist** and **enter grades** for the selected items.
- The app filters to learners with **RoleId = 101** by default. If your org’s student role uses a different ID, update the constant at the top of the script:
  ```js
  var STUDENT_ROLE_ID = 101;
  ```

## API Versions
- Classlist: `LE 1.86`
- Grades: `LE 1.85`
You may bump these if your environment supports higher versions:
```js
var GRADES_API_VER   = "1.85";
var CLASSLIST_VER    = "1.86";
```

## URL Notes
- **Course Files path example:** `/content/api-apps/field-grades/index.html`
- **Organization Files:** copy the **exact URL** from Manage Files when opening the file; this ensures a working link in all courses.

## Testing Checklist
- Open the link as an **Instructor** in a live course with enrolled learners.
- Enter the **OrgUnitId** and click **Load Course**.
- Confirm you can:
  - See only learners (RoleId 101)
  - Select Grade Items
  - View current grade notice
  - Save a grade successfully
