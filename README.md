# LibraTrack - Library Book Management System

DBMS Lab project: a single-page web app that stores library books in a SQL database.
Add, view, search/filter, edit, delete (with confirmation) and live summaries
(COUNT, SUM, AVG, MAX, MIN, GROUP BY) - all done with SQL.

## How it works
- Front end: plain HTML, CSS and JavaScript (no build step).
- Database: SQLite running in the browser through sql.js (WebAssembly, loaded from the jsDelivr CDN
  with a cdnjs fallback). The database is saved in the browser (localStorage) after every change,
  so records stay after a refresh. Use "Reset sample data" to start again.
- The app executes `database/library_sqlite.sql` (copied into `js/seed.js`). If you edit the SQL file,
  run `node tools/build_seed.js` to regenerate `js/seed.js`.
- `database/library_mysql.sql` is the same schema and data for MySQL 8 (Workbench, phpMyAdmin, XAMPP).

## Deploy on Vercel
1. Put these files at the root of a GitHub repository (index.html must be in the root).
2. In Vercel choose Add New > Project, import the repository.
3. Framework Preset: Other. Leave Build Command and Output Directory empty. Click Deploy.

(Or run `npx vercel` inside this folder, then `npx vercel --prod`.)

## Run locally
Open a terminal in this folder and run `npx serve .` (or `python -m http.server 8000`),
then open the address it prints. An internet connection is needed on first load for sql.js.

## Files
- index.html, css/style.css, js/app.js - the application
- js/seed.js - generated from database/library_sqlite.sql
- database/library_sqlite.sql, database/library_mysql.sql - CREATE + sample data (7 categories, 15 books)
- vercel.json - static hosting settings
