# Dark mode (Pure CSS)
Exact source code taken from Aral Balkan's excellent guide on how to implement dark mode via CSS.

I have some mixed feelings. Although this might be a quick solution for large websites, there are greater nuances in crafting a visually realistic dark mode appearance, such as depth and contrast. In addition, dark mode is activated only when system-level dark mode is on, so users who aren't using dark mode are not able to toggle between light/dark mode. 

That said, I love how Aral uses the handy ```filter:invert;``` CSS property to swap around the colours. It's worth noting that chrome://dino also uses this same technique!

https://ar.al/2021/08/24/implementing-dark-mode-in-a-handful-of-lines-of-css-with-css-filters/
