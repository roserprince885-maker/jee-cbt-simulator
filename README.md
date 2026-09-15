# JEE CBT Simulator

A single-file, browser-only mock test tool that mimics the NTA CBT exam screen. Upload a question paper, sit it full-screen with the real palette/timer behaviour, then get a downloadable PDF performance report.

**Nothing is uploaded to a server** — the whole thing runs in the browser tab you open it in, including the PDF export.

## How to use it

1. Open `jee-cbt-simulator.html` (double-click it, or use the live link if this is hosted on GitHub Pages).
2. On the home screen, load a paper:
   - **Upload a file** — `.txt` or `.json` work reliably; `.pdf` is parsed best-effort (review the results before starting).
   - **Paste text** — start each question with `Q1`, `Q2`… and options with `(1)`–`(4)`. Add a short line like `Physics` before a section to split subjects.
   - **JSON template** — the most reliable format; download the template button on that tab for the exact structure (includes correct answers, difficulty, chapter/topic).
   - Or just click **Try the sample paper** to see the whole flow with a small built-in demo paper.
3. Review the parsed questions, add an answer key if one wasn't detected (bulk format: `1-2, 2-4, 3-1 …`).
4. Read the instructions screen, tick the boxes, and click **Start test** — the screen goes full-screen automatically.
5. Take the test using the same Save & Next / Mark for Review / palette workflow as the real NTA screen.
6. On submit, you get a full performance report (score, accuracy, time & difficulty analysis, painful questions, missed concepts…) with a **Download as PDF** button.

## Files

- `jee-cbt-simulator.html` — the entire app (HTML + CSS + JS in one file).

## Tech notes

- No build step, no dependencies to install — it's a static HTML file.
- Uses Chart.js, html2canvas, jsPDF and pdf.js, loaded from cdnjs.cloudflare.com at runtime (so an internet connection is needed the first time each library loads).
- Works best in a recent Chrome/Edge/Firefox. Full-screen and PDF export both rely on browser APIs that may behave slightly differently on Safari/iOS.
