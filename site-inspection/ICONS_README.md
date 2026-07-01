# PWA Icons and Assets

## Required Icons for PWA Installation

To complete the PWA setup, add these icon files to `frontend/public/`:

### Required Icons:

1. **icon-192.png** (192x192 pixels)
   - Used for app icon on home screen
   - PNG format, transparent or white background

2. **icon-512.png** (512x512 pixels)
   - Used for splash screen
   - PNG format, transparent or white background

3. **icon.svg** (optional)
   - Scalable favicon
   - Used in browser tab

### Quick Icon Generation

You can use any of these methods:

#### Option 1: Use an Icon Generator
- Visit: https://favicon.io/favicon-generator/
- Create icon with "🏗️" emoji or your logo
- Download and rename to icon-192.png and icon-512.png

#### Option 2: Create Simple Icon with Text
```bash
# Install ImageMagick
brew install imagemagick  # Mac
# or
sudo apt-get install imagemagick  # Linux

# Generate 192x192 icon
convert -size 192x192 xc:#007AFF \
  -gravity center \
  -pointsize 100 \
  -fill white \
  -annotate +0+0 "🏗️" \
  icon-192.png

# Generate 512x512 icon
convert -size 512x512 xc:#007AFF \
  -gravity center \
  -pointsize 300 \
  -fill white \
  -annotate +0+0 "🏗️" \
  icon-512.png
```

#### Option 3: Use Placeholder
Until you create custom icons, you can use a simple colored square:

```bash
# 192x192 blue square
convert -size 192x192 xc:#007AFF icon-192.png

# 512x512 blue square
convert -size 512x512 xc:#007AFF icon-512.png
```

### Icon Design Tips

For best results:
- **Simple design** - Icons are small, keep it simple
- **High contrast** - Ensure visibility on any background
- **Square format** - Will be rounded by iOS
- **No text** - Except for abbreviations (2-3 letters max)
- **Recognizable** - Should be identifiable at small sizes

### Example Icon Ideas

- Construction helmet emoji: 🏗️
- Clipboard emoji: 📋
- Camera emoji: 📷
- Initial letters: "SI" (Site Inspection)
- Company logo
- Building/construction symbol

### Placement

Place all icons in:
```
frontend/public/
├── icon-192.png
├── icon-512.png
├── icon.svg (optional)
└── manifest.json
```

### Testing Icons

1. **Local testing:**
   ```bash
   npm run dev -- --host
   ```

2. **Open in iPad Safari:**
   ```
   http://YOUR_IP:5173
   ```

3. **Check manifest:**
   - Safari Dev Tools → Application → Manifest
   - Should show all icons

4. **Test installation:**
   - Share → Add to Home Screen
   - Check if icon appears correctly

### Current Status

⚠️ **Icons not yet created** - PWA will work but use default browser icon

✅ **Manifest configured** - Ready for icons when added

🎯 **Next step:** Create or generate icons using one of the methods above

---

## Alternative: Skip Icons for Now

The app will still work without custom icons! Safari will use:
- First letter of the site name
- Screenshot of the page
- Default browser icon

You can add custom icons later without affecting functionality.
