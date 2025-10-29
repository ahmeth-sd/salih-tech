# salih-tech

Personal portfolio website - Frontend Developer Resume/Portfolio

## Features

- Personal portfolio showcase
- Contact form integration with Netlify Forms
- Responsive design
- Modern HTML/CSS/JavaScript

## Deployment to Netlify

This project is configured for deployment on Netlify. Follow these steps to deploy:

### Option 1: Deploy via Netlify UI (Recommended)

1. Go to [Netlify](https://www.netlify.com/) and sign in with your GitHub account
2. Click "New site from Git"
3. Choose GitHub and select the `ahmeth-sd/salih-tech` repository
4. Configure build settings:
   - Build command: (leave empty)
   - Publish directory: `.` (root directory)
5. Click "Deploy site"

### Option 2: Deploy via Netlify CLI

1. Install Netlify CLI globally:
   ```bash
   npm install -g netlify-cli
   ```

2. Login to Netlify:
   ```bash
   netlify login
   ```

3. Initialize the site:
   ```bash
   netlify init
   ```

4. Deploy to production:
   ```bash
   netlify deploy --prod
   ```

## Contact Form

The contact form uses **Netlify Forms**, which:
- Automatically captures form submissions
- No backend/PHP required
- Submissions viewable in Netlify dashboard
- Includes spam protection with honeypot field

### Form Features:
- Name field (required)
- Email field (required)
- City field (optional)
- Message field (required)
- Spam protection (honeypot)

## Git Configuration

The repository is configured to use HTTPS for pushing:
```bash
git remote -v
# origin  https://github.com/ahmeth-sd/salih-tech (fetch)
# origin  https://github.com/ahmeth-sd/salih-tech (push)
```

To push changes:
```bash
git add .
git commit -m "Your commit message"
git push origin main
```

## Project Structure

```
salih-tech/
├── contactform/
│   ├── contactthanks.html    # Success page (converted from PHP)
│   ├── contactthanks.php     # Legacy PHP file (not used)
│   ├── contactengine.php     # Legacy PHP file (not used)
│   └── style.css             # Contact form styles
├── css/                      # Stylesheets
├── images/                   # Images and assets
├── js/                       # JavaScript files
├── upload/                   # Upload directory
├── index.html                # Main page with Netlify Forms
├── home-2.html               # Alternative home page
├── single-port.html          # Portfolio single page
├── netlify.toml              # Netlify configuration
├── .gitignore                # Git ignore file
└── README.md                 # This file
```

## Notes

- The PHP files (`contactengine.php`, `contactthanks.php`) are legacy files and no longer used
- The contact form now uses Netlify Forms instead of PHP
- The `netlify.toml` file contains configuration for Netlify deployment
