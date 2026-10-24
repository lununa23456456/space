# Cosmos Fieldnotes

A searchable, source-backed space knowledge explorer built with React, TypeScript, and Vite.

## Run the site

Open `index.html` in a modern browser. No server or Node.js setup is required for the standalone page. The image analyzer needs an internet connection on first use to download its browser-based vision model (about 190 MB); later use can reuse the browser cache. Uploaded images are analyzed in the browser. NASA receives only the recognized search term when related catalog images are requested.

To use the optional Vite development server, install Node.js 20.19+ or 22.12+, then from this folder run:

```sh
npm install
npm run dev
```

Open the local URL printed by Vite. To create a production build, run `npm run build`.

## What is included

- **Ask the archive:** ranks matching knowledge notes and displays the retrieved passages with their NASA references. This is a transparent, local retrieval layer; it does not call an LLM or invent a synthesized answer.
- **Image atlas:** searches NASA's public Images API live. It needs an internet connection; the NASA API does not require a key.
- **Identify image:** uses a browser-based zero-shot CLIP model to compare JPG, JPEG, PNG, and WEBP uploads with space objects and non-space categories. The first model download is large; image inference runs locally in the browser.
- **Field guide:** filters the included notes by category and text.

The local archive is a curated starter corpus, not a copy of the internet or a comprehensive astronomy database. Sources are linked on each note so facts can be checked and the corpus can be expanded. NASA image titles, thumbnails, and descriptions are provided by the NASA Images API.

## Add knowledge

Add a `KnowledgeEntry` to `src/knowledge.ts` with a unique `id`, a category, a factual summary and passage, and a `source` URL plus readable `sourceLabel`. Add any new category to the filter options in `src/App.tsx`.
