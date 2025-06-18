# Facebook Buy & Sell Group Sold Listing Hider Bookmarklets

A pair of powerful bookmarklets to filter listings in Facebook Buy/Sell groups, making your browsing experience cleaner and more efficient.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

---

## ☕️ Support the Project ☕️

If you find these tools useful, please consider supporting their development!

<a href="https://coff.ee/wild_wanderer" target="_blank"><img src="https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png" alt="Buy Me A Coffee" style="height: 41px !important;width: 174px !important;box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;-webkit-box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;" ></a>
&nbsp;&nbsp;
<a href="https://paypal.me/JustinJWild" target="_blank"><img src="https://img.shields.io/badge/PayPal-Donate-blue?style=flat&logo=paypal" alt="Donate with PayPal"></a>

---

## Features

Do you ever come across the perfect item listed for sale on Facebook, only to get super frustrated when you realize it has already been sold. Are you annoyed that Facebook doesn't provide a way to filter out sold listings? 

These are two separate bookmarklets that work "live" on the page, actively hiding items as you scroll.

1.  **Hide SOLD Items (v14):** Cleans up the feed by hiding all listings marked as `(SOLD)`. Perfect for seeing only what's still available for purchase.
2.  **Show Only SOLD Items (v6):** Does the opposite, hiding all listings that are not marked as `(SOLD)`. Perfect for reviewing what has recently sold and for how much.

Both bookmarklets feature:
* **Live Filtering:** They use a `MutationObserver` to watch the page and automatically hide items as they are loaded, so you only have to click it once.
* **Smart Notifications:** A clean, non-overlapping notification system tells you when the script is active and how many items have been hidden.

## Installation

1.  Make sure your browser's bookmarks/favorites bar is visible. (Usually `Ctrl`+`Shift`+`B` or `Cmd`+`Shift`+`B`).
2.  Create a new bookmark. You can do this by right-clicking the bookmarks bar and selecting "Add page..." or "Add bookmark...".
3.  Give the bookmark a name (e.g., `FB Hide Sold` or `FB Show Only Sold`).
4.  Copy the entire code for the desired bookmarklet (from the files below) and paste it into the **URL / Address** field of the bookmark.
5.  Save the bookmark.

These have been tested and confirmed working in Chrome. 

## Bookmarklet Code

### Hide SOLD Items (v14)

This hides listings marked as `(SOLD)`.

```javascript
javascript:(function(){if(window.soldHiderActive){return}window.soldHiderActive=!0;let e=0;const t=new Set;let i=null,o=null,n=null;function s(s,l){if("activation"===l){if(i)return;i=document.createElement("div"),i.style.cssText="position:fixed; top: 20px; left:50%;transform:translateX(-50%);padding:16px 24px;background-color:#15803d;color:white;border-radius:8px;box-shadow:0 4px 15px rgba(0,0,0,0.2);z-index:999999;font-family:sans-serif;font-size:16px;transition:all 0.5s ease;",i.textContent=s,document.body.appendChild(i),setTimeout(()=>{document.body.contains(i)&&document.body.removeChild(i),i=null,r()},3500)}else if("counter"===l){if(!o)o=document.createElement("div"),o.style.cssText="position:fixed; left:50%;transform:translateX(-50%);padding:16px 24px;background-color:#15803d;color:white;border-radius:8px;box-shadow:0 4px 15px rgba(0,0,0,0.2);z-index:999998;font-family:sans-serif;font-size:16px;transition:all 0.5s ease;",document.body.appendChild(o),r();o.textContent=s,o.style.opacity="1",clearTimeout(n),n=setTimeout(()=>{o&&(o.style.opacity="0")},4e3)}}function r(){if(!o)return;let e=i?i.offsetHeight+30:20;o.style.top=`${e}px`}function l(e){let i=0;const o=e.matches('div[role="feed"] > div')?[e]:Array.from(e.querySelectorAll('div[role="feed"] > div'));return o.forEach(e=>{if(!t.has(e)){const o=e.textContent;o&&o.includes("(SOLD)")&&(e.style.display="none",i++),t.add(e)}}),i}const c=new MutationObserver(t=>{let i=0;t.forEach(t=>{t.addedNodes.forEach(t=>{1===t.nodeType&&(i+=l(t))})}),i>0&&(e+=i,s(`Hid sold item (${e} total listings hidden)`,"counter"))});(function(){e+=l(document.body)})(),s(`Now actively hiding sold listings! ${e} listings hidden. (v14)`,"activation"),c.observe(document.body,{childList:!0,subtree:!0})})();
```
<a href="bookmarklets/hide-sold.js" target="_blank">View the Hide Sold Items js file</a>. 

### Show Only SOLD Items (v6)

This hides all available listings, showing only those marked `(SOLD)`.

```javascript
javascript:(function(){if(window.availableHiderActive){return}window.availableHiderActive=!0;let e=0;const t=new Set;let i=null,o=null,n=null;function s(s,l){if("activation"===l){if(i)return;i=document.createElement("div"),i.style.cssText="position:fixed; top: 20px; left:50%;transform:translateX(-50%);padding:16px 24px;background-color:#a16207;color:white;border-radius:8px;box-shadow:0 4px 15px rgba(0,0,0,0.2);z-index:999999;font-family:sans-serif;font-size:16px;transition:all 0.5s ease;",i.textContent=s,document.body.appendChild(i),setTimeout(()=>{document.body.contains(i)&&document.body.removeChild(i),i=null,r()},3500)}else if("counter"===l){if(!o)o=document.createElement("div"),o.style.cssText="position:fixed; left:50%;transform:translateX(-50%);padding:16px 24px;background-color:#a16207;color:white;border-radius:8px;box-shadow:0 4px 15px rgba(0,0,0,0.2);z-index:999998;font-family:sans-serif;font-size:16px;transition:all 0.5s ease;",document.body.appendChild(o),r();o.textContent=s,o.style.opacity="1",clearTimeout(n),n=setTimeout(()=>{o&&(o.style.opacity="0")},4e3)}}function r(){if(!o)return;let e=i?i.offsetHeight+30:20;o.style.top=`${e}px`}function l(e){let i=0;const o=e.matches('div[role="feed"] > div')?[e]:Array.from(e.querySelectorAll('div[role="feed"] > div'));return o.forEach(e=>{if(!t.has(e)){const o=e.textContent;o&&!o.includes("(SOLD)")&&(e.style.display="none",i++),t.add(e)}}),i}const c=new MutationObserver(t=>{let i=0;t.forEach(t=>{t.addedNodes.forEach(t=>{1===t.nodeType&&(i+=l(t))})}),i>0&&(e+=i,s(`Hid available item (${e} total listings hidden)`,"counter"))});(function(){e+=l(document.body)})(),s(`Now actively hiding available listings! ${e} listings hidden. (v6)`,"activation"),c.observe(document.body,{childList:!0,subtree:!0})})();
```
<a href="bookmarklets/show-only-sold.js" target="_blank">View the Show Only Sold Items js file</a>. 

## Screenshots

![Screenshot of the Hide Sold bookmarklet in action](assets/images/hide-sold.png)
![Screenshot of the Show Only Sold bookmarklet in action](assets/images/show-only-sold.png)

## Contributing

This script relies on the structure of Facebook's code, which changes frequently. If you notice it's broken, please feel free to open an issue or submit a pull request!

## Disclaimer

This is a third-party script and is not affiliated with Facebook in any way. Use at your own risk.
