# Aarya Scan Center Website — Project Guide

## Overview

**Aarya Scan Center** is a static, single-page website for a diagnostic imaging and ultrasound clinic in Ankola, Karnataka, India. The site is fully responsive, bilingual (English/Kannada), and requires no backend, database, or backend server.

**Key tech:**
- HTML5, CSS3 (embedded in HTML)
- Vanilla JavaScript (embedded in HTML)
- Google Fonts (DM Sans, Manrope)
- SVG posters for marketing
- Schema.org structured data for SEO

**Deployment:** Open `index.html` in any modern browser.

---

## Project Structure

```
aarya_scan_center_website/
├── index.html              # Main website (single page, fully responsive)
├── convert.html            # Utility to batch-convert SVG posters to PNG
├── posters/                # SVG marketing posters (6 designs)
├── README.txt              # Quick setup guide
├── CLAUDE.md               # This file
└── .claude/
    └── settings.local.json # Claude Code local settings
```

### Key Files

- **index.html** — The entire website. Contains HTML structure, embedded CSS, embedded JavaScript, and Schema.org markup. ~73 KB.
  - Sections: Header/hero, services, about, process, contact, footer
  - Language toggle (English/Kannada) saved to localStorage
  - Floating WhatsApp contact button
  - Fully responsive (mobile, tablet, desktop)

- **convert.html** — Standalone utility page. Allows bulk SVG-to-PNG conversion of marketing posters with a 1080×1080 oatmeal background.

- **posters/** — Six SVG files for social media and marketing:
  - `aarya-full-services-editorial.svg`
  - `aarya-full-services-dark-cards.svg`
  - `aarya-full-services-lavender-bands.svg`
  - `aarya-full-services-split-directory.svg`
  - `aarya-full-services-numbered-menu.svg`
  - `aarya-whatsapp-services-poster.svg`

---

## Design System & Styling

### Color Palette
- **Pine green:** `#214b3b` (primary, theme color)
- **Oatmeal:** `#f3eee3` (background, light accents)
- **Soft lilac:** `#d5c9e8` (secondary, highlights)
- **Black:** `#1a1a1a` (text)
- **Gray:** `#666666` (secondary text)

### Typography
- **Display/headers:** Manrope (400, 500, 600, 700, 800)
- **Body text:** DM Sans (400, 500, 600)
- Both fonts loaded from Google Fonts (preconnect for performance)

### Responsive Breakpoints
- Mobile: up to 480px
- Tablet: 481px–768px
- Desktop: 769px+

Implemented with `@media (max-width: ...)` queries in embedded CSS.

---

## Content & Before Publishing

Before deploying to production, verify and update these items (see README.txt for details):

1. **Contact Information**
   - Phone: Replace `+91 9480727922` throughout (currently appears in multiple places)
   - WhatsApp link: Update `https://wa.me/919480727922` with the correct number
   - Address: Verify "Shree Manjunath Complex, Opposite Ankola Bus Stand, Ankola, Karnataka 581314"
   - Working hours: Confirm in Schema.org markup (Mon–Sat 08:00–17:00, Sun 09:00–12:00)

2. **Services & Descriptions**
   - Review all medical procedure descriptions with a qualified clinician
   - Confirm accuracy of: General USG, Breast Ultrasound, Pregnancy Scan, Doppler Studies
   - Check FAQ answers for medical accuracy

3. **Compliance & Legal**
   - Verify all local healthcare advertising requirements are met
   - Ensure medical claims in descriptions comply with local regulations
   - Confirm local registrations and licenses are in place

4. **Branding**
   - Replace or update the Aarya logo mark if needed
   - Review hero section imagery/messaging

---

## Language Toggle (English/Kannada)

The website has a language toggle button in the header. Language preference is saved to `localStorage` under key `language`.

**Implementation:**
- All text content has both English and Kannada versions defined in a data structure
- JavaScript detects the toggle click and updates the DOM with the appropriate language
- Browser language preference is checked on first load; falls back to English if not `kn`

**To add/update translated text:**
1. Find the language data object in the `<script>` section of index.html
2. Add or update entries with both English (`en`) and Kannada (`kn`) strings
3. Ensure the JavaScript selector and DOM updates reference the correct elements

---

## Schema.org Structured Data

The page includes three structured data blocks (in `<script type="application/ld+json">`):

1. **MedicalBusiness:** Clinic name, address, phone, hours, geo coordinates
2. **ItemList of MedicalProcedures:** Services offered (USG, Breast, Pregnancy, Doppler)
3. **FAQPage:** Frequently asked questions for rich snippet display in search results

**Importance:** Keep this data in sync with actual clinic info. Search engines use this to display clinic details in search results and Google Maps.

---

## WhatsApp Integration

The floating WhatsApp button links to `https://wa.me/919480727922`. Update the phone number when deploying.

**To modify:**
1. Search for `https://wa.me/` in index.html
2. Replace the phone number with the correct one (format: country code + number without spaces)

---

## JavaScript Conventions

- All JavaScript is embedded in `<script>` tags within index.html
- No build tools, bundlers, or external JS files
- Use vanilla DOM APIs (no frameworks like React or jQuery)
- Store user preferences (language) in `localStorage`
- Smooth scroll on anchor links with `scroll-behavior: smooth` in CSS

**Key functions to know:**
- Language toggle: Swaps all text from English to Kannada and saves preference
- WhatsApp button: Direct link, no JS needed
- Form submission: Handled as needed (currently uses placeholder contact info)

---

## Testing & QA

### Manual Testing Checklist

1. **Responsive Design**
   - [ ] Open in browser on mobile (320px–480px), tablet (768px), and desktop (1920px+)
   - [ ] Verify layout, spacing, and text readability on all breakpoints
   - [ ] Test navigation and buttons on touch devices

2. **Language Toggle**
   - [ ] Click language toggle button, verify all text switches to Kannada
   - [ ] Click again, verify it switches back to English
   - [ ] Refresh page, verify saved language preference persists

3. **Navigation & Links**
   - [ ] Test all internal anchor links (Services, About, Process, Contact)
   - [ ] Verify smooth scroll behavior
   - [ ] Test WhatsApp button, confirm it opens WhatsApp (or fallback on mobile)
   - [ ] Test any external links (e.g., Google Maps, social media)

4. **Content & Compliance**
   - [ ] Verify all contact information is correct (phone, address, hours)
   - [ ] Confirm services and descriptions match clinic offerings
   - [ ] Check all medical information for accuracy with clinician

5. **SEO & Metadata**
   - [ ] Verify page title and meta description in browser tab
   - [ ] Check Open Graph tags (og:title, og:description) for social sharing
   - [ ] Inspect structured data with Google's Rich Results Test
   - [ ] Verify schema.org data is valid and complete

6. **Performance**
   - [ ] Load index.html in browser, check for console errors
   - [ ] Verify Google Fonts load correctly (check Network tab in DevTools)
   - [ ] Test on slow network (DevTools Network throttling)

### Browser Compatibility
- Modern browsers (Chrome, Firefox, Safari, Edge) released in the last 2 years
- Mobile browsers: iOS Safari, Chrome Mobile
- No IE11 support required

---

## Editing & Common Tasks

### Add a Service
1. Open index.html
2. Find the services section (search for "Services")
3. Add a new service block following the existing pattern
4. Update the language data object with English and Kannada text

### Update Contact Information
1. Search for the old phone number or address in index.html
2. Replace with new information in:
   - Navigation/header
   - Contact section
   - Schema.org MedicalBusiness markup
   - WhatsApp links
3. Update `working-hours` in Schema.org if hours change

### Convert SVG Posters to PNG
1. Open `convert.html` in a browser
2. Click "Download all PNG posters"
3. Each SVG file is rasterized to 1080×1080 PNG with an oatmeal background
4. Files download automatically (adjust canvas dimensions in convert.html if needed)

### Update Colors
1. Find the color values in embedded CSS (search for hex codes like `#214b3b`)
2. Replace with new values throughout
3. Update schema.org theme-color if changing primary brand color
4. Test design in light and dark modes if applicable

---

## Deployment

**Static hosting only** — no backend, database, or build step required.

### Hosting Options
- GitHub Pages (free, simple)
- Netlify (free tier, easy deploys)
- Vercel (free tier, fast global CDN)
- Any static web host (S3, Cloudflare Pages, etc.)

### Pre-deployment Checklist
1. Update all contact information per "Content & Before Publishing" above
2. Verify compliance and local requirements
3. Run manual testing checklist
4. Review SEO (structured data, meta tags) with Rich Results Test
5. Test on target devices and browsers

### DNS & Domain
- Update DNS records to point to your hosting provider
- Ensure HTTPS/SSL is enabled (most hosts provide this free)

---

## Troubleshooting

### Language Toggle Not Working
- Check browser console for JavaScript errors
- Verify localStorage is enabled in browser
- Confirm the language data object exists in the script

### Content Not Displaying
- Clear browser cache (Ctrl+Shift+Delete or Cmd+Shift+Delete)
- Check browser console for errors
- Verify all HTML/CSS syntax is correct

### Fonts Not Loading
- Check Network tab in DevTools to verify Google Fonts URLs load
- Ensure preconnect links are in the `<head>`
- Test on different network conditions (DevTools throttling)

### SVG to PNG Conversion Failing
- Open browser console in convert.html to see error messages
- Verify SVG files are in the `posters/` directory
- Confirm browser supports Canvas API (all modern browsers do)

---

## Performance Tips

1. **Images & Assets**
   - Keep SVG posters optimized (use SVGO or similar)
   - Consider lazy-loading for images if added

2. **Fonts**
   - Use `preconnect` and `preload` for Google Fonts (already done)
   - Specify font weights needed to reduce file size

3. **CSS**
   - Keep embedded CSS minimal and organized
   - Use CSS variables for color values (optional refactor)

4. **JavaScript**
   - Keep inline scripts minimal and efficient
   - Avoid excessive DOM manipulation in loops

---

## Future Enhancements (Optional)

- Add online appointment booking (requires backend)
- Integrate with WhatsApp Business API for automated responses
- Add patient testimonials or reviews section
- Implement dark mode toggle
- Add image gallery for services
- Connect to a CMS for easier content updates
- Add multi-language support beyond Kannada/English

---

## Contact & Support

For questions or issues:
- **Project:** Aarya Scan Center Website
- **Type:** Static HTML single-page site
- **Maintenance:** Update content in index.html as needed; no database or backend to maintain
