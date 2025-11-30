# GitHub Pages Deployment Guide for Freo Now

## 📋 Prerequisites
- GitHub account (free at github.com)
- Git installed on your computer
- Your repository at `f:\dev\git_fn\freo_now`

---

## 🚀 EXACT DEPLOYMENT STEPS

### Step 1: Update Credentials (Optional)
If you want to change the login credentials:
1. Open `.env` file in your text editor
2. Update `VITE_AUTH_USERNAME` and `VITE_AUTH_PASSWORD`
3. Example:
   ```
   VITE_AUTH_USERNAME=myusername
   VITE_AUTH_PASSWORD=mysecurepassword
   ```
4. Save the file
5. **⚠️ IMPORTANT:** `.env` is in `.gitignore` so it won't be pushed to GitHub (this keeps your credentials secret)

### Step 2: Create GitHub Repository
1. Go to https://github.com/new
2. Repository name: `freo-now` (or your preferred name)
3. **IMPORTANT:** Select **PUBLIC** (required for free GitHub Pages)
4. DO NOT initialize with README (you already have files)
5. Click "Create repository"
6. Copy the repository URL (looks like `https://github.com/YOUR_USERNAME/freo-now.git`)

### Step 3: Initialize Git & Connect to GitHub
Open PowerShell and run these commands:

```powershell
# Navigate to your project
cd f:\dev\git_fn\freo_now

# Initialize git repository
git init

# Add all files
git add .

# Create initial commit
git commit -m "Initial Freo Now deployment"

# Add remote repository (replace with your URL from Step 2)
git remote add origin https://github.com/YOUR_USERNAME/freo-now.git

# Rename branch to main (if needed)
git branch -M main

# Push to GitHub
git push -u origin main
```

### Step 4: Enable GitHub Pages
1. Go to your GitHub repository: `https://github.com/YOUR_USERNAME/freo-now`
2. Click **Settings** (top right)
3. Click **Pages** (left sidebar)
4. Under "Build and deployment":
   - Source: select **Deploy from a branch**
   - Branch: select **main** and folder **/ (root)**
5. Click **Save**
6. Wait 1-2 minutes for GitHub to build your site

### Step 5: Access Your Site
Your site is now live at:
```
https://YOUR_USERNAME.github.io/freo-now/
```

Example: `https://myusername.github.io/freo-now/`

You'll see the login page with your configured credentials.

---

## 🔄 How to Update Your Site

After making changes to your files:

```powershell
cd f:\dev\git_fn\freo_now

# Stage changes
git add .

# Commit with a message
git commit -m "Description of your changes"

# Push to GitHub
git push
```

GitHub will automatically rebuild your site (1-2 minutes).

---

## 🔐 Updating Credentials for GitHub Pages

Since `.env` is in `.gitignore`, you have two options:

**Option A: Keep Demo Credentials (Easiest)**
- Use the default credentials in `.env`
- Tell people: Username: `freo`, Password: `now2025`

**Option B: Change Credentials**
1. Edit `.env` file locally with new credentials
2. DON'T commit/push (`.gitignore` protects it)
3. Push to GitHub with `git push`
4. Share new credentials only with intended users

---

## 🎯 Optional: Use Custom Domain

1. Buy a domain (Namecheap, GoDaddy, etc.)
2. In your GitHub repo → Settings → Pages
3. Under "Custom domain": enter your domain (e.g., `freonow.com.au`)
4. Update DNS records at your registrar (GitHub provides instructions)
5. Wait 24 hours for DNS to propagate

Your site will be at: `https://freonow.com.au` or `https://www.freonow.com.au`

---

## ⚠️ Important Security Notes

**This uses client-side authentication** — suitable for:
- ✅ Blocking casual/casual viewing
- ✅ Preventing search engine indexing
- ✅ Sharing with specific groups

**NOT suitable for:**
- ❌ Highly sensitive financial/confidential data
- ❌ Medical or regulated information
- ❌ Enterprise security requirements

For stronger security, consider:
- **Netlify** (https://netlify.com) - free, supports environment variables
- **Vercel** (https://vercel.com) - free, supports environment variables
- **Azure Static Web Apps** - enterprise security

---

## ✅ Deployment Checklist

- [ ] GitHub account created and verified
- [ ] `.gitignore` file exists (don't track `.env`)
- [ ] `.env` file updated with your credentials
- [ ] GitHub repository created (PUBLIC)
- [ ] Git initialized: `git init`
- [ ] All files added: `git add .`
- [ ] Initial commit created: `git commit -m "Initial Freo Now"`
- [ ] Remote added: `git remote add origin https://...`
- [ ] Pushed to GitHub: `git push -u origin main`
- [ ] GitHub Pages enabled in Settings
- [ ] Site accessible at `https://YOUR_USERNAME.github.io/freo-now/`
- [ ] Login page appears
- [ ] Credentials work
- [ ] All navigation pages load correctly

---

## 🐛 Troubleshooting

**Issue:** "GitHub Pages deployment failed"
- Solution: Make sure repository is PUBLIC, not private

**Issue:** "Push rejected - remote not found"
- Solution: Verify URL: `git remote -v`
- Fix: `git remote set-url origin https://YOUR_URL`

**Issue:** "404 Not Found" on GitHub Pages
- Solution: Wait 2-3 minutes after enabling Pages
- Or: Rebuild by making a new commit and pushing

**Issue:** "auth.html not found"
- Solution: Make sure `auth.html` is in root directory
- Check: `git ls-files` shows auth.html

**Issue:** "Can't login even with correct credentials"
- Solution: Check .env file has correct credentials
- Try: Hard refresh browser (Ctrl+Shift+R)
- Check: Browser console for errors (F12)

**Issue:** "I don't see a login page, just the main content"
- Solution: The file structure was wrong. It's been fixed.
- The entry point is now `index.html` (login page)
- Main content is `main.html`
- Make sure you've pulled the latest changes: `git pull`

**Issue:** "Navigation links are broken"
- Solution: Links now point to `main.html` instead of `index.html`
- This was updated in the fix above
- Pull latest: `git pull`

---

## 📚 Useful Resources

- GitHub Pages Docs: https://pages.github.com/
- GitHub Pages Settings: https://docs.github.com/en/pages
- Custom Domain Setup: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site
- Git Basics: https://git-scm.com/book/en/v2

---

## 📞 Summary

1. Create public GitHub repo
2. Run: `git init`, `git add .`, `git commit -m "..."`, `git remote add origin URL`, `git push -u origin main`
3. Enable GitHub Pages in Settings
4. Visit: `https://YOUR_USERNAME.github.io/freo-now/`
5. Done! ✅
