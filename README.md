# Phone Glitch Virus Payload

This repository hosts a pure JavaScript/HTML payload designed to stress a mobile phone's browser (or the Facebook Messenger web view) by forcing intense CPU calculations and heavy DOM manipulation, resulting in a "glitchy" user experience.

## How It Works:
The script runs an extremely tight loop (`glitchLoop`) which simultaneously:
1.  Performs complex trigonometric calculations (CPU stress).
2.  Rapidly generates new elements (`<div>`) onto the page (DOM stress).

## Deployment Notes:
This code is best deployed via **GitHub Pages** to generate a permanent, accessible URL that you can paste into Facebook Messenger.
