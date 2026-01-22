# Deployment Checklist - 10x Vibe Marketing

Generated: 2026-01-16
Tech Stack: Next.js
Hosting: Self-hosted

---

## Pre-Deployment

### Content Review
- [ ] All copy proofread for typos
- [ ] All links working (internal anchors)
- [ ] Placeholder content replaced (hero images, screenshots)
- [ ] Copyright year correct (2026)
- [ ] Contact information accurate
- [ ] Social media links updated
- [ ] CTA buttons point to correct booking link

### Technical Verification
- [ ] No build errors (`npm run build` succeeds)
- [ ] No JavaScript errors in console
- [ ] Images loading correctly
- [ ] Fonts loading correctly (Inter from Google Fonts)
- [ ] Favicon displays
- [ ] All components rendering

### Responsive Testing
- [ ] iPhone Safari (iOS)
- [ ] Android Chrome
- [ ] iPad (tablet breakpoint)
- [ ] Desktop Chrome (1920px, 1440px, 1024px)
- [ ] Desktop Firefox
- [ ] Desktop Safari (Mac)
- [ ] No horizontal scroll on any device
- [ ] Mobile navigation works correctly

### Accessibility
- [ ] Color contrast passes WCAG AA (4.5:1)
- [ ] All images have alt text
- [ ] Page navigable by keyboard
- [ ] Focus states visible
- [ ] Skip link works
- [ ] Heading hierarchy correct (h1 > h2 > h3)
- [ ] Form labels properly associated (if forms added)

### SEO Configuration
- [ ] Title tag set: "Master AI Marketing Skills in Hours, Not Months | 10x Vibe Marketing"
- [ ] Meta description set
- [ ] OG tags configured
- [ ] Twitter cards configured
- [ ] Canonical URL set (update to production URL)
- [ ] robots.txt created
- [ ] sitemap.xml created

### Analytics Setup
- [ ] Google Analytics ID added (replace G-XXXXXXXXXX)
- [ ] GA tracking verified in debug mode
- [ ] CTA click tracking working
- [ ] Scroll depth tracking working

### Performance
- [ ] Lighthouse score > 90
- [ ] Page loads in < 3 seconds
- [ ] Images optimized (WebP or compressed JPG/PNG)
- [ ] Fonts preloaded
- [ ] No render-blocking resources

---

## Deployment Steps

### Option A: Self-Hosted (Your Preference)

#### Using Node.js Server

1. **Build the project**
   ```bash
   cd projects/10x-vibe-marketing/build
   npm install
   npm run build
   ```

2. **Upload to your server**
   - Transfer the entire `build` folder via SFTP/SCP
   - Or use Git deployment

3. **Configure process manager (PM2)**
   ```bash
   npm install -g pm2
   pm2 start npm --name "10x-vibe" -- start
   pm2 save
   ```

4. **Configure reverse proxy (Nginx)**
   ```nginx
   server {
       listen 80;
       server_name yourdomain.com;

       location / {
           proxy_pass http://localhost:3000;
           proxy_http_version 1.1;
           proxy_set_header Upgrade $http_upgrade;
           proxy_set_header Connection 'upgrade';
           proxy_set_header Host $host;
           proxy_cache_bypass $http_upgrade;
       }
   }
   ```

5. **Set up SSL (Let's Encrypt)**
   ```bash
   sudo certbot --nginx -d yourdomain.com
   ```

#### Using Static Export (Alternative)

If you prefer static hosting, the `next.config.js` is already configured for static export:

1. **Build static files**
   ```bash
   npm run build
   ```

2. **The `out` folder contains static files**
   - Upload contents to any web server
   - Works with Apache, Nginx, or any static host

---

### Option B: Vercel (Easiest for Next.js)

1. Go to vercel.com and sign up/login
2. Connect your GitHub repository or drag the folder
3. Vercel auto-detects Next.js
4. Configure custom domain
5. Deploy

---

### Option C: Netlify

1. Go to netlify.com and sign up/login
2. Build locally: `npm run build`
3. Drag and drop the `out` folder (static export)
4. Configure custom domain
5. HTTPS automatically enabled

---

## Post-Deployment

### Immediate Checks
- [ ] Live URL loads correctly
- [ ] HTTPS working (no mixed content warnings)
- [ ] All navigation links work
- [ ] Mobile navigation functions
- [ ] CTA buttons clickable
- [ ] FAQ accordion works
- [ ] Scroll animations trigger
- [ ] Footer links work

### Analytics Verification
- [ ] Visit live site
- [ ] Check GA Real-Time reports to confirm tracking
- [ ] Click a CTA button and verify event logged
- [ ] Scroll to bottom and verify scroll depth tracked

### Social Sharing Test
- [ ] Paste URL in Twitter compose box (preview should appear)
- [ ] Paste URL in Facebook post (preview should appear)
- [ ] Paste URL in LinkedIn post (preview should appear)
- [ ] Verify OG image displays correctly

### Search Engine Setup
- [ ] Submit to Google Search Console
- [ ] Verify ownership
- [ ] Submit sitemap.xml
- [ ] Request indexing for main page

### Final Team Review
- [ ] Share URL with team for final review
- [ ] Collect any last-minute feedback
- [ ] Make minor adjustments if needed

---

## Launch Announcement

Once everything is verified:
- [ ] Announce to team
- [ ] Update all marketing materials with new URL
- [ ] Begin driving traffic
- [ ] Monitor analytics daily for first week
- [ ] Collect and document user feedback

---

## Important Files for Deployment

| File | Purpose |
|------|---------|
| `package.json` | Dependencies and scripts |
| `next.config.js` | Next.js configuration |
| `app/layout.js` | Root layout with SEO meta |
| `app/page.js` | Main page component |
| `app/globals.css` | Global styles |
| `components/*` | All UI components |
| `public/` | Static assets (add favicon, OG image here) |

---

## Assets to Create Before Launch

- [ ] **Favicon**: 32x32 PNG or SVG, place in `public/favicon.ico`
- [ ] **OG Image**: 1200x630 PNG, place in `public/og-image.png`
- [ ] **Hero Image/Illustration**: Add to hero section
- [ ] **Logo**: SVG format preferred, add to navigation
