# Field Grades (Mobile)

A lightweight mobile-friendly web app for quickly entering grades directly into D2L Brightspace.

## Features
- Navigate through students with Prev/Next buttons (disabled at ends)
- Enter numeric or scheme-based grades
- Shows current grade value before editing
- Immediate save via API (no queueing)
- Fully contained HTML file (no dependencies)

## Usage
1. Upload `index.html` into your D2L environment (e.g., as a course file or widget).
2. Open the app in your browser inside Brightspace (uses logged-in session).
3. Enter your OrgUnitId, pick a grade item, and start grading.

## API Calls
- Classlist: `/d2l/api/le/1.85/{orgUnitId}/classlist/paged/`
- Grade items: `/d2l/api/le/1.85/{orgUnitId}/grades/`
- Grade values: `/d2l/api/le/1.85/{orgUnitId}/grades/{gradeId}/values/{userId}`

---
© 2025 Delta College (example). Released for collaboration among D2L schools.
