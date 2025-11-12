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

3. Make changes to files in the `public/` directory

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