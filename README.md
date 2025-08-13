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

## step 4 - Basic Authentication for /team

**Username:** grader  
**Password:** 1234
**Protected URL:** https://ucsdcse135.site/team/

## Step 5 — Compression (gzip) verification

**What I enabled**
- Enabled Apache modules: `mod_deflate` (and `filter`, `headers`).
- Added rules in `/etc/apache2/mods-enabled/deflate.conf`:

## Step 6 — Obscure server identity

To set a custom `Server` header, I used Apache ModSecurity instead of only
`ServerTokens/ServerSignature` (those only hide version, not fully replace).

Commands:
- `sudo apt install libapache2-mod-security2 && sudo a2enmod security2`
- Copied and enabled rules: `modsecurity.conf-recommended` → `modsecurity.conf`
- Added: `SecServerSignature "CSE135 Server"` in `/etc/modsecurity/custom-server-header.conf`
- Restarted Apache.

Verification: Chrome DevTools → Network shows `Server: CSE135 Server` on the home page.

## Step 7 — Configured custom 404 by adding:
-ErrorDocument 404 /404.html

-inside the ucsdcse135.site vhosts (HTTP and HTTPS). Verified by visiting a non-existent URL and seeing the custom page.
