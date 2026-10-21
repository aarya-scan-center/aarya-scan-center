===============================================================================
  AARYA SCAN CENTER — STATIC WEBSITE
===============================================================================

Project: Single-page responsive website for a diagnostic imaging & ultrasound
         clinic in Ankola, Karnataka, India

Tech Stack: HTML5 | CSS3 | Vanilla JavaScript | Google Fonts | No backend


QUICK START
===============================================================================

1. Open index.html in any modern browser
   - Internet required only for Google Fonts; site itself is completely static
   - No backend server, database, or installation needed

2. Explore features:
   - Bilingual toggle (English/Kannada) in header
   - Floating WhatsApp contact button
   - Fully responsive design (mobile, tablet, desktop)
   - Complete clinic information and services


PROJECT STRUCTURE
===============================================================================

index.html              Main website (73 KB, fully self-contained)
  ├─ Complete HTML structure, embedded CSS, embedded JavaScript
  ├─ Sections: Header/hero, services, about, process, contact, footer
  └─ Schema.org markup for SEO

convert.html           Utility to batch-convert SVG posters to PNG (1080×1080)

posters/               6 SVG marketing designs for social media
  ├─ aarya-full-services-editorial.svg
  ├─ aarya-full-services-dark-cards.svg
  ├─ aarya-full-services-lavender-bands.svg
  ├─ aarya-full-services-split-directory.svg
  ├─ aarya-full-services-numbered-menu.svg
  └─ aarya-whatsapp-services-poster.svg

CLAUDE.md              Detailed developer guide (edit/enhance/deploy)
README.txt             This file


FEATURES
===============================================================================

✓ Oatmeal (#f3eee3), pine green (#214b3b), and soft lilac (#d5c9e8) palette
✓ Custom Aarya logo mark and premium hero section
✓ Fully responsive: mobile (320px+), tablet (768px+), desktop (1920px+)
✓ English / Kannada language toggle with browser storage persistence
✓ Services, about, process, and contact sections
✓ Floating WhatsApp contact shortcut
✓ Complete structured data (Schema.org) for search engine visibility
✓ Social media meta tags (Open Graph, Twitter Card)
✓ Accessible HTML5 markup with semantic structure


BEFORE PUBLISHING TO PRODUCTION
===============================================================================

CRITICAL: Update all contact information and verify compliance

Contact Information:
  [ ] Replace phone number (+91 9480727922) in all locations:
      - Header/navigation
      - Contact section
      - WhatsApp link (format: https://wa.me/919480727922)
      - Schema.org MedicalBusiness data
      - Footer

  [ ] Update business address:
      - Current: "Shree Manjunath Complex, Opposite Ankola Bus Stand,
                  Ankola, Karnataka 581314"
      - Verify street address, locality, region, postal code
      - Update coordinates if location differs

  [ ] Confirm working hours:
      - Monday–Saturday: 08:00–17:00
      - Sunday: 09:00–12:00
      - Update in Schema.org openingHoursSpecification if needed

Content & Medical Accuracy:
  [ ] Review all service descriptions with qualified clinician/operator
      - General Ultrasound (USG)
      - Breast Ultrasound
      - Pregnancy Scan
      - Doppler Studies

  [ ] Confirm FAQ answers for medical accuracy

  [ ] Verify all medical claims comply with local advertising regulations

Compliance & Legal:
  [ ] Verify local healthcare registrations and licenses are current
  [ ] Confirm all healthcare advertising requirements are met
  [ ] Check local regulatory body guidelines (e.g., medical council)
  [ ] Ensure HIPAA/privacy policy compliance if applicable

Branding:
  [ ] Review Aarya logo mark (replace if needed)
  [ ] Verify hero section image/message aligns with brand


EDITING & CUSTOMIZATION
===============================================================================

Edit Contact Information:
  1. Open index.html in a text editor
  2. Search for "+91 9480727922" or the address
  3. Replace in all occurrences (typically 5–7 places)
  4. Include Schema.org MedicalBusiness section updates

Add or Update Services:
  1. Find "Services" section in index.html
  2. Add new service block following existing pattern
  3. Update language data object with English and Kannada text

Change Colors:
  1. Search for hex codes in CSS: #214b3b, #f3eee3, #d5c9e8
  2. Replace with new values throughout
  3. Update schema.org theme-color meta tag if primary color changes

Language Toggle:
  - Works automatically; saved to browser localStorage as "language"
  - To add translations: edit language data object in JavaScript section

Convert SVG Posters to PNG:
  1. Open convert.html in browser
  2. Click "Download all PNG posters"
  3. Each SVG becomes 1080×1080 PNG with oatmeal background
  4. To customize canvas size/background: edit convert.html


DEPLOYMENT OPTIONS
===============================================================================

This is a static website — no build tools, backend, or database required.

Recommended Free Hosting:
  • GitHub Pages        — Simple, free, integrates with git
  • Netlify             — Fast, easy deploys, free tier
  • Vercel              — Excellent performance, free tier
  • Cloudflare Pages    — Global CDN, free tier
  • AWS S3 + CloudFront — More advanced, low cost

Basic Deployment Steps:
  1. Ensure all contact info and compliance checks are complete
  2. Upload all files (index.html, convert.html, posters/) to host
  3. Configure domain DNS to point to hosting provider
  4. Enable HTTPS/SSL (all modern hosts provide this free)
  5. Test on mobile and desktop browsers


TESTING & QUALITY ASSURANCE
===============================================================================

Before launching, verify:

  [ ] Responsive design works on mobile (320px), tablet (768px), desktop
  [ ] Language toggle switches between English and Kannada correctly
  [ ] Preference persists after page refresh
  [ ] All links work (internal anchors, WhatsApp button, external links)
  [ ] Contact information displays correctly everywhere
  [ ] Google Fonts load (check Network tab in browser DevTools)
  [ ] No JavaScript errors in browser console
  [ ] Page performs well on slow network (throttle in DevTools)
  [ ] Schema.org structured data is valid (test with Google Rich Results)
  [ ] Social media preview looks correct (Open Graph meta tags)
  [ ] All medical content is accurate and compliant


BROWSER COMPATIBILITY
===============================================================================

Supported:
  • Chrome/Edge (latest 2 versions)
  • Firefox (latest 2 versions)
  • Safari (latest 2 versions)
  • Mobile browsers (iOS Safari, Chrome Mobile)

Not supported:
  • Internet Explorer (use modern browser alternative)


TROUBLESHOOTING
===============================================================================

Fonts not loading?
  → Check internet connection (Google Fonts requires online access)
  → Verify Google Fonts URLs in <head> section of index.html
  → Check browser console for CORS or loading errors

Language toggle not working?
  → Clear browser cache (Ctrl+Shift+Delete / Cmd+Shift+Delete)
  → Check browser console for JavaScript errors
  → Verify localStorage is enabled in browser settings

Content not displaying?
  → Clear browser cache
  → Try different browser
  → Check HTML/CSS syntax for typos

SVG-to-PNG conversion failing?
  → Verify all SVG files are in posters/ directory
  → Check browser console for error messages
  → Ensure browser supports Canvas API (all modern browsers do)

How to view in developer mode?
  → Right-click → Inspect (or press F12)
  → Check Console tab for errors
  → Use Network tab to monitor resource loading


ADDITIONAL RESOURCES
===============================================================================

For detailed development guidance, see CLAUDE.md:
  • Project architecture and conventions
  • Design system documentation
  • Schema.org structured data details
  • JavaScript implementation notes
  • Complete testing checklist
  • Performance optimization tips
  • Future enhancement ideas


IMPORTANT NOTES
===============================================================================

• This is a static website only (no backend)
• Does NOT include online appointment booking
• Does NOT include database or admin panel
• Does NOT collect or store patient data
• No email forms or automated messaging (contact via WhatsApp only)

To add advanced features (appointments, forms, messaging):
  → Requires backend server, database, and additional development
  → Contact a web developer for custom integration


SUPPORT & MAINTENANCE
===============================================================================

Regular maintenance tasks:
  • Keep contact information current
  • Review and update service descriptions as needed
  • Monitor for broken links or outdated content
  • Test on new browser versions
  • Update compliance information as regulations change

For questions or customization:
  → Review CLAUDE.md for detailed documentation
  → Consult with a qualified web developer for complex changes


===============================================================================
Last updated: October 2026
Aarya Scan Center — Clear Care. Confident Answers.
===============================================================================
