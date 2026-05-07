# Bella Vista Weddings - QR Link Hub Documentation

This document explains how the mobile "Review & Social" landing page (LittleLink fork) is structured and how you can update it in the future.

## Overview
This is a static HTML, mobile-first one-page application designed for patrons to scan via QR code. It provides high-contrast, premium, brand-cohesive links to Google Reviews, Social Media, and the Isabella AI Concierge.

## Editing the Hub

Everything you need to edit is located inside a single file: `index.html`.

### 1. How to Update Links
If you need to change where a button points (for instance, adding the official TikTok link or updating the Google Review link), open `index.html` and scroll down to the `.button-stack` section (around line 175).

Find the `href=""` attribute on the corresponding button and replace the URL:

```html
<!-- TikTok Example -->
<a class="button button-tiktok-custom" href="YOUR_TIKTOK_LINK_HERE" target="_blank" rel="noopener" role="button">
  <img class="icon" aria-hidden="true" src="images/icons/tiktok.svg" alt="TikTok Logo">Follow us on Tik Tok
</a>
```

### 2. How to Update the Google Review Link
Currently, the Google Review button uses a fallback Google Maps search link. Once you have access to your Google Business Profile dashboard:
1. Copy the short URL (e.g., `g.page/r/YOUR_ID/review`).
2. Replace the existing Maps link inside the `button-google-review` anchor tag.

### 3. Understanding the Colors & Styles
All custom styling has been consolidated into the `<style>` block at the top of the `index.html` file to make maintenance easy. 

The color palette uses CSS Variables for consistency:
- `--champagne-gold`: `#C9A84C` (Used for Google Review button & Isabella's text)
- `--obsidian`: `#0D0D12` (Used for text and page borders)
- `--cream`: `#FAF8F5` (The page background)
- `--burgundy`: `#6A2B36` (Pulled from the logo; used for Isabella's button)
- `--dark-green`: `#2d5a27` (Used for Instagram)
- `Facebook Blue`: `#1877F2` (Hardcoded for the Facebook button)

To change a button's color, simply find its class (e.g., `.button-isabella`) in the `<style>` block and update the `--button-background` and `--button-text` variables.

## Typography
The project uses Google Fonts:
- **Cormorant Garamond**: Elegant serif used for headings, paragraph text, and buttons.
- **Inter**: Clean sans-serif used as a fallback and for the footer.
