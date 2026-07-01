# Parth Dharashivkar — Portfolio Website

This is a premium, minimal, dark-themed portfolio website for **Parth Dharashivkar** (Editor · Cinematographer · Colorist) built using semantic HTML5, vanilla CSS, and JavaScript.

---

## 🤖 Instructions for AI Agents
If you are an AI coding agent working on this repository, please read these instructions carefully before starting any tasks.

### 1. Local Hosting & Server Setup
* **Port Warning (8080 Caching Conflict):** Do NOT host this project on port `8080` by default. There is a persistent **Service Worker caching conflict** on the user's system from a previous project (*Cyberpunk Advanced Calculator*). If hosted on port `8080`, the browser will intercept requests and display the calculator instead of this website.
* **Preferred Port:** Use port **`8085`** (e.g. `npx -y http-server -p 8085`).
* **Command:** `npx -y http-server -p 8085` (Node) or `python -m http.server 8085` (Python).

### 2. File Structure & Assets
* **`index.html`:** The core and only page of the website. It contains structural HTML, CSS styling in the `<style>` block, and JavaScript interaction logic in the `<script>` block.
* **`assets/`:** Contains video and image assets.
  * **Hero Background Video:** The hero background video uses the YouTube unlisted video `m-dJeHzjJjk` loaded through an iframe configured to loop, mute, and autoplay without controls.
  * **Showreel Video (`AADAT a shortfilm.mp4`):** Located locally in `/assets`. This video is roughly 354MB and is loaded dynamically when the user clicks the play button in the Showreel section to avoid slowing down the page on initial load.
  * **Showreel Thumbnail (`AADAT a shortfilm_preview.jpg`):** Used as a static placeholder in the showreel section, generated to shorten site load time.

### 3. Key Components & Implementation Details
* **Hero Background (Intro Panel):** Has a background iframe loading a muted YouTube video that is styled to cover the viewport cleanly using absolute positioning and translation (`transform: translate(-50%, -50%)`).
* **Showreel Player:** Starts with a static poster wrapper (`.reel-poster-wrap`). Clicking the play button calls `loadReelVideo()`, hides the poster, and injects a local `<video>` element playing the local 53MB showreel video with audio and controls.
* **Work Grid:** Uses individual portfolio items that open a fullscreen popup modal (`#videoModal`) playing their respective MP4 source clips via Javascript `openWorkModal()`.

### 4. Performance & Best Practices
* **Keep Homepage Loading Fast:** Avoid loading heavy video files directly in `<video autoplay>` tags on the homepage. Instead, use static image previews or highly compressed GIFs for initial load, and only fetch/play large video files on user interaction.
* **Service Worker Programmatic Clear:** If you need to programmatic clean up caching, you can inject a script to unregister local service workers.

---

## Technical Specifications
* **Frontend:** Vanilla HTML5, CSS3, ES6 JavaScript.
* **Dependencies:** Google Fonts (Cormorant Garamond, Inter).
* **Responsive Layout:** Tailored with CSS Media Queries for mobile screen sizes (max-width `768px`) and smooth scroll capabilities.
