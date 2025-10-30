Design Notes — Task Tracker

Database Design
- Database: SQLite
- Table: tasks
- Fields:
  - id (Primary Key)
  - title (Text)
  - description (Text)
  - priority (Low / Medium / High)
  - status (Pending / Completed)
  - due_date (Date)

This structure allows easy filtering and insights calculation.

Backend Logic
- Framework: Flask
- /tasks → Add or list tasks
- /tasks/<id> → Update task status
- /insights → Compute summary like:
  - Count of total tasks
  - Count of high-priority tasks
  - Tasks due soon (within 2 days)
  - Generates readable summary text

---

Frontend Logic
- Pure HTML, CSS, and JS.
- script.js handles API calls using fetch().
- Task list updates dynamically.
- “Insights” panel updates automatically when tasks change.


Improvements (Future Work)
- Add user login (JWT)
- Add pagination and sorting in backend
- Visualize insights using charts
- Store completed tasks history
- Host frontend + backend online


Deployment Plan
- Backend: Flask with Gunicorn on Render/Heroku
- Frontend: Netlify / GitHub Pages