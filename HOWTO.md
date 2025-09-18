# HOWTO — Field Grades (Mobile)

This guide is for **instructors** and **field evaluators** who will use the app inside Brightspace.

## Quick Start
1. Open the **Field Grades** link in your course (your admin will add it to Content or the navbar).
2. Enter your **OrgUnitId** (find it in your course URL: `.../d2l/home/{ou}`).
3. Click **Load Course**.
4. Choose a **Grade Item** from the dropdown.
5. Navigate between students with **Prev/Next** or swipe on mobile.
6. Enter a grade and optional comment → click **Save for this student**.
   - The grade is sent immediately to the Brightspace gradebook.
7. Repeat for remaining students.

## Tips
- **Current grade**: A notice shows the existing grade (if any) for the selected item/student.
- **Numeric items**: The current points (if present) are prefilled; you can overwrite before saving.
- **Filtering**: Use the **Find Student** search to filter by name or OrgDefinedId.
- **Students only**: The app lists only learners with **RoleId = 101**.

## Troubleshooting
- *“No students found”*: Verify the OrgUnitId and that the class has enrolled learners (RoleId 101).
- *Can’t save*: Ensure you have **grade entry permissions** for the selected item in this course.
- *XSRF/CSRF errors*: Make sure you’re **logged in** to Brightspace in the same browser tab.
- *Which Grade Item?* Confirm that you selected the correct grade item and grade type (Numeric, Pass/Fail, SelectBox, Text).
