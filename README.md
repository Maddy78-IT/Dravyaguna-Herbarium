# Dravyaguna Herbarium

A tiny static site for your Dravyaguna plant notes. Scan a QR code → land straight on that plant's rasa–guna–virya–vipaka profile. No backend, no build step — just HTML, CSS and one data file.

## Files

```
index.html        the homepage — searchable grid of all plants
plant.html         the specimen page — reads ?id=xxx and shows that plant
qrcodes.html       generates & downloads a QR code per plant
style.css          shared styling
data/plants.js     <-- the only file you edit to add plant data
```

## 1. Add your plants

Open `data/plants.js`. At the top there's a commented-out template object showing every field (rasa, guna, virya, vipaka, prabhava, karma, dose, etc). For each plant:

1. Copy the template.
2. Paste it inside the `PLANTS = [ ... ]` array.
3. Fill in the values. Leave anything blank (`""`) if you don't have it yet — blank fields are just skipped on the page.
4. Give it a unique `id` (lowercase, hyphens, no spaces) — e.g. `"tulsi"`, `"ashwagandha"`. This becomes the URL: `plant.html?id=tulsi`.

Save the file and open `index.html` in a browser to check it worked. You can keep adding plants any time — no other file needs to change.

## 2. Put it on GitHub Pages

1. Create a new repository on GitHub (e.g. `dravyaguna-herbarium`) and push these files to it (the whole folder, including `data/`).
2. In the repo, go to **Settings → Pages**.
3. Under "Build and deployment", set **Source** to "Deploy from a branch", branch `main`, folder `/ (root)`. Save.
4. GitHub gives you a URL like `https://yourusername.github.io/dravyaguna-herbarium`. It can take a minute or two to go live after each push.

## 3. Generate QR codes

1. Open `qrcodes.html` (either locally or on your live GitHub Pages URL).
2. Paste your live site URL from step 2 into the box at the top.
3. Click **Generate all codes** — each plant gets its own QR code pointing to `plant.html?id=<that plant>`.
4. Click **Download** under any code to save it as a PNG, or **Print sheet** to print all of them at once for labels.

Note: the QR codes only work once the site is actually live at that URL — generate them after deploying, and re-generate if the URL ever changes.

## Updating later

Whenever you add or edit a plant in `data/plants.js`, just push the change to GitHub — the live site updates automatically, and existing QR codes keep working as long as you don't change a plant's `id`.
