# NYS Design System Test Drive for IES District Worker Portal

This Chrome extension lets you preview how the NYS Design System looks and behaves on the IES District Worker Portal without changing the actual application. It's meant for stakeholder review and design validation.

- **See NYS styling applied** to a legacy application
- **Toggle design updates on/off** to compare before and after
- **Review proposed improvements** like updated spacing, typography, and accessibility features

---

## Installing

1. **Download the extension**
   - Get the ZIP file or cloned folder from your team
   - If it's a ZIP, right-click and select “Extract All” to unzip it

2. **Open Chrome Extensions**
   - Go to `chrome://extensions` in your Chrome browser

3. **Enable Developer Mode**
   - In the top-right corner, turn on **Developer mode**

4. **Load the extension**
   - Click **Load unpacked**
   - Select the folder that contains `manifest.json` (not just the top-level ZIP folder)

5. **(Optional) Pin the extension**
   - Click the puzzle piece icon in your Chrome toolbar
   - Click the pin icon next to "NYSDS Override"

---

## Activating

1. Open the **IES District Worker Portal** in Chrome  
2. Click the **NYSDS Override** icon in the toolbar  
3. Use the **toggle switch** to turn the NYS styling on or off  
4. Refresh the page if you don’t see changes right away

---

## Notes

- You’re not changing the real application—just previewing updates on your device
- This helps you give early feedback on how the NYS Design System could be applied
- The extension adds updated fonts, spacing, colors, and some accessibility features

---

## For Developers

Once stakeholders approve the design, here's how to bring these changes into the legacy application:

### CSS Styles

The styles in `override.css` are production-ready. You can copy them directly into your application's stylesheet. They use [NYSDS design tokens](https://designsystem.ny.gov/foundations/tokens/) (CSS custom properties) for colors, typography, and spacing.

**To use the tokens**, you can add this to your application's `<head>`:

```html
<link rel="stylesheet" href="https://unpkg.com/@nysds/styles@latest/dist/nysds.min.css">
```

Or install via npm:

```bash
npm install @nysds/styles
```

### Fonts

The extension uses NYSDS fonts (Proxima Nova, D Sari, Oswald). To use them in your application:

1. **Request access** to the [nysds-fonts repo](https://github.com/ITS-HCD/nysds-fonts) (private, requires NYS authorization)
2. Copy the font files to your project
3. Include `nysds-fonts.css` or add the `@font-face` declarations to your stylesheet

### DOM/HTML Changes

Review the comments in `override.js` — they document proposed HTML improvements (accessibility fixes, semantic markup, ARIA attributes). These are meant as a guide for what to implement in your source code, not to be used directly.

### Resources

- [NYSDS Tokens Reference](https://designsystem.ny.gov/foundations/tokens/)
- [NYSDS Components](https://designsystem.ny.gov/components/)
- [@nysds/styles on npm](https://www.npmjs.com/package/@nysds/styles)
