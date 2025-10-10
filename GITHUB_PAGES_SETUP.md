# GitHub Pages Setup Instructions

## Automated Deployment

This repository includes a GitHub Actions workflow that automatically deploys the website to GitHub Pages whenever you push to the `main` branch.

## Required Repository Settings

To enable GitHub Pages deployment, you need to configure the following settings in your GitHub repository:

### Step 1: Enable GitHub Pages

1. Go to your repository on GitHub: `https://github.com/coder-bat/life-docs`
2. Click on **Settings** (in the repository menu)
3. Scroll down and click on **Pages** (in the left sidebar)
4. Under **Build and deployment**:
   - **Source**: Select **GitHub Actions** (NOT "Deploy from a branch")
   - This tells GitHub to use the workflow file instead of automatically deploying from a branch

### Step 2: Verify Workflow Permissions

1. Still in **Settings**, click on **Actions** → **General** (in the left sidebar)
2. Scroll down to **Workflow permissions**
3. Make sure **Read and write permissions** is selected
4. Check the box for **Allow GitHub Actions to create and approve pull requests**
5. Click **Save**

### Step 3: Trigger the Deployment

The workflow will automatically run when:
- You push to the `main` branch
- You manually trigger it from the Actions tab

To manually trigger:
1. Go to the **Actions** tab in your repository
2. Click on **Deploy to GitHub Pages** workflow
3. Click **Run workflow** button
4. Select the `main` branch
5. Click **Run workflow**

### Step 4: Access Your Website

After the workflow completes successfully (takes 1-2 minutes):

1. Go back to **Settings** → **Pages**
2. You'll see a message: "Your site is live at `https://coder-bat.github.io/life-docs/`"
3. Click the URL or visit: **https://coder-bat.github.io/life-docs/**

## What Gets Deployed

The workflow deploys the entire repository content, including:

- **`index.html`** - Main wiki homepage (at the root URL)
- **`wiki-styles.css`** - Styles for the wiki homepage
- **`dog-heart-health/`** - Complete dog heart health guide
  - Accessible at: `https://coder-bat.github.io/life-docs/dog-heart-health/`

## Troubleshooting

### If deployment fails:

1. Check the **Actions** tab for error messages
2. Verify that GitHub Pages is set to use **GitHub Actions** (not branch deployment)
3. Ensure workflow permissions are set correctly
4. Make sure the workflow file is on the `main` branch

### If the page shows 404:

1. Wait a few minutes - GitHub Pages can take time to propagate
2. Make sure you're visiting the correct URL: `https://coder-bat.github.io/life-docs/`
3. Check that the deployment succeeded in the Actions tab

### If styles don't load:

1. Verify that `wiki-styles.css` is in the repository root
2. Check browser console for errors
3. Ensure the CSS file was committed and pushed

## Custom Domain (Optional)

If you want to use a custom domain:

1. Go to **Settings** → **Pages**
2. Under **Custom domain**, enter your domain (e.g., `docs.example.com`)
3. Follow GitHub's instructions to configure DNS records
4. Enable **Enforce HTTPS** after DNS propagates

## Updating the Website

Any changes you push to the `main` branch will automatically trigger a new deployment:

```bash
git add .
git commit -m "Update content"
git push origin main
```

The workflow will:
1. Detect the push
2. Build the site
3. Deploy to GitHub Pages
4. Your changes will be live in 1-2 minutes

## Workflow Status Badge

Add this to your README to show deployment status:

```markdown
![Deploy to GitHub Pages](https://github.com/coder-bat/life-docs/actions/workflows/deploy-pages.yml/badge.svg)
```

## Local Testing

Before deploying, test locally:

```bash
# Using Python
python3 -m http.server 8080

# Then visit: http://localhost:8080
```

---

## Summary Checklist

- [ ] Go to repository **Settings** → **Pages**
- [ ] Set **Source** to **GitHub Actions**
- [ ] Go to **Settings** → **Actions** → **General**
- [ ] Enable **Read and write permissions**
- [ ] Push changes to `main` branch or manually trigger workflow
- [ ] Wait 1-2 minutes for deployment
- [ ] Visit `https://coder-bat.github.io/life-docs/`

**Your wiki-style knowledge base will be live at:**  
🌐 **https://coder-bat.github.io/life-docs/**

The dog heart health guide will be accessible at:  
🐕 **https://coder-bat.github.io/life-docs/dog-heart-health/**
