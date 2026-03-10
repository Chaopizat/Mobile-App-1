# Foreman Pro — PWA Deployment Guide

## What's in this folder

```
foreman-pwa/
├── index.html       ← Your full app
├── manifest.json    ← PWA config (name, icon, colors)
├── sw.js            ← Service worker (offline caching)
└── icons/
    ├── icon-192.png ← App icon (Android)
    └── icon-512.png ← App icon (splash screen)
```

---

## How to deploy (3 options, all free)

### Option A — Netlify (Easiest, 2 minutes)
1. Go to https://netlify.com and create a free account
2. Drag and drop the entire `foreman-pwa/` folder onto the Netlify dashboard
3. Done — you'll get a live URL like `https://foreman-pro.netlify.app`
4. Share that URL with anyone — they can install it from their phone browser

### Option B — GitHub Pages (Free forever)
1. Create a free GitHub account at https://github.com
2. Create a new repository called `foreman-pro`
3. Upload all files in this folder to that repo
4. Go to Settings → Pages → Source: main branch → Save
5. Your app will be live at `https://yourusername.github.io/foreman-pro`

### Option C — Vercel (Fastest CDN)
1. Go to https://vercel.com
2. Connect your GitHub repo (from Option B)
3. Click Deploy — done in 30 seconds

---

## How users install it on their phone

### Android (Chrome)
- Visit your URL in Chrome
- A banner will automatically appear after 3 seconds: "Add to Home Screen"
- Tap Install — it appears on the home screen like a native app

### iPhone (Safari)
- Visit your URL in Safari (must be Safari, not Chrome)
- Tap the Share button ⬆ at the bottom
- Scroll down and tap "Add to Home Screen"
- Tap Add — done

---

## What it can do as a PWA
✅ Installs to home screen with icon
✅ Launches fullscreen (no browser bar)
✅ Works completely offline after first load
✅ Saves all data locally (survives app restarts)
✅ Safe-area support for iPhone X+ notch
✅ Offline indicator banner
✅ Push notifications (infrastructure ready)

---

## Next steps to make it a real app store app
Once deployed as a PWA, you can wrap it for app stores using Capacitor:

```bash
npm install -g @capacitor/cli
npx cap init "Foreman Pro" com.foremanpro.app
npx cap add ios      # requires Mac + Xcode
npx cap add android  # requires Android Studio
npx cap copy
npx cap open android
```

This generates a real .apk / .ipa you can submit to Google Play or the App Store.
