# Motiv8 Consulting — GoHighLevel Import Guide

## Overview

This guide explains how to import and host the Motiv8 Consulting website on GoHighLevel (GHL).
The site was built as clean HTML/CSS/JS and is designed for easy GHL integration.

---

## Method 1: GHL Website Builder (Recommended)

### Step 1 — Create the Website in GHL
1. Log in to your GHL sub-account
2. Go to **Sites → Websites → + New Website**
3. Name it "Motiv8 Consulting"

### Step 2 — For Each Page
For each page (Home, About, Services, Contact, Blog):
1. Click **+ Add Page**
2. Choose **Blank** template
3. Drag in a **Custom HTML/CSS** element (or use the Code Block element)
4. Paste the full HTML from the corresponding `.html` file
5. The CSS is referenced via `assets/css/style.css` — you'll need to either:
   - **Option A:** Host the CSS file in GHL's Media Library and update the `<link>` path
   - **Option B:** Inline the CSS directly in a `<style>` block in each page's `<head>`

### Step 3 — Upload Assets
1. Go to **Media Library** in GHL
2. Upload your logo: `assets/images/logo.png`
3. Update all `src="assets/images/logo.png"` references in the HTML to the GHL Media Library URL

---

## Method 2: GHL Custom Code (Fastest)

GHL supports full custom HTML pages:

1. Go to **Sites → Websites**
2. For each page, click **Edit** → **Page Settings** → **Header/Body Tracking Code**
3. In the **Body** section, paste the full page HTML

OR use the **Raw HTML** element in the page builder to embed the full page layout.

---

## Integration Checklist

### Calendly Booking Widget
Replace the placeholder in `contact.html` with:
```html
<div class="calendly-inline-widget"
     data-url="https://calendly.com/YOUR_USERNAME/30min"
     style="min-width:320px;height:400px;">
</div>
<script src="https://assets.calendly.com/assets/external/widget.js" async></script>
```

### GHL Live Chat Widget
1. Go to **Sites → Chat Widget** in GHL
2. Copy the embed code
3. Replace the `.chat-widget` div at the bottom of each page with your GHL chat embed code

### GHL Contact Form
Replace the `<form id="contact-form">` in `contact.html` with your GHL form embed:
1. Go to **Sites → Forms** in GHL
2. Create a form matching the fields in the contact page
3. Click **Embed** and paste the iframe or code into the page

### GHL Payments
For service payment links:
1. Go to **Payments → Products** in GHL
2. Create products for each service
3. Add payment links/buttons to the relevant service pages

### Social Media Feeds (Live)
To connect real social feeds:
- **Instagram:** Use GHL's Social Planner or embed via Instagram Basic Display API
- **TikTok:** Embed TikTok posts using their oEmbed API
- **LinkedIn:** Use LinkedIn's sharing widgets or a third-party feed tool like Elfsight

---

## Domain Setup
1. Go to **Sites → Websites → Settings**
2. Add your custom domain: `motiv8.consulting`
3. Update your DNS records as instructed by GHL

---

## Font & Style Notes

| Element | Font | Weight |
|---------|------|--------|
| Headings | Space Grotesk | 700/600 |
| Body Text | Inter | 400/500 |
| Labels/Tags | Rajdhani | 600 |

Fonts are loaded from Google Fonts CDN. Ensure the `<head>` import is present:
```html
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=Inter:wght@300;400;500;600;700&family=Rajdhani:wght@400;500;600;700&display=swap" rel="stylesheet">
```

---

## Color Reference

| Name | Hex |
|------|-----|
| Primary Navy | `#0C2D48` |
| Accent Cyan | `#00B4D8` |
| Bright Cyan | `#00D4FF` |
| Dark Background | `#06101A` |
| Surface Cards | `#0D1F30` |
| Body Text | `#E2EFF5` |
| Muted Text | `#7AACBF` |

---

## Files Included

```
motiv8-website/
├── index.html          ← Home page
├── about.html          ← About page (incl. Statement of Exclusivity)
├── services.html       ← Services page (AI Consulting, AI Agency, Advisory)
├── contact.html        ← Contact page (form + Calendly placeholder)
├── blog.html           ← Blog page (featured post + 6 posts + newsletter)
├── assets/
│   ├── css/
│   │   └── style.css   ← Global stylesheet (all pages)
│   ├── js/
│   │   └── main.js     ← Animations, nav, forms, counters
│   └── images/
│       └── logo.png    ← Place your logo here
└── GHL-IMPORT-GUIDE.md ← This file
```

---

## Support

If you need help with the GHL import, contact: hello@motiv8.consulting
