# Molbhav — website

Static marketing site for the Molbhav expense tracker, matching the app's
ink + marigold brand. Pure HTML/CSS/JS — no build step.

```
molbhav-site/
├── index.html        # landing page (hero, features, taglines, contact)
├── terms.html        # Terms & Conditions
├── privacy.html      # Privacy Policy
└── assets/
    ├── styles.css
    ├── favicon.png
    └── app-icon.png
```

## 1. Contact form (Web3Forms — free, no backend)

The form is already wired to Web3Forms. To point it at a different inbox:

1. Go to <https://web3forms.com>, enter the email where you want messages
   delivered, and copy the **Access Key** they email you (no account needed).
2. In `index.html`, update the `access_key` value on this line with your key:
   ```html
   <input type="hidden" name="access_key" value="PASTE-YOUR-KEY-HERE" />
   ```
   Only change the `value` — do not touch the JavaScript below it.

Submissions then arrive in your inbox. If the key isn't a valid Web3Forms key,
the form shows a friendly "email us directly" message instead of failing.

## 2. Publish on GitHub Pages

1. Create a new GitHub repo, e.g. `molbhav-site`.
2. From this folder:
   ```bash
   git init
   git add .
   git commit -m "Molbhav website"
   git branch -M main
   git remote add origin https://github.com/aftabpatwekar/molbhav-site.git
   git push -u origin main
   ```
3. On GitHub: **Settings → Pages → Build and deployment → Source: Deploy from a
   branch → Branch: `main` / `/ (root)` → Save.**
4. Your site goes live at `https://aftabpatwekar.github.io/molbhav-site/` in a
   minute or two.

### Custom domain (optional)
Add a `CNAME` file containing your domain (e.g. `molbhav.app`) and point the
domain's DNS to GitHub Pages, then set the custom domain under Settings → Pages.

## Notes
- The legal pages are solid, plain-language starting points tailored to Molbhav.
  For anything you'll rely on commercially, have a lawyer review them.
- Everything is self-contained; the only external calls are Google Fonts and
  (on submit) the Web3Forms API.
