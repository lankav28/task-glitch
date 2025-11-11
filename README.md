🧠 TaskGlitch – SDE Bug Fix Challenge
🚀 Live Demo

🔗 taskglitch-lankav28.surge.sh

🧾 Project Overview

TaskGlitch is a Task Management Web App designed for sales teams to track, manage, and prioritize tasks based on ROI (Return on Investment).
This version focuses on stabilizing the application by identifying and fixing critical UI, logic, and performance bugs.

⚙️ Tech Stack

Frontend: React + TypeScript + Vite

UI Library: Material UI (MUI)

State Management: React Context API

Hosting: Surge

Data: LocalStorage persistence (no backend)

🧩 Fixed Bugs Summary
✅ Bug 1 – Double Fetch Issue

Problem: Tasks were being fetched twice due to duplicate useEffect calls.
Fix: Added a fetchedRef guard to ensure data fetch runs only once.

✅ Bug 2 – Undo Snackbar Bug

Problem: Undo restored old deleted tasks even after snackbar closed.
Fix: Reset lastDeletedTask when snackbar closes or undo completes.

✅ Bug 3 – Unstable Sorting

Problem: Tasks with equal ROI and priority were flickering on rerender.
Fix: Implemented deterministic sorting:

Primary → ROI

Secondary → Priority

Tertiary → Title (A–Z)

Fallback → CreatedAt (newest first)

✅ Bug 4 – Double Dialog Opening

Problem: Edit/Delete triggered both View and Edit dialogs simultaneously.
Fix: Added stopPropagation() on Edit/Delete button clicks in TaskTable.tsx.

✅ Bug 5 – ROI Calculation & Validation

Problem: Invalid ROI (NaN/Infinity) due to division by zero or missing data.
Fix: Added safe ROI computation with formatting and fallback to 0.

📊 Features

✅ Add, edit, and delete tasks
✅ ROI auto-calculation (Revenue ÷ Time Taken)
✅ Undo delete with snackbar
✅ Search, filter, and sort tasks
✅ Summary metrics (Total Revenue, Average ROI, etc.)
✅ Export tasks as CSV
✅ Charts & analytics dashboards
✅ LocalStorage persistence

🧱 Folder Structure
src/
├── components/
│   ├── TaskTable.tsx
│   ├── TaskForm.tsx
│   ├── UndoSnackbar.tsx
│   ├── ChartsDashboard.tsx
│   ├── AnalyticsDashboard.tsx
│   └── ActivityLog.tsx
├── context/
│   ├── TasksContext.tsx
│   └── UserContext.tsx
├── utils/
│   ├── logic.ts      // Core ROI and sorting logic
│   └── csv.ts
├── App.tsx
└── main.tsx

🧰 Installation & Run Locally
# Clone the repository
git clone https://github.com/lankav28/task-glitch.git

# Navigate to project
cd task-glitch

# Install dependencies
npm install

# Run locally
npm run dev

🏗️ Build & Deploy
npm run build
surge dist taskglitch-lankav28.surge.sh

🧠 Developer

👩‍💻 Kaveramma M B
GitHub: lankav28

Email: mbkaveramma@gmail.com

✅ Final Evaluation Notes

All five critical bugs are fixed, UI stable, ROI validated, sorting deterministic, and the app is live and functional.
This project meets all the assignment’s acceptance criteria.
