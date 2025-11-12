# Solve Now - Company Website

This repository contains the source code for the Solve Now company website, a static website hosted on Firebase Hosting.

## 🚀 Live Website

- **Default Firebase URL:** https://solve-e0820.web.app
- **Custom Domain:** https://solve-now.net (pending DNS propagation)

## 📁 Project Structure

```
solve-now/
├── public/                 # Static files served by Firebase Hosting
│   └── index.html         # Main homepage
├── .github/workflows/     # GitHub Actions for CI/CD
│   ├── firebase-hosting-merge.yml
│   └── firebase-hosting-pull-request.yml
├── .firebaserc            # Firebase project configuration
├── firebase.json          # Firebase hosting configuration
└── README.md              # This file
```

## 🛠️ Technologies Used

- **Frontend:** HTML, CSS, JavaScript
- **Hosting:** Firebase Hosting
- **CI/CD:** GitHub Actions
- **Version Control:** Git

## 🚀 Deployment

The website is automatically deployed to Firebase Hosting when changes are pushed to the `main` branch via GitHub Actions.

### Development Workflow

- **Development Branch:** `dev` - Use this branch for all development work
- **Production Branch:** `main` - Only production-ready code should be merged here
- **Automatic Deployment:** Pushes to `main` trigger automatic deployment to Firebase Hosting

### Manual Deployment

If needed, you can deploy manually:

```bash
# Install Firebase CLI if not already installed
npm install -g firebase-tools

# Login to Firebase
firebase login

# Deploy
firebase deploy
```

## ✉️ Contact Form Setup

The homepage contact form writes submissions into **Cloud Firestore** (`contacts` collection). Before deploying, replace the placeholder config inside `public/index.html` with your project's values:

1. In the Firebase console open **Project settings → Your apps → Firebase SDK snippet → Config** and copy the object.
2. Paste it into the `const firebaseConfig = { ... }` block at the bottom of `public/index.html`.
3. Enable Firestore (production mode is fine) and update the rules so anonymous writes are allowed only for the `contacts` collection while you iterate, e.g.:
   ```
   service cloud.firestore {
     match /databases/{database}/documents {
       match /contacts/{document} {
         allow create: if true;
         allow read: if false;
       }
     }
   }
   ```
4. After testing, check **Firestore → Data → contacts** to confirm new documents are created.

> Firebase web configs are public by design, but you can still lock down the API key to `solve-now.net` in the Google Cloud Console for extra safety.

## 👀 Local Preview

Preview the site locally before merging to `main`:

```bash
firebase login                             # once per machine
firebase emulators:start --only hosting    # or: firebase serve --only hosting
```

The emulator serves the files in `public/` so you can review layout changes. The form still talks to your configured Firebase backend, so double-check your config values before submitting test entries.

## 🎨 Tech Stack Logos

### Quick Download Summary

| Technology | Best Source | Format | Link |
| --- | --- | --- | --- |
| Vertex AI | Wikimedia / LobeHub | SVG / PNG | https://commons.wikimedia.org |
| n8n | LobeHub | SVG / PNG / WebP | https://lobehub.com/icons/n8n |
| CrewAI | LobeHub / GitHub | SVG / PNG / WebP | https://lobehub.com/icons/crewai |
| OpenAI | OpenAI Brand Kit | SVG / PNG | https://openai.com/brand |
| Azure AI | Microsoft Learn | SVG | https://learn.microsoft.com/en-us/azure/templates |
| Google Cloud (GCP) | Google Cloud | SVG / PNG | https://cloud.google.com/icons |
| A2A Protocol | Google AI | SVG | https://ai.google |

> **Fastest single source:** [LobeHub](https://lobehub.com/) – search once and grab consistent SVG/PNG/WebP assets for every stack logo you need.

### Ways to Use the Logos

1. **Embed from a CDN (zero downloads)** – point `img` tags straight to a trusted CDN such as `logo.svgcdn.com` or `cdn.simpleicons.org`.
2. **Download locally** – keep SVGs in `public/images/tech-stack/` for full control.
3. **Upload to Firebase Storage** – host the SVGs behind Firebase's CDN and reuse the same URLs across landing pages.

Sample markup once you have URLs handy:

```html
<div class="tech-stack">
  <div class="tech-card">
    <img src="https://logo.svgcdn.com/logos/google-vertex-ai.svg" alt="Vertex AI" width="80">
    <p>Google Vertex AI</p>
  </div>
  <div class="tech-card">
    <img src="https://logo.svgcdn.com/simple-icons/n8n.svg" alt="n8n" width="80">
    <p>n8n</p>
  </div>
</div>
```

Pick whichever hosting approach matches your workflow now and swap the URLs inline in `public/index.html` when you're ready to ship the branded badges.

> **Current implementation:** `public/index.html` now reads the PNG logos stored under `public/img/`. Replace any of those files with your preferred artwork to update the badges while keeping all assets self-hosted.

## 🏗️ Development

1. Clone the repository:
   ```bash
   git clone https://github.com/dubaisolve/solve-now.git
   cd solve-now
   ```

2. Switch to development branch:
   ```bash
   git checkout dev
   ```

3. Make changes to files in the `public/` directory (the homepage lives at `public/index.html`)

4. Commit changes locally:
   ```bash
   git add .
   git commit -m "Your commit message"
   ```

5. When ready to deploy, merge to main:
   ```bash
   git checkout main
   git merge dev
   git push origin main  # This triggers automatic deployment
   ```

### Branch Strategy

- **`dev` branch:** Primary development branch - commits here don't trigger deployments
- **`main` branch:** Production branch - only push/merge here when ready to deploy

## 📝 Custom Domain Setup

The custom domain `solve-now.net` has been configured with the following DNS records:

- **A Record:** `solve-now.net` → `199.36.158.100`
- **TXT Record:** `solve-now.net` → `"hosting-site=solve-e0820"`

DNS propagation may take up to 48 hours.

## 📞 Contact

For questions or contributions, please contact the repository owner.

---

*This project is maintained by dubaisolve*</content>
<parameter name="filePath">/Users/niko/Documents/solve/README.md
