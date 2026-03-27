# eastbaymoney.com

QR → eastbaymoney.com/talk → Formspree → Gmail

---

## One-time setup (30 minutes total)

### 1. Buy the domain (~5 min)
Purchase `eastbaymoney.com` at Namecheap (~$12/yr).

### 2. Create GitHub repo and enable Pages (~5 min)
1. Create a new public repo at github.com named `eastbaymoney`
2. Push this folder to it: `git init && git add . && git commit -m "init" && git remote add origin https://github.com/YOUR_USERNAME/eastbaymoney.git && git push -u origin main`
3. In repo Settings → Pages → Source: `main` branch, `/ (root)` folder → Save
4. GitHub will show a URL like `your-username.github.io/eastbaymoney` — ignore this, the custom domain overrides it

### 3. Connect domain to GitHub Pages (~10 min)
In Namecheap DNS, add these records:

| Type  | Host | Value                    |
|-------|------|--------------------------|
| A     | @    | 185.199.108.153          |
| A     | @    | 185.199.109.153          |
| A     | @    | 185.199.110.153          |
| A     | @    | 185.199.111.153          |
| CNAME | www  | YOUR_USERNAME.github.io  |

Then in GitHub repo Settings → Pages → Custom domain: type `eastbaymoney.com` → Save.
Check "Enforce HTTPS" once it appears (may take a few minutes).

### 4. Set up Formspree (~5 min)
1. Create free account at formspree.io
2. New form → name it "East Bay Money Talk"
3. Copy your form endpoint — looks like `https://formspree.io/f/abcdefgh`
4. In `talk/index.html`, find this line and replace the placeholder:
   ```
   action="https://formspree.io/f/REPLACE_WITH_YOUR_FORMSPREE_ID"
   ```
5. Commit and push the change
6. Formspree free tier: 50 submissions/month — more than enough for park tabling

### 5. Test end-to-end (~5 min)
- Visit `eastbaymoney.com/talk` on your phone
- Fill out and submit the form
- Confirm the response arrives in Gmail

---

## Files

```
eastbaymoney/
├── index.html          # Redirects / → /talk/
├── talk/
│   └── index.html      # The intake form (mobile-optimized)
└── sign/
    ├── sign-4x1.svg    # Print-ready sign, 4'×1', send directly to printer
    └── qr.svg          # Standalone QR code (eastbaymoney.com/talk)
```

## Sending the sign to print
`sign/sign-4x1.svg` is ready to send to any banner printer. It is:
- Vector (scales to any resolution without loss)
- Sized at `width="48in" height="12in"` (4'×1')
- Self-contained — QR code is embedded, no external files needed

Upload directly to vistaprint.com, bannersonthecheap.com, or a local FedEx Office.

## QR code durability
The QR encodes `https://eastbaymoney.com/talk`. As long as the domain is renewed (~$12/yr), the printed sign is permanently valid. The form backend (Formspree) can be swapped at any time without reprinting anything.

## Annual cost to maintain
| Item | Cost |
|---|---|
| Domain renewal (Namecheap) | ~$12/yr |
| GitHub Pages | $0 |
| Formspree (free tier) | $0 |
| **Total** | **~$12/yr** |
