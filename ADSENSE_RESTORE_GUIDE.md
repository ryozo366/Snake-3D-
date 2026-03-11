# How to Restore Everything After AdSense Approval

Once Google AdSense is approved, follow these steps to re-enable login, tutorial, and third-party ads.

Search for `TEMPORARILY DISABLED FOR ADSENSE VERIFICATION` in `index.html` to find all changes.

---

## 1. Re-enable Monetag + Adsterra (Head Scripts)

**Line ~9-18**: Replace the comment block with the original scripts:

```html
<meta name="monetag" content="42171f7af91f7e042d03227c2e4a2b55">
```
(remove the `<!-- -->` comment around it)

**Line ~14-18**: Replace the plain text comment with the actual script tags:

```html
<script src="https://5gvci.com/act/files/tag.min.js?z=10710453" data-cfasync="false" async></script>
<script>(function(s){s.dataset.zone='10710458',s.src='https://nap5k.com/tag.min.js'})([document.documentElement, document.body].filter(Boolean).pop().appendChild(document.createElement('script')))</script>
<script src="https://pl28890807.effectivegatecpm.com/3e/5e/a5/3e5ea57d3a8c42c73ddcf3f97353491f.js"></script>
```

---

## 2. Re-enable Adsterra Banner Ads (Game Over Screen)

**Line ~852**: Replace the comment with:

```html
<div class="ad-banner-side left" id="go-ad-left">
  <script>atOptions={'key':'3306d19d042fdaa38a6dfac27962817e','format':'iframe','height':300,'width':160,'params':{}};</script>
  <script src="https://www.highperformanceformat.com/3306d19d042fdaa38a6dfac27962817e/invoke.js"></script>
</div>
```

**Line ~877**: Replace the comment with:

```html
<div class="ad-banner-side right" id="go-ad-right">
  <script>atOptions={'key':'3306d19d042fdaa38a6dfac27962817e','format':'iframe','height':300,'width':160,'params':{}};</script>
  <script src="https://www.highperformanceformat.com/3306d19d042fdaa38a6dfac27962817e/invoke.js"></script>
</div>
```

---

## 3. Re-enable Rewarded Ad (Adsterra + Monetag in JavaScript)

**Line ~2589**: Uncomment the JavaScript code (remove the `//` from each line):

```javascript
  try {
    const slot = document.getElementById('rewarded-ad-slot');
    window.atOptions = { key: '3306d19d042fdaa38a6dfac27962817e', format: 'iframe', height: 300, width: 160, params: {} };
    const adScript = document.createElement('script');
    adScript.src = 'https://www.highperformanceformat.com/3306d19d042fdaa38a6dfac27962817e/invoke.js';
    slot.appendChild(adScript);
  } catch(e) {}

  try {
    const s = document.createElement('script');
    s.dataset.zone = '10710460';
    s.src = 'https://gizokraijaw.net/vignette.min.js';
    document.body.appendChild(s);
  } catch(e) {}
```

---

## 4. Re-enable Tutorial

**Line ~1169**: Change this:

```javascript
  // TEMPORARILY DISABLED FOR ADSENSE VERIFICATION - tutorial was blocking content for crawlers
  // if (!tutorialDone) { tutorialDone = true; startTutorial(); }
  tutorialDone = true;
```

Back to:

```javascript
  if (!tutorialDone) { tutorialDone = true; startTutorial(); }
```

---

## 5. Re-enable Login Screen

**Line ~4143**: Change this:

```javascript
  // Original: showLoginScreen();
  // Temporarily skip login, play as guest automatically
  playAsGuest();
```

Back to:

```javascript
  showLoginScreen();
```

---

## 6. Re-enable Watch Ad Buttons

Search for `TEMPORARILY DISABLED FOR ADSENSE VERIFICATION - Watch Ad button` — there are 3 places (upgrades, maps, skins). Remove the `//` or `/* */` comment markers around the code blocks.

---

## 7. Rename Cheat Code Back (optional)

The cheat code `hack` was renamed to `god`. If you want to change it back, find `code === 'god'` and change it to `code === 'hack'`, and change `GOD MODE!` back to `HACKED!`.

---

## Optional: Remove SEO/Privacy additions

You can keep these even after re-enabling everything (they help with SEO):
- Meta description, viewport, keywords tags
- noscript block with game description
- Privacy Policy footer
- Improved title tag
