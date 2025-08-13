# CSE 135 – HW1

This repo contains my HW1 website for CSE 135.  
The site is served from my DigitalOcean Droplet (Ubuntu + Apache).

## 🌐 Live URLs
- Team Home (stub): https://ucsdcse135.site/
- Personal Page: https://ucsdcse135.site/members/boscoliu/

(Info) Other vhosts created in Part 1:
- collector: https://collector.ucsdcse135.site/
- reporting: https://reporting.ucsdcse135.site/

## 📁 What’s Included
- Valid HTML (checked via W3C validator)
- `favicon.ico` at site root (prevents silent 404s)
- `robots.txt` at site root (minimal allow-all)

## 📦 Directory / Files (short)
- `index.html` — Team/homework stub page (links to member + assignments)
- `members/boscoliu/` — my personal site from CSE134B (HTML/CSS/JS/assets)
- `about.html`, `projects.html`, `contact.html`, `resume.html`,
  `form-no-js.html`, `form-with-js.html`, `assets/`, `astro-blog/` — additional
  static pages/resources used by my personal site
- (recommended to keep in repo) `favicon.ico`, `robots.txt`

> Server webroot: `/var/www/ucsdcse135.site/html`

## 🚀 Deployment
**Option A — Manual (current setup)**
1. Commit & push changes to this repo (`main`).
2. SSH to the Droplet and run:
   ```bash
   cd /var/www/ucsdcse135.site/html
   git pull
