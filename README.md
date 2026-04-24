# Hyde Park Equipment — Warranty Management System

A warranty claim management web app for Hyde Park Equipment Ltd. Built for HYD010 (London) and HYD020 locations. Manages the full warranty lifecycle from work order review through OEM submission, reconciliation, and archive.

---

## Live App

Once deployed, the app will be available at:
```
https://[your-github-username].github.io/hpe-warranty/
```

---

## Quick Deploy to GitHub Pages

### Step 1 — Create a GitHub account
If you don't already have one, go to [github.com](https://github.com) and sign up. It's free.

### Step 2 — Create a new repository
1. Click the **+** button top right → **New repository**
2. Name it: `hpe-warranty`
3. Set it to **Private** (recommended — only people with the link can access)
4. Click **Create repository**

### Step 3 — Upload the files
1. On your new repository page, click **uploading an existing file**
2. Drag and drop ALL files from this folder into the upload area:
   - `index.html`
   - `README.md`
   - `.github/` folder (the whole folder)
3. Scroll down, add a commit message like `Initial deployment`
4. Click **Commit changes**

### Step 4 — Enable GitHub Pages
1. Go to your repository **Settings** (top menu)
2. Click **Pages** in the left sidebar
3. Under **Source**, select **GitHub Actions**
4. The workflow will run automatically — wait about 60 seconds
5. Refresh the page — your live URL will appear at the top

### Step 5 — Share the URL
Copy the URL (format: `https://[username].github.io/hpe-warranty/`) and share it with your team. Bookmark it on phones and tablets — it works as a mobile web app.

---

## Updating the App

When you receive an updated `index.html` file:
1. Go to your repository on GitHub
2. Click on `index.html`
3. Click the **pencil icon** (Edit) top right — or click the three dots → **Upload file**
4. Upload the new file
5. Commit the change — it deploys automatically within 60 seconds

---

## User Roles & Default Access

| Role | Name | Notes |
|------|------|-------|
| Technician | Andrew, Alex, John, Jared (HYD010) | |
| Technician | Nate, Don, Tyler, Ed, Al, Logan, Caden (HYD020) | |
| Warranty Admin | Andy | Full claim workflow |
| Service Manager | Steve | HYD010 only |
| Service Manager | Bill | HYD020 only |
| Admin / Finance | Anne | Reconciliation only |
| Management | (tap logo 3×) | Full access |

**To add or edit users:** Log in as Management → Staff & Locations → Add User or Edit.

---

## Current Version

**v7** — Includes: role-based access, two-location support (HYD010/HYD020), Smartsheet WO integration, AI Three Cs review, part retention tracking, printable labels, closed claims archive, reconciliation history, analytics dashboard, warranty validity checks, OEM submission workflow.

---

## Production Upgrade Path

This version runs entirely in the browser with no backend — all data resets on refresh. When you're ready to make data persistent across sessions and devices:

| Service | Purpose | Cost |
|---------|---------|------|
| [Supabase](https://supabase.com) | Database (replaces in-memory data) | Free tier |
| [Google Drive API](https://console.cloud.google.com) | Photo/file storage | Free (uses existing Drive) |
| [Smartsheet API](https://smartsheet.com/developers) | Live WO sync | Included in Smartsheet plan |

Estimated developer cost to wire up the backend: **$300–600 on Upwork/Fiverr** using this prototype as the full specification.

---

## Support

Built by Claude (Anthropic). For changes or issues, return to the Claude conversation and describe what needs updating.
