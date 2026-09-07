# Learning with my teacher — K-5 Math (TEKS-aligned)

One application, eight views (Students keeps a record per child: last help, notes, completed work across subjects; plus a Standards library covering every K-5 chapter): **Plan** (full-year planner: fall introduces every standard, spring reteaches and applies it, with STAAR readiness for grades 3-5), **Teach** (daily lessons with warm-up, learn, worked examples, machines, whole-class presenter, practice, exit ticket), **Assignments** (homework, quizzes, exit tickets, bell ringers; print / HTML / CSV; saved library), **Progress** (pacing grid, notes, per-student exit-ticket scores), **Activities** (Division Factory and the machines), **Settings** (teacher name, class, projector mode, rosters, backup).

## Open it (pick one)

1. **Double-click `index.html`.** Works offline immediately. Progress saves in that browser.
2. **Host the folder** on any static web host and share the link with other teachers. Each teacher's data stays in their own browser; the app installs like a native app (address bar → "Install") and works offline after the first visit.
   - GitHub Pages: push the folder to a repo, Settings → Pages → deploy from branch.
   - Netlify Drop: drag the folder onto https://app.netlify.com/drop
   - Your own server: copy the folder to any nginx/Apache web root. No database, no build step, no runtime.
3. **Local network for a classroom:** from inside the folder run `python3 -m http.server 8080` (Python is preinstalled on macOS and most Linux) and open `http://<your-ip>:8080` on student devices.


## Keep progress when you move the app (folders, computers, USB)
Settings → **Progress file** → "Create and link a progress file" (Chrome or Edge). From then on every change is written to that JSON file automatically; on the next open the app shows a Reconnect bar, and one click loads it. Keep the file next to the app or in a synced folder. Browsers that cannot write files (Firefox, Safari) use Export / Import in Settings instead.

## First-time tour
The app opens with a short guided tour. Esc or Skip closes it; the checkbox in the tour (or Settings) controls whether it opens next time. "? Tour" under the header reopens it any time.

## Teacher name
The title is "Learning with my teacher". Settings → Teacher name (optional) changes it everywhere to "Learning with my teacher, Name", including assignment headers and the Division Factory module.

## Every subject
The Standards library holds every K-5 chapter the State Board lists, with links to the TEA chapter index, the subchapter PDF, and the compiled grade PDF. Loaded verbatim so far: Mathematics K-5 (full lessons), Character Traits K-5 (19 TAC Ch. 120), Social Studies K-5 and ELAR K-5 (question banks on every knowledge statement; Kindergarten with full material), Science K-5 (with authored material: big ideas, facts, drawn visuals, activities, and check questions for every content standard, plus links to NASA, USGS, NOAA, TPWD, and Wikimedia Commons for real photographs), and every Kindergarten subject. For loaded packs the app generates a 36-week plan and concept lesson decks; add your own questions on any expectation and they flow into practice, exit checks, and sheets. Coverage per expectation: not started, covering, covered, mastered. Privacy: rosters and scores never leave the browser; export is explicit.

## Teaching a lesson
Teach → Teach it live is an 11-slide deck with the same routine every day: goal, warm-up retrieval, vocabulary cards, word check, memory device, steps, I do (one step at a time), We do, You do, find the mistake, wrap-up. Teacher notes sit under each slide; Print teacher guide prints them. Settings → Accessibility has text size, dyslexia-friendly text, high contrast, and reduced motion. 

## Sharing your screen
Teach and Activities have pop-out buttons that open the student-facing parts (lesson, Teach it live, machines) in their own window. Share that window; teacher-only material never appears in it. Export/Import in Settings moves everything between computers as one JSON file.

## Files
- `index.html`, `styles.css`, `app.js` — the interface
- `engine.js` — 105 skill generators, 3-level difficulty policy, no-repeat set builder
- `app.js` also carries the lesson deck (explicit-instruction slides with teacher scripts), the glossary of 325 kid-language definitions, 28 memory devices, step-by-step solution traces for every skill, and 24 interactive machines (ten frames, base-ten blocks, place-value chart, number-line jumps, rounding, even/odd pairs, arrays/area, sharing, long division with 1- or 2-digit divisors, fractions, decimal grids, clock, coins, budget, measuring, shapes, angles, coordinates, volume, graphs, input-output, order of operations, balance); every one of the 540 days has at least one
- `data.js` — 6 grades × 36 weeks × 5 days (1,080 lessons), TEKS text from 19 TAC Ch. 111 Subch. A
- `activities/division.html` — Division Factory (Grade 4-5)
- `manifest.webmanifest`, `sw.js`, icons — installable/offline support when hosted
- `qa-audit-report.md` — defect log and automated test results

## Sources
- 19 TAC Chapter 111, Subchapter A: https://tea.texas.gov/laws-and-rules/sboe-rules-tac/sboe-tac-currently-effect/ch111a.pdf
- TEA rule index: https://tea.texas.gov/about-tea/laws-and-rules/texas-administrative-code/19-tac-chapter-111
- TEKS overview: https://tea.texas.gov/academics/curriculum-standards/teks/texas-essential-knowledge-and-skills
