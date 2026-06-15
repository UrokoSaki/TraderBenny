# TraderBenny

Professional trading education in Market Structure (SMC), Volume Profile, and Footprint charts. In-person mentorship program based in Prague.

## About

This is the official website for TraderBenny — a professional trading education site and mentorship program based in Prague, Czech Republic.

## Tech Stack

- Pure HTML, CSS, and vanilla JavaScript
- No build process required
- All images embedded as base64 (single-file deployment)
- Mobile-responsive design
- SEO optimized with Open Graph, Twitter Cards, and Schema.org structured data

## Deployment

This site is deployed via **GitHub Pages**.

### To deploy:

1. Push this repository to GitHub
2. Go to **Settings → Pages**
3. Select **Source: Deploy from a branch**
4. Choose the `main` branch and `/` (root) folder
5. Save — your site will be live at `https://<username>.github.io/<repository-name>/`

### Custom domain (optional):

1. Add a `CNAME` file to the root containing your domain (e.g., `traderbenny.com`)
2. In your domain registrar, point DNS to GitHub Pages:
   - A records: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - Or CNAME: `<username>.github.io`

## File Structure

```
traderbenny-site/
├── index.html          # Main site (all pages, all assets)
├── README.md           # This file
├── robots.txt          # Search engine instructions
├── sitemap.xml         # Sitemap for SEO
├── .gitignore          # Git ignore rules
└── CNAME               # (Add this for custom domain)
```

## Pages

- **Home** — Site introduction with featured chart
- **My Story** — Benny's personal trading journey
- **Market Structure** — SMC concepts explained
- **Volume Profile** — POC, VAH, VAL, HVN, LVN
- **Footprint** — Order flow, delta, absorption
- **Mentorship** — In-person mentorship program with contact form

## Notes

- The contact form on the Mentorship page is currently UI-only. To make it functional, connect it to a service like:
  - [Formspree](https://formspree.io/)
  - [EmailJS](https://www.emailjs.com/)
  - [Netlify Forms](https://www.netlify.com/products/forms/) (if deploying on Netlify)

## License

© 2026 TraderBenny. All rights reserved.

---

**Disclaimer:** Educational content only. Trading involves substantial risk of loss. Nothing on this site constitutes financial advice.
