# Mike Stay - Software Website

Personal website showcasing free, ad-free software utilities for Windows.

## Project Structure

```
├── index.html          # Home page
├── menu.html           # Shared navigation menu (injected via JS)
├── styles.css          # Global stylesheet
├── donate.html         # Donation page
├── license.html        # Software license
├── privacy.html        # Privacy policy
├── tech-support.html   # Support request form
├── clockalarm/         # ClockAlarm app pages
│   ├── clockalarm-about.html
│   ├── clockalarm-guide.html
│   └── clockalarm-gallery.html
├── sysbar/             # SysBar app pages
│   ├── sysbar-about.html
│   ├── sysbar-guide.html
│   └── sysbar-gallery.html
├── icons/              # UI icons
├── images/             # Screenshots and assets
└── package.json        # Local development setup
```

## Local Development

### Prerequisites

- Node.js (any recent version)
- npm (comes with Node.js)

### Setup

1. Install dependencies:
```bash
npm install
```

2. Start the local development server:
```bash
npm run dev
```

This will:
- Start an HTTP server on port 8080
- Automatically open your browser to `http://localhost:8080`
- Serve the files with proper MIME types

3. To start without auto-opening browser:
```bash
npm start
```

### Tech Support Form (Local Testing)

The tech support form uses Web3Forms API. To test it locally:

1. Get a free access key from [web3forms.com](https://web3forms.com/)
2. Create a local `env-config.js` file (copy from the template below)
3. Uncomment and set your key in `env-config.js`:
```javascript
window.WEB3FORMS_ACCESS_KEY = 'your_actual_key_here';
```

**Note**: `env-config.js` is in `.gitignore` and will not be committed to the repository.

### GitHub Pages Deployment

For production deployment on GitHub Pages:

1. The site is deployed from the root directory
2. Set the Web3Forms API key as a GitHub repository secret
3. Use GitHub Actions to inject the key at build time (if needed)
4. The form will use the fallback value if no key is configured

## File Path Conventions

- **Root-level HTML files**: Use relative paths without `../` (e.g., `styles.css`, `index.html`)
- **Subdirectory HTML files** (sysbar/, clockalarm/): Use `../` to reference parent directory (e.g., `../styles.css`, `../index.html`)

## Making Changes

### CSS Changes
- Edit `styles.css` directly
- No build process required
- Changes reflect immediately on browser refresh

### Adding New Pages
1. Create HTML file in appropriate directory
2. Follow existing template structure (sidebar, page-wrapper, main, footer)
3. Include the menu injection script at the bottom
4. Add navigation link in `menu.html` if needed

### Images
- Place screenshots in `images/` subdirectory
- Use lowercase filenames for cross-platform compatibility
- Reference with correct relative paths

## Deployment

### GitHub Pages

The site is configured to deploy via GitHub Pages. Push changes to the repository and they will be automatically deployed.

### Manual Deployment

If deploying manually:
1. Build/minify assets if desired (optional)
2. Upload all files to your web server
3. Ensure server has proper MIME types for HTML, CSS, JS

## Security Notes

- API keys are never committed to the repository
- Use environment variables or repository secrets for sensitive data
- The `.gitignore` file prevents accidental commits of sensitive files

## Browser Support

- Modern browsers (Chrome, Firefox, Edge, Safari)
- Responsive design works on mobile and desktop
- Dark mode support via CSS variables

## License

Content and code are subject to the custom MIT-based license. See `license.html` for details.
