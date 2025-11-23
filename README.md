# Truestory Preference Center

**[Live Preview](https://mylokaye.info/Dynamics-365-Preference-Center/)**

A modern, responsive email preference center built for Dynamics 365 Marketing integration.

## Technologies

| Technology | Purpose |
|------------|---------|
| [Tailwind CSS](https://tailwindcss.com/) | Utility-first styling via CDN |
| [Alpine.js](https://alpinejs.dev/) | Lightweight reactive data binding |
| [GSAP](https://greensock.com/gsap/) | Page load animations |
| [Google Fonts](https://fonts.google.com/) | Fraunces (headings) + DM Sans (body) |

## Project Structure

```
├── index.html          # Main preference center page
├── assets/
│   ├── logo.png        # Brand logo
│   ├── header.jpg      # Hero section image
│   ├── favicon.ico     # Browser favicon
│   ├── favicon.svg     # SVG favicon
│   ├── favicon-96x96.png
│   ├── apple-touch-icon.png
│   ├── site.webmanifest
│   ├── lock.icloud.png     # Trust section icon
│   ├── person.3.png        # Trust section icon
│   └── checkmark.shield.png # Trust section icon
└── README.md
```

## Customization

### Brand Colors

Edit the Tailwind config in `index.html` (lines 28-33):

```javascript
colors: {
  'brand': {
    300: '#a8c4bd',  // Light - borders, subtle text
    600: '#456d61',  // Medium - body text, links
    900: '#2c3f3a'   // Dark - headings, buttons
  }
}
```

### Fonts

Change fonts in the Tailwind config (lines 24-27):

```javascript
fontFamily: {
  'heading': ['Fraunces', 'serif'],
  'body': ['DM Sans', 'sans-serif']
}
```

Update the Google Fonts import in `<head>` to match.

### Marketing Preferences

Add or modify preference options in the form section (starting line 112). Each preference follows this structure:

```html
<div class="group">
  <label class="flex items-start gap-3 cursor-pointer">
    <input
      type="checkbox"
      value="your-preference-id"
      x-model="formData.preferences"
      class="w-5 h-5 mt-0.5 rounded-full border-2 border-brand-300 text-brand-600 focus:ring-brand-600 focus:ring-offset-0 cursor-pointer"
    >
    <div>
      <span class="text-brand-900 group-hover:text-brand-600 transition-colors font-medium">Preference Title</span>
      <p class="text-brand-600 text-sm mt-1">Description of what this preference controls.</p>
    </div>
  </label>
</div>
```

### Trust Section Cards

Modify the three trust cards in the `#trust` section (lines 207-229). Each card:

```html
<div class="bg-brand-600/30 rounded-2xl p-6 backdrop-blur-sm">
  <img src="assets/your-icon.png" alt="Description" class="w-10 h-10 mb-4 opacity-90">
  <p class="text-brand-300 text-sm leading-relaxed">
    Your trust message here.
  </p>
</div>
```

### Footer Links

Update footer links in the `<footer>` section (lines 235-260) with your actual URLs.

## Dynamics 365 Integration

To connect with Dynamics 365 Marketing:

1. Replace the `x-data` object with your contact's pre-filled data
2. Add form submission handler to POST preferences to your Dynamics 365 endpoint
3. Map checkbox `value` attributes to your Dynamics 365 consent fields

## Browser Support

- Modern browsers (Chrome, Firefox, Safari, Edge)
- Mobile responsive design
- Smooth scroll behavior

## License

MIT
