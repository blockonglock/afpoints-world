# AF.POINTS Roadmap

## Later: Safe Album Import Admin

Goal:
- Bring back the convenient old flow: paste a Spotify album link and get title, artist, year, cover, Spotify URL, and likely genre prefilled.

Constraints:
- Do not restore the old public `server.js` or admin panel as-is.
- Do not expose Spotify, OpenAI, MongoDB, or admin secrets in the public GitHub Pages repo or browser code.
- GitHub Pages remains static; any admin/import feature needs a separate trusted execution path.

Preferred direction:
- Build a small private admin/import tool that fetches Spotify metadata server-side and writes a new review entry to `src/data/reviews.json` or a future content collection.
- The tool can commit to the public repo through GitHub auth/token, or generate a ready-to-commit JSON/Markdown entry locally.
- Keep the public site as static Astro output.

Acceptance:
- Paste Spotify album URL.
- Preview/edit imported fields before saving.
- Add review text/rating manually.
- Save produces a valid static review page after the next Pages build.
