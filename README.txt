# PCS Maine Squash Winter League Dashboard — Build Instructions

## What you need first
- Node.js installed on your computer (free, from nodejs.org)
  - To check if you have it: open Terminal (Mac) or Command Prompt (Windows) and type: node --version
  - If you see a version number (e.g. v20.11.0), you're good.

## Folder structure
Your project folder should look like this before building:

  squash-build/
  ├── index.html          ← provided
  ├── package.json        ← provided
  ├── vite.config.js      ← provided
  └── src/
      ├── main.jsx        ← provided
      └── App.jsx         ← THIS IS YOUR DASHBOARD FILE (squash_v9.jsx renamed to App.jsx)

## Step-by-step build

1. Copy squash_v9.jsx into the src/ folder and rename it App.jsx

2. Open Terminal (Mac) or Command Prompt (Windows)

3. Navigate to your squash-build folder:
      cd /path/to/squash-build

4. Install dependencies (only need to do this once):
      npm install

5. Build the app:
      npm run build

6. A "dist" folder will appear containing:
      dist/
      ├── index.html
      └── assets/
          ├── index-[hash].js
          └── index-[hash].css

## Putting it on your website

Option A — Root of your domain (yourdomain.com/):
  - Upload everything inside dist/ to your web server's root folder
  - No changes to vite.config.js needed

Option B — Subfolder (yourdomain.com/squash/):
  - In vite.config.js, change:  base: '/'
  - To:                         base: '/squash/'
  - Run npm run build again
  - Upload everything inside dist/ to a folder called "squash" on your server
  - Link to it from your site as: https://yourdomain.com/squash/

## Previewing before upload
After building, you can preview it locally by running:
    npm run preview
Then open http://localhost:4173 in your browser.

## Updating the data next season
1. Replace src/App.jsx with the new dashboard file
2. Run npm run build again
3. Upload the new dist/ folder to your server (overwrite the old files)
