# Barn South website

Plain HTML/CSS — no build tools, no npm install. Every page is a separate `.html` file you can open and edit directly.

## Files

```
index.html      Home page
rental.html     Bike Rental (fleet + prices)
storage.html    Bike Storage
gallery.html    Gallery + Instagram link
for-sale.html   Used bikes, tires, jerseys
contact.html    Contact details + map
CNAME           Tells GitHub Pages to serve this at barnsouth.my (leave as is)
css/styles.css  All the styling — colors, fonts, layout
js/main.js      Just the mobile menu button
```

## 1. Upload to GitHub

In your `barnsouth.my` repo: **Add file → Upload files**, then drag in *all* of the above files and folders at once (including `css` and `js`), keeping the folder structure intact. Commit changes. Within a minute or two, `barnsouth.my` should show this site instead of a 404.

## 2. Things to replace before going live

Every placeholder is marked with a yellow banner at the top of each page — delete that `<div class="build-note">...</div>` line once a page is finalized.

**Your WhatsApp number** — appears many times as `https://wa.me/60123456789`. Use Find & Replace in any text editor (or GitHub's own editor: click the pencil icon on a file) to swap `60123456789` for your real number in international format with no `+`, spaces or dashes (e.g. Malaysian mobile `012-345 6789` becomes `60123456789`).

**Your Instagram handle** — search for `barnsouthmy` in `instagram.com` links and `@barnsouthmy` mentions (found in every page footer, plus `gallery.html` and `contact.html`) and replace with your real handle.

**Bike inventory & prices** — edit the tables and lists in `rental.html`. Each bike is one `<li>` line; each price is one `<td class="price">` cell. Copy an existing line and change the text to add more bikes.

**Storage details & pricing** — edit the paragraphs and price table in `storage.html`.

**For Sale items** — each product is one `.product-row` block in `for-sale.html`. Copy, paste, and edit to add or remove items.

**Contact details** — address, email, hours are plain text in `contact.html`'s info list. The map is a placeholder OpenStreetMap embed; once you have a confirmed address, search it on [openstreetmap.org](https://www.openstreetmap.org), use Share → Embed, and paste the new `iframe` code in over the old one.

## 3. Adding real photos and video

1. Create an `images` folder in the repo (or a `videos` folder) and upload your files there.
2. In `gallery.html` (or `storage.html`), find a `<div class="media-tile">...</div>` block and replace it with:
   ```html
   <div class="media-tile" style="background:none; padding:0;">
     <img src="images/your-photo.jpg" alt="Describe the photo" style="width:100%; height:100%; object-fit:cover;">
   </div>
   ```
3. For video, same idea but with:
   ```html
   <video src="videos/your-clip.mp4" controls style="width:100%; height:100%; object-fit:cover;"></video>
   ```

## 4. Editing text or colors

- Wording: just edit the text between HTML tags directly in each `.html` file — nothing will break as long as you don't touch anything inside `< >` angle brackets.
- Colors: all colors are defined once at the top of `css/styles.css` under `:root { ... }` — change a value there (e.g. `--accent: #C1652F;`) and it updates everywhere that color is used.

## 5. Testing changes before pushing

Since these are plain files, you can double-click `index.html` on your own computer to preview it in a browser before uploading — no server needed. Links between pages (`rental.html`, etc.) will work locally too.
