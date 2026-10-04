# Gaurav D. Shinde: Portfolio (static site)

Plain HTML/CSS/JS. No build step and no `npm install` needed.

## Files
- `index.html`: the whole site (edit links and projects in the script near the bottom)
- `assets/`: photo, resume preview, project images, certificates, paper pages
- `favicon.svg`, `vercel.json`

## Preview on your computer
Double-click `index.html`, or run `npx serve .` in this folder.

## Deploy on Vercel (recommended: via GitHub)
1. Create an empty repo at github.com (for example `portfolio`).
2. In this folder:
   ```bash
   git init
   git add .
   git commit -m "Initial portfolio"
   git branch -M main
   git remote add origin https://github.com/Gauravs1714/portfolio.git
   git push -u origin main
   ```
3. Go to vercel.com, sign in with GitHub, then **Add New → Project** and import the repo.
4. Framework Preset: **Other**. Leave Build Command and Output Directory empty. Click **Deploy**.
5. You get a permanent `https://<project>.vercel.app` link. Every `git push` redeploys automatically.

(No GitHub? `npm i -g vercel`, then run `vercel --prod` in this folder.)

## Custom domain
1. Buy a domain (Cloudflare, Namecheap, GoDaddy, Hostinger...).
2. Vercel project → **Settings → Domains → Add** your domain.
3. Add the DNS records Vercel shows (A record for the root, CNAME for `www`) at your registrar.
4. Wait a few minutes to a few hours. HTTPS is automatic.

## Editing later
- **Links / email / photo:** the `const C={...}` line in the script of `index.html`.
- **Add a project:** copy a project object inside `const projects=[...]`. Fields: `t` title, `slug`, `c` category, `d` description, `h` highlights, `s` tech stack, `repo`, `demo` (GitHub/demo URLs), `video` (an .mp4/.webm path such as `assets/rover.mp4`, or a YouTube link), `images` (a list of paths such as `assets/rover-1.jpg`), `more` (longer text), `g` (two gradient colours).
- **Add a certificate:** add an image to `assets/`, add an entry in the `DOCS` object, and a card with `data-cert="key"` in the Certifications section.
- After any change: `git add . && git commit -m "update" && git push`.

## After deploying, check
- [ ] Every menu link and the light/dark toggle
- [ ] Project windows (images, results), certificate and paper viewers
- [ ] Email buttons open your mail app (test on phone and PC)
- [ ] Photo card rotates on scroll
- [ ] Open the site on a real phone
- [ ] Paste your link in WhatsApp/LinkedIn to see the preview card; add `og:image` and `og:url` meta tags in `index.html` once you have your final URL

## Notes
- Screenshot protection is a deterrent only; nothing on the web can fully block screenshots.
- The contact form opens the visitor's email app. For direct delivery to your inbox, ask for a Formspree setup.
