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

2. Make changes to files in the `public/` directory

3. Commit and push changes:
   ```bash
   git add .
   git commit -m "Your commit message"
   git push origin main
   ```

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