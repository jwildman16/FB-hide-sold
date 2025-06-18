Facebook Marketplace Feed Hider Bookmarklets
A pair of powerful bookmarklets to filter listings in Facebook Marketplace Buy/Sell groups, making your browsing experience cleaner and more efficient.

❤️ Support the Project
If you find these tools useful, please consider supporting their development!

Features
These are two separate bookmarklets that work "live" on the page, actively hiding items as you scroll.

Hide SOLD Items (v14): Cleans up the feed by hiding all listings marked as (SOLD). Perfect for seeing only what's still available for purchase.

Show Only SOLD (v6): Does the opposite, hiding all available listings. Perfect for reviewing what has recently sold and for how much.

Both bookmarklets feature:

Live Filtering: They use a MutationObserver to watch the page and automatically hide items as they are loaded, so you only have to click it once.

Smart Notifications: A clean, non-overlapping notification system tells you when the script is active and how many items have been hidden.

Installation
Make sure your browser's bookmarks/favorites bar is visible. (Usually Ctrl+Shift+B or Cmd+Shift+B).

Create a new bookmark. You can do this by right-clicking the bookmarks bar and selecting "Add page..." or "Add bookmark...".

Give the bookmark a name (e.g., Hide SOLD or Show Only SOLD).

Copy the entire code for the desired bookmarklet (from the files below) and paste it into the URL / Address field of the bookmark.

Save the bookmark.

Bookmarklet Code
🟢 Hide SOLD Items (v14)
This hides listings marked as (SOLD).

javascript:(function(){if(window.soldHiderActive){return}window.soldHiderActive=!0;let e=0;const t=new Set;let i=null,o=null,n=null;function s(s,l){if("activation"===l){if(i)return;i=document.createElement("div"),i.style.cssText="position:fixed; top: 20px; left:50%;transform:translateX(-50%);padding:16px 24px;background-color:#15803d;color:white;border-radius:8px;box-shadow:0 4px 15px rgba(0,0,0,0.2);z-index:999999;font-family:sans-serif;font-size:16px;transition:all 0.5s ease;",i.textContent=s,document.body.appendChild(i),setTimeout(()=>{document.body.contains(i)&&document.body.removeChild(i),i=null,r()},3500)}else if("counter"===l){if(!o)o=document.createElement("div"),o.style.cssText="position:fixed; left:50%;transform:translateX(-50%);padding:16px 24px;background-color:#15803d;color:white;border-radius:8px;box-shadow:0 4px 15px rgba(0,0,0,0.2);z-index:999998;font-family:sans-serif;font-size:16px;transition:all 0.5s ease;",document.body.appendChild(o),r();o.textContent=s,o.style.opacity="1",clearTimeout(n),n=setTimeout(()=>{o&&(o.style.opacity="0")},4
