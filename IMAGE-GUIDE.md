# How to Add Images to Your Landing Page

## Setup: Create Images Folder

First, create a folder structure:
```
claudetest/
├── journey-of-your-life-landing.html
└── images/
    ├── hero-bg.jpg
    ├── testimonial-sarah.jpg
    ├── testimonial-michael.jpg
    ├── testimonial-elena.jpg
    ├── ebook-cover.jpg
    └── logo.png
```

---

## Where to Add Images

### 1. HERO BACKGROUND IMAGE

**Find this in your HTML (around line 1000):**
```html
<section class="hero">
```

**Add a background image by finding the `.hero` CSS style (around line 135) and modify:**
```css
.hero {
    position: relative;
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    overflow: hidden;
    background: linear-gradient(rgba(44, 24, 16, 0.7), rgba(44, 24, 16, 0.7)),
                url('images/hero-bg.jpg');  /* ADD THIS LINE */
    background-size: cover;                  /* ADD THIS LINE */
    background-position: center;             /* ADD THIS LINE */
}
```

---

### 2. LOGO (Add to Hero Section)

**Add before the compass in the hero section:**
```html
<div class="hero-content">
    <!-- ADD LOGO HERE -->
    <img src="images/logo.png" alt="The Journey Of Your Life Logo" style="width: 150px; margin-bottom: 2rem;">

    <svg class="compass-icon" viewBox="0 0 100 100">
    ...
```

---

### 3. TESTIMONIAL PHOTOS

**Find the testimonial section (around line 1180) and replace the avatar divs:**

**BEFORE:**
```html
<div class="author-avatar">S</div>
```

**AFTER:**
```html
<img src="images/testimonial-sarah.jpg" alt="Sarah Mitchell" class="author-avatar" style="width: 60px; height: 60px; border-radius: 50%; border: 3px solid #DAA520; object-fit: cover;">
```

Do this for all 3 testimonials with their respective images.

---

### 4. EBOOK COVER IMAGE

**Find the free ebook section (around line 1110) and replace the book-icon:**

**BEFORE:**
```html
<div class="book-cover">
    <div class="free-badge">FREE</div>
    <div class="book-icon">📖</div>
    <h3>The Life Story Discovery Guide</h3>
```

**AFTER:**
```html
<div class="book-cover" style="padding: 0; overflow: hidden;">
    <div class="free-badge">FREE</div>
    <img src="images/ebook-cover.jpg" alt="Life Story Discovery Guide" style="width: 100%; height: 100%; object-fit: cover;">
</div>
```

OR keep the styled book cover and just change the icon to an image:
```html
<img src="images/book-icon.png" alt="Book" style="width: 80px; height: 80px; margin-bottom: 1rem;">
```

---

### 5. ADD PHOTO SECTION (Optional)

You can add an image gallery section. Add this after Event Details:

```html
<!-- PHOTO GALLERY SECTION -->
<section class="photo-gallery fade-in" style="padding: 5rem 2rem; background: var(--color-parchment);">
    <div class="container">
        <h2 class="section-title">Moments from Past Adventures</h2>

        <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 2rem; margin-top: 3rem;">
            <img src="images/event-1.jpg" alt="Event moment 1" style="width: 100%; height: 300px; object-fit: cover; border-radius: 10px; border: 3px solid var(--color-bronze); box-shadow: 0 10px 30px rgba(0,0,0,0.2);">

            <img src="images/event-2.jpg" alt="Event moment 2" style="width: 100%; height: 300px; object-fit: cover; border-radius: 10px; border: 3px solid var(--color-bronze); box-shadow: 0 10px 30px rgba(0,0,0,0.2);">

            <img src="images/event-3.jpg" alt="Event moment 3" style="width: 100%; height: 300px; object-fit: cover; border-radius: 10px; border: 3px solid var(--color-bronze); box-shadow: 0 10px 30px rgba(0,0,0,0.2);">
        </div>
    </div>
</section>
```

---

## Method 2: Use Online Images (URLs)

Instead of local files, you can use images from:
- **Your website** (if you have one)
- **Image hosting** (Imgur, Cloudinary, etc.)
- **Cloud storage** (Dropbox, Google Drive with public links)

**Example:**
```html
<img src="https://your-website.com/images/photo.jpg" alt="Description">
```

**For hero background:**
```css
.hero {
    background: url('https://your-website.com/images/hero-bg.jpg');
}
```

---

## Method 3: Optimize Your Images

Before adding images, optimize them:

1. **Resize** - Hero images: 1920x1080px, Thumbnails: 600x400px
2. **Compress** - Use tools like:
   - TinyPNG.com
   - Squoosh.app
   - ImageOptim (Mac)
3. **Format** - Use JPG for photos, PNG for logos/graphics

---

## Quick Test

To test if images work:

1. Save an image as `test.jpg` in the `images/` folder
2. Add to your HTML:
   ```html
   <img src="images/test.jpg" alt="Test" style="width: 300px;">
   ```
3. Open the HTML file in your browser
4. If you see the image, it works!

---

## Troubleshooting

**Image doesn't show?**
- Check the file path is correct
- Make sure image file exists in the folder
- Check spelling and file extension (.jpg vs .JPG)
- Try right-click → Inspect to see the error

**Image path examples:**
```html
<!-- Correct -->
<img src="images/photo.jpg">

<!-- Wrong -->
<img src="/images/photo.jpg">  <!-- Extra slash -->
<img src="photo.jpg">           <!-- Missing folder -->
```

---

## Need Help?

Just tell me which images you want to add and where, and I'll update the HTML file for you!
