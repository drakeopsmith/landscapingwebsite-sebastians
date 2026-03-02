# Go High Level (GHL) — Import Setup Guide

## 📋 Prerequisites

- Active Go High Level account (any plan with website/funnel builder)
- A Website or Funnel already created in GHL
- The export files from this folder

---

## 📦 Export Files Overview

| File | Purpose | Where to paste in GHL |
|---|---|---|
| `ghl-head-code.html` | Fonts, icons, CSS | Page Settings → Tracking → Head |
| `ghl-body-code.html` | JavaScript initialization | Page Settings → Tracking → Body |
| `ghl-custom-element.html` | Main HTML content | Custom Code element on page |
| `ghl-css-overrides.css` | CSS overrides (if needed) | Page Settings → Custom CSS |
| `full-page.html` | Reference — open locally | N/A (for comparison only) |

---

## 🚀 Step-by-Step Import

### Step 1: Create a Blank Page

1. In GHL, go to **Sites → Websites** (or **Funnels**)
2. Select your website/funnel
3. Click **"+ Add New Page"**
4. Choose **"Blank"** template
5. Name it: `Verdant Scapes | Premium Landscaping in Santa Barbara & Montecito`

### Step 2: Configure Page Settings

1. Click the **⚙️ gear icon** (top right) to open Page Settings
2. Under **General**:
   - Set the **page title**: `Verdant Scapes | Premium Landscaping in Santa Barbara & Montecito`
   - Set the **meta description** from the source site
   - Set the **URL path/slug**

### Step 3: Add Head Tracking Code

1. In Page Settings, go to **"Tracking Code"** tab
2. Find **"Head Tracking Code"** section
3. Open `ghl-head-code.html` in a text editor
4. **Copy the entire contents** and paste into the Head Tracking Code field
5. Click **Save**

> **What this does:** Loads Google Fonts, the Lucide icon library, and all CSS styles.

### Step 4: Add Body Tracking Code

1. Still in **"Tracking Code"** tab
2. Find **"Body Tracking Code"** section
3. Open `ghl-body-code.html` in a text editor
4. **Copy the entire contents** and paste into the Body Tracking Code field
5. Click **Save**

> **What this does:** Initializes JavaScript — scroll effects, animations, FAQ toggles, dynamic card rendering, mobile menu, parallax, and Lucide icon rendering.

### Step 5: Add Main Content

1. **Close** the Settings panel
2. In the page builder, you should see a blank page
3. Click **"+ Add Section"** → choose **Full Width** (no padding, no container)
4. Inside the section, click **"+ Add Element"**
5. Find **"Custom Code"** (under Advanced or Custom elements)
6. Drag it into the section
7. Open `ghl-custom-element.html` in a text editor
8. **Copy the entire contents** and paste into the Custom Code element
9. Click **Save**

> **What this does:** Adds all the website HTML — navbar, hero, sections, footer, everything.

### Step 6: GHL Section Settings

1. Click on the section containing the Custom Code element
2. In Section Settings:
   - Set **padding** to `0` on all sides
   - Set **margin** to `0` on all sides
   - Set **Background** to transparent or match `#fcfaf7`
   - Set **Full Width** to enabled
3. Click **Save**

### Step 7: Add GHL Form (Lead Capture)

1. The exported code has a placeholder where the original form was
2. **Below the Custom Code element**, add a new row
3. Drag a **"Form"** element into it
4. Configure form fields:
   - Full Name (text, required)
   - Phone Number (phone, required) 
   - Email Address (email, optional)
   - Service Needed (dropdown)
   - Project Description (textarea)
5. Set the form's styling to match the site design:
   - Background: white
   - Border radius: 3rem / 48px
   - Padding: 2.5rem / 40px
   - Font: Inter
6. Configure form actions (pipeline, automation, etc.)
7. Click **Save**

> **Why native form?** GHL native forms integrate directly with contacts, automations, and pipelines — no workaround needed.


### Step 8: Preview & Verify

1. Click **"Preview"** in the GHL builder (top right)
2. Open `full-page.html` locally in a browser
3. Compare both side by side:
   - [ ] All sections render correctly
   - [ ] Fonts load (Playfair Display, Inter)
   - [ ] Icons render (Lucide icons should appear)
   - [ ] Scroll animations work (cards fade up on scroll)
   - [ ] Hero parallax effect works
   - [ ] Navbar changes on scroll (transparent → solid)
   - [ ] Mobile menu opens/closes
   - [ ] FAQ accordion opens/closes
   - [ ] Hover effects work (cards, buttons)
   - [ ] Sticky mobile bar appears on scroll (mobile only)
   - [ ] All links work (smooth scroll to sections)
   - [ ] All images load
4. Test on mobile viewport sizes

### Step 9: Publish

1. If everything looks correct, click **"Save"** in the builder
2. Go to page settings and set the page to **Published**
3. Visit the live URL and verify once more

---

## ⚠️ Troubleshooting

| Issue | Solution |
|---|---|
| Fonts not loading | Check that `ghl-head-code.html` was pasted in **Head** (not Body) tracking code |
| Icons not showing | Verify Lucide script tag is in head code. Try adding `<script>setTimeout(function(){lucide.createIcons()},1000)</script>` to body code |
| Layout looks broken | Make sure the GHL section has **0 padding** and **full width** enabled |
| Animations not working | Verify body code was pasted correctly. Check browser console for JS errors |
| Images not loading | Ensure all image URLs are absolute (start with `https://`). Check GHL doesn't block external images |
| Mobile menu not working | The mobile menu JavaScript should be in the body tracking code. Verify no JS errors |
| Form not submitting | If using native mode, add a GHL form widget. If using custom mode, verify hidden fields exist |
| Navbar not sticking | `position: fixed` may conflict with GHL's layout. Try adding `position: fixed !important` to navbar CSS |

---

## 📝 Notes

- The exported code is fully self-contained — it doesn't depend on any build tools
- All external resources (fonts, icons, images) are loaded from CDNs
- The CSS is scoped to avoid conflicts with GHL's built-in styles
- SEO meta tags should be set through GHL's page settings, not in the custom code
