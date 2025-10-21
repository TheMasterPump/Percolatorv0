# 🚀 Deploy Percolator to GitHub

Complete guide to publish Percolator to GitHub and enable GitHub Pages.

---

## 📋 Step 1: Create GitHub Repository

### Option A: Via GitHub Website

1. Go to https://github.com/new
2. Repository name: `percolator`
3. Description: `Sharded perpetual exchange protocol for Solana`
4. Choose **Public**
5. **DO NOT** initialize with README (we already have one)
6. Click "Create repository"

### Option B: Via GitHub CLI

```bash
gh repo create percolator --public --description "Sharded perpetual exchange protocol for Solana"
```

---

## 📦 Step 2: Push Code to GitHub

Open terminal in the `percolator-master` directory:

```bash
# Initialize git (if not already done)
git init

# Add all files
git add .

# First commit
git commit -m "Initial commit - Percolator v0

- v0 simplified architecture (Router + Slab programs)
- 54 unit tests passing (100%)
- Capital efficiency proof ($0 margin for zero net exposure)
- Professional website with Solana branding
- Complete documentation

Status: Core Infrastructure Complete ✓"

# Add remote (replace YOUR_USERNAME)
git remote add origin https://github.com/YOUR_USERNAME/percolator.git

# Push to GitHub
git branch -M main
git push -u origin main
```

---

## 🌐 Step 3: Enable GitHub Pages

### Via GitHub Website

1. Go to your repository: `https://github.com/YOUR_USERNAME/percolator`
2. Click **Settings** (top right)
3. Scroll down to **Pages** (left sidebar)
4. Under "Source":
   - Branch: `main`
   - Folder: `/docs`
5. Click **Save**

### Wait 1-2 minutes

GitHub will build and deploy your site.

### Your site will be live at:
```
https://YOUR_USERNAME.github.io/percolator/
```

---

## ✅ Step 4: Verify Deployment

1. Visit: `https://YOUR_USERNAME.github.io/percolator/`
2. Check that:
   - ✓ Website loads
   - ✓ Solana colors display correctly (#14f195, #9945FF)
   - ✓ All sections are visible
   - ✓ Links work

---

## 🔧 Step 5: Update Repository Settings

### Add Topics

In your GitHub repo, click ⚙️ (top right) and add topics:
- `solana`
- `defi`
- `perpetuals`
- `rust`
- `blockchain`
- `decentralized-exchange`
- `portfolio-margin`

### Update Description

Add a description in the "About" section:
```
Sharded perpetual exchange protocol for Solana with infinite capital efficiency through cross-slab portfolio margin
```

### Add Website Link

In "About" section, add website:
```
https://YOUR_USERNAME.github.io/percolator/
```

---

## 📢 Step 6: Share with Community

### Update README

Add the live site link to README.md:

```markdown
## 🌐 Live Demo

**Website:** https://YOUR_USERNAME.github.io/percolator/

**GitHub:** https://github.com/YOUR_USERNAME/percolator
```

### Share on Social Media

**Twitter Template:**
```
🚀 Just launched Percolator v0!

A sharded perpetual exchange protocol for @solana that achieves INFINITE capital efficiency 📈

✅ 54 tests passing
✅ $0 margin for hedge positions
✅ Portfolio margin across slabs

Check it out: https://YOUR_USERNAME.github.io/percolator/

#Solana #DeFi
```

**Discord/Telegram Template:**
```
🎉 Percolator v0 is live!

Sharded perpetual exchange protocol for Solana:
✓ Infinite capital efficiency
✓ 54/54 tests passing
✓ $0 margin for zero net exposure

🌐 Demo: https://YOUR_USERNAME.github.io/percolator/
💻 Code: https://github.com/YOUR_USERNAME/percolator

Built with Rust & Solana 🦀⚡
```

---

## 🔄 Future Updates

When you make changes:

```bash
# Make your changes...

# Add and commit
git add .
git commit -m "Description of changes"

# Push
git push

# GitHub Pages will auto-update in 1-2 minutes
```

---

## 🎨 Customize GitHub Pages (Optional)

### Custom Domain

If you have a domain (e.g., `percolator.exchange`):

1. In GitHub Pages settings, add custom domain
2. Update DNS settings:
   ```
   Type: CNAME
   Name: www
   Value: YOUR_USERNAME.github.io
   ```

### Custom Theme

Currently using custom HTML/CSS. To keep Solana branding, keep `docs/index.html` as is.

---

## 📊 GitHub Repository Checklist

Before going public, ensure:

- [ ] All sensitive data removed (no private keys, secrets)
- [ ] .gitignore configured properly
- [ ] README.md is clear and professional
- [ ] LICENSE file included (Apache-2.0)
- [ ] Website works on GitHub Pages
- [ ] All tests pass
- [ ] Documentation is complete

---

## 🐛 Troubleshooting

### GitHub Pages not working

**Problem:** 404 error when visiting site

**Solution:**
1. Check Settings → Pages
2. Ensure source is set to `main` branch, `/docs` folder
3. Check that `docs/index.html` exists in repo
4. Wait 5 minutes and try again

### Build failing

**Problem:** GitHub Actions failing

**Solution:**
```bash
# Test locally first
cargo build --release
cargo test

# If passing locally, check .gitignore
# Make sure /target/ is ignored
```

### Website displays incorrectly

**Problem:** Colors or layout broken

**Solution:**
- Check browser console for errors
- Verify `docs/index.html` uploaded correctly
- Clear browser cache (Ctrl+Shift+R)

---

## 🎯 Quick Reference

| Action | Command |
|--------|---------|
| Check git status | `git status` |
| Add all files | `git add .` |
| Commit changes | `git commit -m "message"` |
| Push to GitHub | `git push` |
| View remote URL | `git remote -v` |
| Check branches | `git branch -a` |

---

## 📞 Need Help?

- **GitHub Docs:** https://docs.github.com/pages
- **Git Docs:** https://git-scm.com/doc
- **GitHub Support:** https://support.github.com

---

**You're ready to deploy! 🚀**

Run through the steps above and your project will be live for the community to see!

---

**Last Updated:** October 21, 2025
