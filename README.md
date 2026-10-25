

> Preserve village memories. Amplify local voices.

Built for **Hacktober HackDays 2026** · Theme: Empowering Local Communities · Powered by **Cloudinary**

**Live app:** <https://live-it-6b3d80.netlify.app>

**Documentation (Notion):** <https://app.notion.com/p/Gaon-Ki-Awaaz-404f57244a2880e1a742e70a2f4827df?source=copy_link>

## The Problem
Old photos and stories of villages are lost as the elderly pass away, and everyday local problems (a broken hand pump, a bad road) rarely reach the right people. Most villagers cannot write a formal complaint, and most tools are English-only and text-heavy.

## The Solution
A mobile-first web app with two modules:

**🗺️ Yaadein (Memory Map)**
- Pin an old photo on a map with a title and year
- Record an elder's voice story
- AI restores the photo, with a before/after slider

**📢 Awaaz (Village Voice)**
- Record a 15-second video of a local problem
- Title and category are burned onto the video automatically
- "Main bhi sehmat" votes push the most-supported problems to the top
- One-tap summary to send to the Sarpanch or officials

## How We Use Cloudinary
| Feature | Used for |
|---|---|
| Unsigned upload API (image + video) | Photos, videos and voice stories, no backend |
| `e_gen_restore` | AI restoration of old photos |
| `e_improve` + `e_sharpen` | Fallback enhancement if the add-on is off |
| `q_auto`, `f_auto` | Light, fast delivery on low bandwidth |
| `w_`, `c_limit` | Resizing for cheap phones |
| `du_15` | Trim problem videos to 15 seconds |
| `f_mp4` | Plays on every device |
| `l_text` overlay | Title + category on the video |
| `so_0` `.jpg` | Automatic video thumbnails |
| Audio as `.mp3` | Voice stories work on Safari/iOS too |

## Tech Stack
HTML, CSS, JavaScript · Cloudinary · Leaflet + OpenStreetMap · Web Speech API · MediaRecorder API

## Run It Yourself
1. Create a free [Cloudinary](https://cloudinary.com) account.
2. Go to **Settings → Upload → Upload presets → Add upload preset** and set **Signing Mode: Unsigned**.
3. Open `index.html` and replace these two lines:
   ```js
   const CLOUD = "YOUR_CLOUD_NAME";
   const PRESET = "YOUR_UNSIGNED_PRESET";
   ```
4. Open `index.html` in a browser (or host it on Netlify/Vercel).

> Never put your Cloudinary **API secret** in this project. The app only needs the cloud name and an unsigned preset.

## Known Limitations
- Data is stored in the browser and shared through a link, so votes are per device for now.
- Overlay text on videos supports Latin letters (Hinglish), not Devanagari.
- AI restore needs Cloudinary's Generative Restore add-on; otherwise a basic enhancement is shown.

## Future Scope
- Shared database so memories and votes sync across everyone
- Hindi auto-subtitles
- Offline mode
- Integration with government complaint portals

## Team
<Team name> · <Member 1>, <Member 2>, <Member 3>

## License
MIT
