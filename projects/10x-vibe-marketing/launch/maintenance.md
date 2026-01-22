# Maintenance Guide - 10x Vibe Marketing

Generated: 2026-01-16

---

## Quick Reference

### Project Structure
```
build/
├── app/
│   ├── layout.js       # Root layout, SEO meta tags
│   ├── page.js         # Main page composition
│   └── globals.css     # Global styles, Tailwind
├── components/
│   ├── Navigation.jsx  # Header navigation
│   ├── Hero.jsx        # Hero section
│   ├── Problem.jsx     # Problem/agitation section
│   ├── Solution.jsx    # Solution introduction
│   ├── Benefits.jsx    # Benefits cards
│   ├── HowItWorks.jsx  # 3-step process
│   ├── Features.jsx    # Feature cards
│   ├── SocialProof.jsx # Certification section
│   ├── FAQ.jsx         # Accordion FAQ
│   ├── FinalCTA.jsx    # Final call to action
│   └── Footer.jsx      # Footer
├── public/             # Static assets
├── package.json        # Dependencies
├── tailwind.config.js  # Tailwind configuration
└── next.config.js      # Next.js configuration
```

---

## Common Updates

### Changing Text/Copy

**In components:**
1. Open the relevant component file (e.g., `components/Hero.jsx`)
2. Find the text you want to change
3. Edit directly in the JSX
4. Save the file
5. Run `npm run build` to rebuild
6. Re-deploy to server

**Example - Changing the headline:**
```jsx
// In components/Hero.jsx, find:
<h1 className="mb-6">
  Master{' '}
  <span className="gradient-text">AI Marketing Skills</span>{' '}
  in Hours, Not Months
</h1>

// Change to your new headline
```

---

### Changing Colors

Colors are defined in two places:

**1. Tailwind Config (`tailwind.config.js`):**
```javascript
colors: {
  primary: {
    DEFAULT: '#6366F1',  // Change this
    light: '#818CF8',
    dark: '#4F46E5',
  },
  // ...
}
```

**2. CSS Variables (`app/globals.css`):**
```css
:root {
  --color-primary: #6366F1;  /* Change this */
  --color-primary-light: #818CF8;
  --color-primary-dark: #4F46E5;
}
```

After changing, rebuild and redeploy.

---

### Changing Fonts

1. Go to fonts.google.com
2. Select new fonts
3. Update the `<link>` in `app/layout.js`:
   ```jsx
   <link href="https://fonts.googleapis.com/css2?family=YourFont:wght@400;500;600;700&display=swap" rel="stylesheet" />
   ```
4. Update `tailwind.config.js`:
   ```javascript
   fontFamily: {
     sans: ['YourFont', '-apple-system', ...],
   }
   ```
5. Rebuild and redeploy

---

### Adding/Changing Images

1. **Optimize the image** using tinypng.com or squoosh.app
2. **Add to `public/` folder**
3. **Reference in component:**
   ```jsx
   <img
     src="/your-image.png"
     alt="Descriptive alt text"
     width={600}
     height={400}
   />
   ```
4. Always include `alt` text for accessibility
5. Rebuild and redeploy

---

### Updating CTA Link

The main CTA button links are in several components:

1. **Hero.jsx** - Primary hero CTA
2. **HowItWorks.jsx** - Mid-page CTA
3. **FinalCTA.jsx** - Final CTA section
4. **Navigation.jsx** - Nav CTA button

Search for `href="#cta"` or `href="#"` and replace with your booking link:
```jsx
<a href="https://your-booking-link.com" className="btn-primary">
  Book Your Free Strategy Call
</a>
```

---

### Adding/Editing FAQ Questions

Open `components/FAQ.jsx` and find the `faqs` array:

```javascript
const faqs = [
  {
    question: 'Your new question?',
    answer: 'Your answer here...',
  },
  // Add more questions...
]
```

---

### Adding Testimonials (Future Enhancement)

To add testimonials:

1. Create a new component `components/Testimonials.jsx`
2. Add testimonial data
3. Import and add to `app/page.js` in the appropriate position
4. Style using existing card patterns

---

## Monthly Maintenance

- [ ] Check all links still work
- [ ] Review analytics data
  - Page views and sessions
  - Bounce rate
  - CTA click rate
  - Scroll depth
- [ ] Update any outdated information
- [ ] Check page speed (pagespeed.web.dev)
- [ ] Review and respond to any feedback
- [ ] Check for any console errors

---

## Quarterly Maintenance

- [ ] Review overall conversion performance
- [ ] A/B test headline variations (if needed)
- [ ] Update testimonials/social proof
- [ ] Review competitive landscape
- [ ] Consider copy refreshes

---

## Annual Maintenance

- [ ] Update copyright year in Footer.jsx
- [ ] Refresh all testimonials if possible
- [ ] Review and update any statistics
- [ ] Consider design refresh
- [ ] Update dependencies:
  ```bash
  npm update
  npm audit fix
  ```
- [ ] Test all functionality after updates

---

## Troubleshooting

### Page not loading
1. Check hosting status
2. Verify domain DNS settings
3. Check SSL certificate validity
4. Review server logs for errors

### Styles not applying
1. Clear browser cache (Ctrl+Shift+R)
2. Check for CSS errors in console
3. Verify Tailwind is building correctly
4. Check for typos in class names

### Images not showing
1. Verify file path is correct (`/image.png` for public folder)
2. Check file exists in public folder
3. Ensure proper file extension
4. Check for case sensitivity (Linux servers)

### JavaScript not working
1. Check browser console for errors
2. Verify build completed successfully
3. Check for syntax errors in components
4. Ensure `'use client'` directive on interactive components

### Build errors
1. Run `npm install` to ensure all dependencies
2. Check for import errors
3. Verify all components exist
4. Check for TypeScript/JSX syntax errors

---

## Performance Optimization Tips

1. **Images**
   - Use WebP format when possible
   - Compress images before uploading
   - Use appropriate dimensions (don't scale down large images)
   - Add `loading="lazy"` for below-fold images

2. **Fonts**
   - Only load weights you need (400, 500, 600, 700)
   - Use `font-display: swap`

3. **JavaScript**
   - Keep animations simple
   - Avoid heavy libraries
   - Use native features when possible

---

## Support Resources

- **Next.js Docs**: nextjs.org/docs
- **Tailwind CSS Docs**: tailwindcss.com/docs
- **Google Analytics**: analytics.google.com
- **PageSpeed Insights**: pagespeed.web.dev
- **Search Console**: search.google.com/search-console

---

## Backup Recommendations

- Keep the original source files in version control (Git)
- Before major changes, create a backup:
  ```bash
  cp -r build build-backup-YYYY-MM-DD
  ```
- Document all changes made
