# PixelForge Tech - Quick Reference Guide

## Project Structure

```
pixelforge/
├── README.md                        GitHub documentation
├── index.html                       Main page (224 KB)
├── css/
│   └── styles.css                   Main page styles (40 KB)
├── js/
│   └── script.js                    Main page functionality (32 KB)
├── events/
│   ├── index.html                   Events page (300 KB)
│   ├── styles.css                   Events styles (24 KB)
│   └── script.js                    Events functionality (8 KB)
└── partners/
    ├── index.html                   Partners page (296 KB)
    ├── styles.css                   Partners styles (20 KB)
    └── script.js                    Partners functionality (4 KB)
```

---

## HTML File References

### Main Page (Root)
**File:** `index.html`

```html
<!-- CSS Reference -->
<link rel="stylesheet" href="css/styles.css">

<!-- Script Reference -->
<script src="js/script.js"></script>
```

**Navigation Links:**
- Home: `index.html` or `/`
- Events: `events/`
- Partners: `partners/`

### Events Page
**File:** `events/index.html`

```html
<!-- CSS Reference -->
<link rel="stylesheet" href="styles.css">

<!-- Script Reference -->
<script src="script.js"></script>
```

**Navigation Links:**
- Home: `../` or `../index.html`
- Events: Current page
- Partners: `../partners/`

### Partners Page
**File:** `partners/index.html`

```html
<!-- CSS Reference -->
<link rel="stylesheet" href="styles.css">

<!-- Script Reference -->
<script src="script.js"></script>
```

**Navigation Links:**
- Home: `../` or `../index.html`
- Events: `../events/`
- Partners: Current page

---

## File Dependencies

### index.html depends on:
- `css/styles.css` - All styling for main page
- `js/script.js` - All interactivity for main page
- Google Fonts API (external)

### events/index.html depends on:
- `events/styles.css` - All styling for events page
- `events/script.js` - All interactivity for events page
- Google Fonts API (external)

### partners/index.html depends on:
- `partners/styles.css` - All styling for partners page
- `partners/script.js` - All interactivity for partners page
- Google Fonts API (external)

---

## Running the Project

### Method 1: Python HTTP Server
```bash
cd pixelforge
python -m http.server 8000
```
Then visit: `http://localhost:8000`

### Method 2: Node.js HTTP Server
```bash
cd pixelforge
npx http-server
```
Then visit: `http://localhost:8080`

### Method 3: PHP Server
```bash
cd pixelforge
php -S localhost:8000
```
Then visit: `http://localhost:8000`

### Method 4: VS Code Live Server
1. Install "Live Server" extension in VS Code
2. Open the project folder in VS Code
3. Right-click on `index.html`
4. Select "Open with Live Server"
5. Browser opens automatically

---

## File Access Patterns

### From index.html (root)
```
css/styles.css          ✓ Correct
js/script.js            ✓ Correct
events/index.html       ✓ Can navigate
partners/index.html     ✓ Can navigate
```

### From events/index.html
```
styles.css              ✓ Correct (same directory)
script.js               ✓ Correct (same directory)
../index.html           ✓ Can navigate to home
../partners/            ✓ Can navigate to partners
```

### From partners/index.html
```
styles.css              ✓ Correct (same directory)
script.js               ✓ Correct (same directory)
../index.html           ✓ Can navigate to home
../events/              ✓ Can navigate to events
```

---

## Common Issues & Solutions

### Issue: "CSS file not found" in console
**Solution:** 
- Ensure you're running through a server (not file://)
- Check the file path in <link> tag
- Verify the CSS file exists in the directory

### Issue: "JavaScript not working"
**Solution:**
- Ensure <script> tag path is correct
- Check browser console for errors
- Verify script.js exists in the directory
- Make sure script runs after page load

### Issue: "Navigation links broken"
**Solution:**
- Use relative paths (../events/, ./styles.css)
- Don't use absolute paths (/events/index.html)
- Check that all directories and files exist

### Issue: "Styles not applying"
**Solution:**
- Hard refresh browser (Ctrl+Shift+R or Cmd+Shift+R)
- Check CSS file size in Network tab
- Verify CSS syntax is valid
- Check for typos in selectors

---

## CSS File Contents

### css/styles.css (40 KB)
Contains:
- Global styles and resets
- Cyberpunk color scheme
- Responsive grid system
- Animation keyframes
- Typography styles
- Component styles (buttons, cards, etc.)
- Dark/light theme variables
- Media queries for mobile

### events/styles.css (24 KB)
Contains:
- Events page specific styles
- Calendar widget styling
- Event card designs
- Form styling for registrations
- Table styling for event lists
- Event filter UI styles

### partners/styles.css (20 KB)
Contains:
- Partners page specific styles
- Partner card layouts
- Logo grid styling
- Testimonial sections
- Partnership tier display
- Integration showcase styles

---

## JavaScript File Contents

### js/script.js (32 KB)
Contains:
- Theme toggle functionality (dark/light)
- Typewriter animation effect
- Interactive tools (password generator, text tools)
- Form handling and validation
- Navigation menu interactivity
- Mobile hamburger menu
- Smooth scroll behavior
- Event listeners for components

### events/script.js (8 KB)
Contains:
- Event filtering and search
- Calendar functionality
- Registration form handling
- Date/time formatting
- Event category filtering
- RSVP functionality

### partners/script.js (4 KB)
Contains:
- Partner filter functionality
- Logo carousel/slider
- Testimonial rotation
- Partnership tier selection
- Inquiry form handling

---

## Deployment Checklist

Before deploying to production:

- [ ] Test all pages on local server
- [ ] Check console for JavaScript errors
- [ ] Verify all CSS loads correctly
- [ ] Test responsive design on mobile
- [ ] Test dark/light theme toggle
- [ ] Test all interactive features
- [ ] Check all navigation links work
- [ ] Verify images load (if any)
- [ ] Test on different browsers
- [ ] Minify CSS and JS for production
- [ ] Set up cache headers
- [ ] Enable GZIP compression
- [ ] Configure HTTPS/SSL

---

## Performance Tips

1. **Minify CSS and JS**
   ```bash
   # Using cssnano and terser
   npm install -g cssnano-cli terser
   cssnano css/styles.css -o css/styles.min.css
   terser js/script.js -o js/script.min.js
   ```

2. **Use CSS variables for theming**
   - Define colors in CSS variables
   - Switch themes with one variable change

3. **Lazy load images**
   - Use loading="lazy" attribute
   - Implement intersection observer for custom loading

4. **Browser caching**
   - Set cache-control headers on server
   - Version static files with hash

5. **Code splitting**
   - Separate page-specific CSS and JS
   - Load only needed resources per page

---

## Browser Compatibility

| Browser | CSS | JavaScript | Status |
|---------|-----|------------|--------|
| Chrome 90+ | Full | Full | Fully supported |
| Firefox 88+ | Full | Full | Fully supported |
| Safari 14+ | Full | Full | Fully supported |
| Edge 90+ | Full | Full | Fully supported |
| Mobile Safari 14+ | Full | Full | Fully supported |
| Chrome Mobile 90+ | Full | Full | Fully supported |

---

## Best Practices

### When Adding New Pages
1. Create new directory: `newpage/`
2. Add: `newpage/index.html`
3. Add: `newpage/styles.css`
4. Add: `newpage/script.js`
5. Link CSS in HTML: `<link rel="stylesheet" href="styles.css">`
6. Link JS in HTML: `<script src="script.js"></script>`
7. Use relative paths for navigation

### When Modifying Styles
1. Edit the appropriate CSS file based on the page
2. Keep page-specific styles in their directory
3. Consider extracting common styles to shared file
4. Test responsive breakpoints
5. Use CSS variables for consistency

### When Adding JavaScript
1. Add code to the appropriate script.js file
2. Use event delegation for dynamic content
3. Keep code modular and commented
4. Test in console for errors
5. Avoid global variables

---

## Useful Commands

```bash
# Start Python server
python -m http.server 8000

# Start Node server
npx http-server

# View file structure
find . -type f -name "*.html" -o -name "*.css" -o -name "*.js"

# Count lines of code
wc -l css/*.css js/*.js events/*.css events/*.js partners/*.css partners/*.js

# Check file sizes
du -sh css/* js/* events/* partners/*
```

---

## Support Resources

- **GitHub Issues:** [pixelforge-tech/pixelforge](https://github.com/pixelforge-tech/pixelforge/issues)
- **Community Chat:** [WhatsApp](https://pixelforge.tech/whatsapp)
- **Forums:** [Telegram](https://pixelforge.tech/telegram)
- **Documentation:** [docs.pixelforge.tech](https://docs.pixelforge.tech)

---

**Last Updated:** June 1, 2026  
**Version:** 1.1.0  
**Status:** Production Ready
