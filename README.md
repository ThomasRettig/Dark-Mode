**Original link**: https://ar.al/2021/08/24/implementing-dark-mode-in-a-handful-of-lines-of-css-with-css-filters/

---

# Dark mode (Pure CSS)
What you see here is the source code taken directly from Aral Balkan’s excellent just-add-water dark mode CSS solution.

## Design considerations
Although this might be an efficient solution for large websites, it’s a bit hacky in my opinion, because the `filter` property can lead to some visual artefacts caused by the browser rendering engine. Additionally, there are greater nuances in crafting a visually realistic dark mode appearance, such as depth and contrast. In addition, dark mode is activated only when ```@media (prefers-color-scheme: dark)``` is on. In other words, it’s system-level, so folks can't toggle between dark mode and light mode.

## Source code
```css
/*
Source code by Aral Balkan -> https://ar.al/2021/08/24/implementing-dark-mode-in-a-handful-of-lines-of-css-with-css-filters/
*/

@media (prefers-color-scheme: dark) {
  /* Invert all elements on the body while attempting to not alter the hue substantially. */
  body {
    filter: invert(100%) hue-rotate(180deg);
  }

  /* Workarounds and optical adjustments. */

  /* Firefox workaround: Set the background colour for the html
     element separately because, unlike other browsers, Firefox
     doesn’t apply the filter to the root element’s background. */
  html {
    background-color: #111;
  }

  /* Do not invert media (revert the invert). */
  img, video, iframe {
    filter: invert(100%) hue-rotate(180deg);
  }

  /* Improve contrast on icons. */
  .icon {
    filter: invert(15%) hue-rotate(180deg);
  }

  /* Re-enable code block backgrounds. */
  pre {
    filter: invert(6%);
  }

  /* Improve contrast on list item markers. */
  li::marker {
    color: #666;
  }
}
```
