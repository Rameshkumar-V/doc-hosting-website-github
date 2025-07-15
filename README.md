
---

# 🚀 Deploy React (Vite) Project to GitHub Pages (Step-by-Step)

## 📋 Prerequisites

* Node.js installed
* GitHub account
* A new or existing GitHub repository

---

## ⚙️ 1. Install `gh-pages` (Optional but recommended for easy deploy)

In your **React + Vite** project root directory:

```bash
npm install --save-dev gh-pages
```

---

## 🛠️ 2. Update `vite.config.js` for GitHub Pages

> This is important so your app knows the correct URL path.

```javascript
// vite.config.js
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'

export default defineConfig({
  base: '/your-repo-name/',  // 👈 Replace with your repo name
  plugins: [react()],
})
```

Example:
If your repo is `portfolio-site`, then:

```javascript
base: '/portfolio-site/'
```

---

## 📝 3. Update `package.json` Scripts

Add these two scripts to `package.json`:

```json
"scripts": {
  "dev": "vite",
  "build": "vite build",
  "preview": "vite preview",
  "deploy": "gh-pages -d dist"
}
```

Explanation:

* `gh-pages -d dist` tells it to deploy the `dist/` folder.

---

## 🏗️ 4. Build the Project

```bash
npm run build
```

This generates the `dist/` folder.

---

## 🚀 5. Deploy to GitHub Pages

```bash
npm run deploy
```

---

## 🔧 6. Push Your Source Code to GitHub

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/YourUsername/your-repo-name.git
git push -u origin main
```

---

## 🌐 7. Enable GitHub Pages

1. Go to your GitHub repository.
2. Click **Settings** > **Pages**.
3. Set **Source** to **`gh-pages` branch**.
4. Click **Save**.

GitHub will give you a live URL:

```
https://YourUsername.github.io/your-repo-name/
```

---

## 🏁 Done!

Your React (Vite) app is now hosted on GitHub Pages 🎉

---

## ✅ Quick Summary

| Step    | Command / Action                       |
| ------- | -------------------------------------- |
| Install | `npm install gh-pages`                 |
| Config  | Edit `vite.config.js` + `package.json` |
| Build   | `npm run build`                        |
| Deploy  | `npm run deploy`                       |
| GitHub  | Push code + Enable Pages               |

---


