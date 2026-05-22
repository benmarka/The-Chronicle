# The Chronicles
## A Century in Snapshots

A static website for year-by-year history essays — politics, culture, science, art & society across the twentieth century.

---

## Folder structure

```
chronicles/
├── index.html          ← the calendar homepage
├── style.css           ← shared styles for all pages
├── README.md           ← this file
└── essays/
    ├── _template.html  ← copy this to start each new essay
    ├── ep0.html        ← Prologue: The World at the Threshold
    ├── 1900.html
    ├── 1901.html
    └── ...
```

---

## Adding a new essay

1. Copy `essays/_template.html` to `essays/YEAR.html` (e.g. `essays/1906.html`)
2. Replace all the placeholder text (YEAR, ESSAY TITLE, etc.)
3. Write the essay between the `<article class="essay-body">` tags
4. Update the `prev`/`next` links at the bottom of the new essay and the previous one
5. Open `index.html` and add the year to the `published` object near the top of the `<script>` tag:

```js
const published = {
  // existing entries...
  1906: { title: "Your Essay Title Here", file: "essays/1906.html" },
};
```

That's it. The calendar dot appears automatically.

---

## Hosting (free options)

### GitHub Pages (recommended)
1. Create a free account at github.com
2. Create a new repository (e.g. `the-chronicles`)
3. Upload all files keeping the folder structure intact
4. Go to Settings → Pages → Source: main branch → Save
5. Your site is live at `https://YOURUSERNAME.github.io/the-chronicles`

### Netlify
1. Drag and drop the `chronicles/` folder onto netlify.com/drop
2. Live instantly at a random URL — you can rename it in settings

### Cloudflare Pages
Similar to Netlify, free tier is generous.

---

## Customizing

- **Colors & fonts**: edit the `:root` variables at the top of `style.css`
- **Site name/subtitle**: edit the `<header>` in `index.html` and each essay file
- **Adding decades beyond the 1990s**: add entries to the `decades` array in `index.html`

---

## Essay formatting tips

- First paragraph: add `class="drop-cap"` for the decorative large first letter
- Section headings: use `<h2>` — they render as small-caps dividers with a rule above
- Pull quotes: use `<blockquote>` — renders with a red left border
- Keep paragraphs relatively short; these read best at a measured pace
