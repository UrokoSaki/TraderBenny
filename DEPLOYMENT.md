# How to deploy TraderBenny on GitHub Pages

A complete step-by-step guide. Follow these in order.

---

## Step 1 — Create a GitHub account
If you don't have one already, go to https://github.com and sign up.

---

## Step 2 — Create a new repository

1. Click the **+** icon in the top right → **New repository**
2. **Repository name:** `traderbenny` (or any name you want)
3. **Description:** "Professional trading education site"
4. Choose **Public** (required for free GitHub Pages)
5. **Do NOT** check "Initialize with README" (you already have one)
6. Click **Create repository**

---

## Step 3 — Upload your files

The easiest way (no command line needed):

1. On the new empty repository page, click **uploading an existing file**
2. Drag ALL files from the `traderbenny-site` folder:
   - `index.html`
   - `README.md`
   - `robots.txt`
   - `sitemap.xml`
   - `.gitignore`
   - `404.html`
3. Scroll down, write a commit message like "Initial site upload"
4. Click **Commit changes**

---

## Step 4 — Enable GitHub Pages

1. In your repository, click **Settings** (top tab)
2. In the left sidebar, click **Pages**
3. Under "Source", select **Deploy from a branch**
4. Branch: **main**, Folder: **/ (root)**
5. Click **Save**

GitHub will start building your site. Wait 1–2 minutes.

---

## Step 5 — Visit your live site

Your site will be live at:
```
https://<your-username>.github.io/traderbenny/
```

Replace `<your-username>` with your GitHub username.

---

## Step 6 (Optional) — Connect a custom domain

If you bought a domain (e.g., `traderbenny.com`):

### A. Add a CNAME file
1. In your repository, click **Add file** → **Create new file**
2. Filename: `CNAME` (exactly that, no extension)
3. Content: your domain name (e.g., `traderbenny.com`)
4. Commit changes

### B. Configure DNS at your registrar
Go to your domain registrar (GoDaddy, Namecheap, Google Domains, etc.) and add these records:

**For root domain (`traderbenny.com`):**
Add 4 A records pointing to:
- 185.199.108.153
- 185.199.109.153
- 185.199.110.153
- 185.199.111.153

**For www subdomain (`www.traderbenny.com`):**
Add a CNAME record pointing to: `<your-username>.github.io`

### C. Enable HTTPS
After DNS propagates (can take up to 24 hours), go back to **Settings → Pages** in GitHub and check **Enforce HTTPS**.

---

## Step 7 — Connect the contact form (Important!)

The contact form on the Mentorship page currently shows a success message but doesn't actually send emails. To make it work:

### Option A — Formspree (easiest, free up to 50/month)

1. Sign up at https://formspree.io
2. Create a new form, copy the form endpoint URL
3. In `index.html`, find the `submitForm()` function
4. Replace the `setTimeout(...)` block with a real fetch call:

```javascript
fetch('YOUR_FORMSPREE_URL', {
  method: 'POST',
  body: JSON.stringify({ name, email, experience: exp, message }),
  headers: { 'Content-Type': 'application/json' }
})
.then(() => {
  document.getElementById('contactForm').style.opacity = '0.4';
  document.getElementById('contactForm').style.pointerEvents = 'none';
  success.style.display = 'block';
  btn.textContent = 'Sent ✓';
});
```

### Option B — EmailJS
Similar approach. Documentation at https://www.emailjs.com/

---

## Step 8 — Update site URLs

In `index.html`, search and replace:
- `https://www.traderbenny.com/` → your actual final domain

Same in `sitemap.xml` and `robots.txt`.

---

## Troubleshooting

**Site not appearing after 5 minutes?**
- Check Settings → Pages — there should be a green checkmark
- The URL must end with `/` slash

**Custom domain not working?**
- DNS changes can take up to 24 hours
- Use https://www.whatsmydns.net to check propagation
- Make sure the CNAME file content has no extra spaces or newlines

**Contact form not sending?**
- Make sure you replaced the dummy code with real Formspree/EmailJS integration
- Check browser console for errors (F12 → Console)

---

## You're done!

Your professional trading education site is now live. 🎉

If anything doesn't work, the most common fix is to wait 5–10 minutes for GitHub to rebuild after your changes.
