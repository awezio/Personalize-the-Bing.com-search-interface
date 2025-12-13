## Personalize the Bing.com Search Interface

This project provides a simple CSS customization for `bing.com` to **beautify the search page header** by replacing the `header#b_header` background image and tuning how it scales/crops.

### Preview

![Result preview](image/README/1765598185596.png)

## Features

- **Replace the Bing header background image** with your own picture
- **Responsive fitting** via `background-size` and `background-position`
- **Works via browser user-style tools** (recommended: Stylus)

## Quick Start

### Option A (Recommended): Stylus

- **Install** the Stylus extension (Chrome / Edge / Firefox)
- **Create a new style**
- **Apply to**: `bing.com`
- **Paste** the CSS below and save

### Option B: Tampermonkey

If you prefer JavaScript-based injection, you can also apply the CSS using Tampermonkey (not included as a script in this repo).

## CSS (Header Background Replacement)

Paste and edit the URL:

```css
/* Target the Bing search header */
header#b_header {
  /* 1) Your custom image URL */
  background-image: url("{your_picture_url}") !important;

  /* 2) Image fitting (core) */
  /* cover: fills the area, may crop edges (best for backgrounds) */
  /* contain: fully visible, may leave empty space */
  background-size: cover !important;

  /* 3) Prevent tiling */
  background-repeat: no-repeat !important;

  /* 4) Center the image */
  background-position: center center !important;
}
```

### Tuning Tips

- **Try `background-size`**: `cover` (default), `contain`, or a percentage like `100% auto`
- **Try `background-position`**: `center top`, `center 30%`, etc.

## Choosing & Preparing an Image

### Recommended aspect ratio

The `header#b_header` area is very wide and short. In Microsoft Edge devtools, it’s roughly:

| Element             | Size (example)              |
| ------------------- | --------------------------- |
| `header#b_header` | ~1103.64 × 144.79 (≈ 8:1) |

Because of this, images with an **~8:1** aspect ratio tend to look best.

### Example workflow (AI expand → crop → finish in an editor)

- **Source image example**:
  - Original:![img](https://raw.githubusercontent.com/awezio/Personalize-the-Bing.com-search-interface/main/images/233416-1711121656e5bd.jpg)
  - Credit: Pinterest link (see [Credits](#credits))
- **Step 1: Expand to a wider canvas** (optional)
  - Many image AIs work better if you generate a wider ratio like **10:1**, then crop down to **8:1**
  - Example prompt:

```text
Extend the uploaded image to an aspect ratio of 10:1, keep consistent style, and maintain realistic lighting.
```

- **Step 2: Crop to ~8:1**
  - Generated sample: ![img](https://raw.githubusercontent.com/awezio/Personalize-the-Bing.com-search-interface/main/images/Gemini_Generated_Image.png)
  - Cropped sample: ![img](https://raw.githubusercontent.com/awezio/Personalize-the-Bing.com-search-interface/main/images/Gemini_Generated_Image_cutted.jpeg)
- **Step 3: Final polish in an editor** (Photoshop / PowerPoint / etc.)
  - Typical tweaks: sharpening, filters, subtle vignette/edge blur
  - Example process images:
    - ![img](https://raw.githubusercontent.com/awezio/Personalize-the-Bing.com-search-interface/main/images/processed.jpg)
    - ![img](https://raw.githubusercontent.com/awezio/Personalize-the-Bing.com-search-interface/main/images/processed2.jpg)
    - ![img](https://raw.githubusercontent.com/awezio/Personalize-the-Bing.com-search-interface/main/images/processed3.jpg)
    - ![img](https://raw.githubusercontent.com/awezio/Personalize-the-Bing.com-search-interface/main/images/processed4.jpg)

## FAQ

- **Will this affect other sites?** Sure—if you scope the style to `bing.com`, it only affects Bing.However, you can choose other webs and do the right picture adaptation
- **Why does my image look cropped?**
  `background-size: cover` is designed to fill the header and may crop edges. Try `contain` or adjust `background-position`.

## Credits

- **Wallpaper source**: [Pinterest pin](https://www.pinterest.com/pin/588775351318617923/)

## License

Licensed under the **MIT License**. See `LICENSE`.
