# Learning with my teacher — QA Audit Report (v6, social studies, ELAR, character traits)

**Scope:** the unified application, delivered as a folder (`learning-with-my-teacher/`, zipped as `learning-with-my-teacher-app.zip`) and as the identical single file `learning-with-my-teacher.html`. Views: Plan (semester planner), Teach (daily lessons), Assignments, Progress, Activities (Division Factory + machines), Settings. The three earlier separate files are superseded and folded into this one app.
**Standards source:** 19 TAC Chapter 111, Subchapter A (§111.2–§111.7), <https://tea.texas.gov/laws-and-rules/sboe-rules-tac/sboe-tac-currently-effect/ch111a.pdf>
**Audit date:** September 5, 2026
**Roles applied:** educator (progression, misconceptions, language), LMS senior developer (persistence, progress model, export), senior web developer (rendering, print, accessibility), software architect (data flow, separation of content from engine), senior QA auditor (defect log, root cause), senior tester (automated matrix, visual review).

---

## 0000000. Social Studies, ELAR, and Character Traits at full depth (v6)

Same depth as science for every unit: verbatim standard, kid-language big idea, three facts, glossary words with pictures, a drawn visual, a hands-on activity, discussion prompts, teacher talking points (hook, say-lines, examples, the misconception to listen for, questions with expected answers), and six check questions. Everything flows into decks, warm-ups, We do / You do, practice, exit checks, sheets, index cards, coverage, and student records.

| Pack | Standards source | Units | Questions | Glossary words | Visuals |
|---|---|---|---|---|---|
| Social Studies, Kindergarten | §113.11 (2022, effective 2024-25), TEA compiled K PDF | 15 | 90 | 55 | 15 (flags with all fifty stars, campus map, needs vs wants, jobs, rules, authority figures, voting, families, traditions, technology, sources, timeline, holidays, historical figures, places) |
| English Language Arts and Reading, Kindergarten | §110.2 (2017), TEA compiled K PDF | 12 | 72 | 55 | 9 (listening and speaking, letters and sounds, word categories, book parts, story map, genres, author's craft, writing process, inquiry) |
| Character Traits, K-5 | 19 TAC Chapter 120 Subchapter A: §120.3 (K-2) loaded for K, 1, 2; §120.5 (3-5) loaded for 3, 4, 5. Adopted 2020, effective 2021-22. Verified against the published rule text | 4 per grade band (trustworthiness, responsibility, caring, good citizenship), written separately for K-2 and 3-5 | 48 (6 per unit per band) | 35 | 4 |

Character Traits is a subject in the drop-down and the Standards library, with the state's four strands and the statute's own trait lists. K-2 material teaches the traits concretely (stop, breathe, think, choose; the four trust builders; patience in line; fair sharing); 3-5 material adds reliability and loyalty, unethical behavior, accountability and consequences, acting on feedback, empathy and charity, fairness versus justice, and courage for the common good, in the standard's own words.

Accuracy notes: Independence Day, Veterans Day (November 11), Presidents' Day, and Constitution Day (September 17) as in the standard; George Washington first president, Stephen F. Austin's settlements, José Antonio Navarro's role in Texas law, Columbus's voyage; the U.S. flag drawing carries fifty stars in the nine-row pattern and thirteen stripes; the Texas flag is the Lone Star; ELAR phonics examples use the letter-sound convention (b says /b/); every character definition mirrors the strand definitions in §120.3(b)(2).

Test T21 checks all 48 units (material complete, six valid questions each, glossary entries present, pictures render, decks and every view render) and the character standards' shape.

### Not yet loaded, stated plainly
Social Studies and ELAR for grades 1-5 (the TEA compiled grade PDFs are one ingestion each), Health, PE, Fine Arts, and Technology Applications for grades 1-5. The format and pipeline are proven on every pack above; the Standards library shows exactly what is loaded.

## 0000000000000. Dyslexia mode contrast (v6.2)

**D-73.** Dyslexia-friendly text turned every card cream, including the dark hero cards on Home, Teach, and the student record, which left white text on a cream background. The cream now applies only to light cards; the hero, the lesson deck, and the helper card keep their dark background and white text. Checked in T26 against the built stylesheet.

## 000000000000. Generation to 100 for every subject; subject list follows the grade (v6.1)

The user was right on both counts: subjects were still listed for grades that had nothing, and "the count that exists" was a description of the problem rather than a solution.

* **D-71 Subject list follows the grade.** The Subject drop-down and the Standards tabs list only subjects with standards loaded for the selected grade (or the selected student's grade). Health, PE, Art, Music, Theatre, and Technology Applications appear for Kindergarten only until their upper grades are ingested; Mathematics, Science, ELAR, Social Studies, and Character Traits appear for every grade. Switching to a grade where the current subject has nothing falls back to Mathematics.
* **D-72 Question generation for every non-math subject.** Two generators now run beside the authored banks:
  * **Vocabulary items** from the subject glossary, up to four per term: word to meaning, meaning to word, "which one shows the meaning," and fill-in-the-blank from the example sentence. Distractors are drawn from other terms in the same subject; choices are guaranteed distinct; an item that cannot reach four distinct choices is dropped.
  * **Fact items** from authored material: "Which statement is true about [big idea]?" with the unit's fact against facts from other units.
  Glossaries were grown to make this work: Social Studies +43 grade-tagged terms (grades 1–5), ELAR +38, Character Traits +9, and new glossaries for Health (20), PE (20), Art (30), Music (26), Theatre (26), and Technology Applications (24). Every term has a kid-language meaning, an example, a "not this," and a drawn picture for its card.
* **Any count up to 100 for any type.** Homework, quiz, exit ticket, bell ringer, and in-class practice accept up to 100. If the chosen scope cannot supply the count, the sheet widens automatically to earlier units, then the whole grade, and says so on the sheet; review items carry their unit in the answer key. Vocabulary card sets max out at the number of words for the scope, as requested. Result: every subject and grade in the app can fill 100 distinct questions; whole-grade pools now range from 102 (Technology Applications K) to 267 (Social Studies K).
* Decks and practice draw from the same pools, so warm-ups, You do, and exit checks have more variety too.

Test T26 builds a 100-item pool for every subject and grade, checks distinct question text and distinct choices, renders a 100-question sheet of each of the five types, checks vocabulary sheets equal the glossary count, and checks the grade-driven subject list.

## 00000000000. Assignment types for every subject, higher counts, registry cleanup (v6.0)

* **D-68 Assignment types.** Non-math subjects offered only "question sheet." Every subject now has the same five types as math: Homework (15, gets harder), Quiz (10, mixed), Exit ticket (3, with a score line), Bell ringer (5, basic), In-class practice (20), plus vocabulary card sets and the rubric checklist. Each sheet has a title, an answer key on its own page with explanations, optional hints and level badges, the type printed in the header, and **Save to library** with a per-subject, per-grade list to reopen or delete. The Type control drives the form: question types show count, scope, difficulty, and options; card and rubric types hide them.
* **D-69 Counts.** The Questions field accepts up to 100 in every subject, including math (was 40). Math generates any count fresh. Other subjects draw from their pools: the count message reports how many distinct questions exist for the chosen scope before you generate and again on the sheet if the request exceeds it.
* **D-70 Empty subjects removed.** Spanish Language Arts and ESL, Languages Other Than English, Career and Technical Education, and Other TEKS had no standards or content in the app; they are gone from the subject list and the Standards library. The PRD still records them for the roadmap. Every remaining subject has at least one loaded grade with standards and questions.

Test T25 checks the five types with keys and options, a 60-question whole-grade quiz, an exit ticket with a score line, vocabulary and rubric sheets, library persistence, and that no empty subject remains.

## 0000000000. Social Studies and ELAR, every grade (v5.9)

* **ELAR grades 1–5 loaded** verbatim from 19 TAC Chapter 110 Subchapter A (August 2019 update; adopted 2017): §110.3–110.7, 65 knowledge statements with every sub-item inline. Social Studies grades 1–5 were loaded in v5.7. Both subjects now show all six grades in the Standards library, Plan, Teach, Assignments, Activities, Progress, and coverage tracking.
* **Question banks on every knowledge statement, K–5, both subjects.** Social Studies: 531 questions (K 45; grades 1–5 authored this round for all 99 knowledge statements, three to eight each). ELAR: 365 questions (K 36; grades 1–5 for all 65 knowledge statements). Every question was written against the standard's own examples: the historical figures, documents, dates, symbols, and inventors the standard names, and the phonics, grammar, and genre terms the ELAR standard names. Facts spot-checked in the audit include the dates of Texas independence (March 2, 1836), San Jacinto (April 21, 1836), annexation (1845), Spindletop (1901), the Louisiana Purchase (1803), the Transcontinental Railroad (1869), the 13th and 15th Amendments, the Mayflower Compact (1620) and House of Burgesses (1619), state and national symbols, and the spelling rules (drop e, change y to i, double the final consonant).
* **Assignments now fill.** A whole-grade question sheet in either subject draws from 40 to 130 distinct questions per grade; the unit scope draws that unit's questions; the "everything so far" scope draws all units to date. The count message and scope control from v5.8 remain, so the sheet still says exactly how many exist when a request exceeds the pool.
* **Audit fixes this round (D-67):** four question items had answer choices that differed only by case or were duplicated, which would have let a student see two identical options; corrected. Two overlapping K banks merged by text so a question never appears twice on a sheet.

Test T24 checks, for both subjects and all six grades: standards loaded, three or more questions on every knowledge statement, a whole-grade pool of forty or more, no duplicate choices (case-insensitive), decks build, and views render.

## 000000000. Round v5.8: machines, sheet counts, multiplication and division mix

* **D-64 Math machines under other subjects.** The Activities view for non-math subjects appended four math machines. Removed; machines belong to math only.
* **D-65 Fifty requested, six delivered, and repeated.** Two causes. The Kindergarten ELAR unit had the same three questions in two files (authored material and the question bank), so the sheet drew each twice with shuffled choices; questions are now deduplicated by text everywhere they are pooled. Second, there is no question generator for language and social subjects the way there is for math, so a sheet can only contain the questions that exist. The sheet now says so plainly ("6 of the 50 requested; that is every distinct question for this scope") instead of padding, and a **Scope** control widens the pool: this unit, everything taught so far (weeks 1 to this one), or the whole grade. Adding questions to any expectation in Standards grows every scope.
* **D-66 Multiplication and division mix.** The level policy turned the Basic level of every multi-digit multiplication into two-digit-by-one-digit, so single-digit factors dominated. Now Basic is two-by-two (or three-by-two) with small factors, Core is the standard's own size, and Challenge moves up (two-by-two to three-by-two; four-by-one to two-by-two). For long division, the Challenge level with a two-digit divisor now uses larger dividends and remainders. Grade 4 division keeps one-digit divisors because §111.6(b)(4)(E)–(F) limits it to that; Grade 5 uses two-digit divisors.

Test T23 checks no repeated questions in a unit or across a grade, scope widening, no machines outside math, no single-digit factor at any multiplication level, and two-digit divisors at the top division level.

## 00000000. Live sync, Social Studies 1–5, plan rail (v5.7)

* **Teach it live is now synchronized (D-62).** The teacher's deck publishes its state (lesson, slide, revealed answers, revealed steps, flipped cards, finish) over the browser's same-origin channel (localStorage event plus BroadcastChannel). The student window opened with Pop out follows automatically: Next on the teacher's screen advances the board; Show answer, Show step, and Flip all cards reveal on the board; Finish shows the completion card on the board; changing lesson on the teacher's screen switches the board to that lesson. The student window shows "Following the teacher's screen" and keeps its own Next only as a fallback when the teacher's window is closed. Followers never publish, so two windows cannot fight. Test T22 runs a publisher and a follower in the same harness. Limitation: both windows must come from the same file on the same computer or the same site address; a different device on the projector would need a network relay, which this app does not have.
* **Character Traits jump list (D-63).** The Plan view's left rail listed math weeks for every subject. It now lists the selected subject's weeks (the Teach rail already did).
* **Social Studies grades 1–5 loaded** verbatim from 19 TAC Chapter 113 Subchapter A (August 2024 update; adopted 2022, effective 2024–25): §113.12–113.16, 99 knowledge statements. Generated year plans, concept decks, coverage tracking, and teacher questions work for every grade; authored material (big ideas, pictures, questions) exists for Kindergarten and is the next authoring pass for 1–5.
* **ELAR grades 1–5 not loaded in this build.** §110.3–110.7 is the largest elementary document (each grade has roughly a hundred expectations with sub-items). It is one ingestion of one state document in the same format; it did not fit alongside this round's work and is the first item of the next pass. The Standards library shows exactly which packs are loaded so nobody mistakes an unloaded grade for coverage.

## 0000000. Student at the top, grade lock, taught-and-complete sync (v5.6)

* **D-59 Sync.** "Mark this day taught" at the bottom of a lesson (class-level) and "Mark complete for [student]" in the helper card were independent, so a teacher could mark a lesson and see nothing change for the child. Now, with a student selected, the bottom button reads "Mark taught and complete for [name]" and does both in one click (class day taught, standards covered, lesson complete for the student, session logged); if the class day was already taught it reads "Taught; mark complete for [name]". The helper card shows "Class: marked taught" when the day is taught. Math uses the same rule in its lesson drawer.
* **D-60 Persistent student.** A student selector now sits in the header on every screen. With a student chosen, a yellow "Helping [name] · grade · room · homeroom" tag stays at the top with Record and Clear buttons.
* **D-61 Grade lock.** With a student selected, the app shows only that student's grade: other grade buttons are hidden, the grade switches automatically, Home shows one grade card with a note, and every view (Plan, Teach, Assignments, Activities, Progress, Standards) follows. Choosing "No student (show everything)" restores all grades. A student's grade is edited on their record if they work at a different level.
* **Tours updated:** the Home tour explains the student selector and the lock; the Teach tour explains the one-click taught-and-complete; the Progress tour distinguishes class progress from per-student completion.

Test T21: selecting a student forces the grade; Mark taught sets the class day, the coverage status, the student's completion, and a session in both math and a subject; clearing restores.

## 000000. Student records (v5.5)

Built for the special-education reality that the student, not the class, is the unit of continuity: a child arrives from math, science, or another room and the teacher needs to know in seconds where they were helped last.

* **Students tab.** Search by name, homeroom teacher, room number, or any label; cards show grade, homeroom, last lesson opened, the last help note, and counts of completed lessons and notes. Add a student with first and last name, grade, homeroom teacher and number. **Labels for every student:** add any label once (case manager, accommodations, bus, medication time); it appears on every existing record and on the add form for new students, and can be removed the same way. Old per-grade rosters migrate automatically into records.
* **Who am I helping?** Every Teach view (math and every subject) starts with this card. Pick the student (from any grade; a fourth grader can work in a second-grade lesson) and from then on the lesson is logged to their record once per day, the exit ticket attaches with its score, "Log help" saves a one-line note tagged with the lesson, and "Mark this lesson complete for [name]" records it as coursework completed by that student. The card shows their homeroom and labels and where they were helped last, and opens their record.
* **Student record.** Where we left off (the last lesson with its I-can, standards, and date; the last help note; a Resume button that reopens that exact lesson with the student selected); notes timeline with labels (help given, strategy that worked, accommodation, behavior, parent contact, IEP goal); completed coursework across every subject; every session (lesson opened, exit ticket, help given); the standards the student has worked on, by subject, with counts; edit details; CSV export of the whole record; print.
* **Home** gains a Find-a-student box. Settings points to the Students tab; the old roster textareas are gone.
* Privacy unchanged: records live in the browser and the linked progress file; export is explicit.

Test T20: roster migration, labels applied to existing and new students, cross-grade sessions, once-per-day logging, exit score and help note attachment, completion and coverage, CSV, and all views rendering. Run three times for ordering stability.

## 00000. Round v5.4: Smithsonian removed, teacher guide rebuilt, deck navigation

* **Smithsonian Open Access photos removed** at the user's request: the search returned unrelated collection objects (herbarium sheets and 19th-century engravings for "forces"), because the collection is catalogued by object, not by teaching topic, and keyword search cannot tell a classroom picture from a museum record. The drawn pictures stay; free-image search links and the attach-your-own-photo option stay. Settings no longer has an Image sources section. D-56.
* **Print teacher guide** (D-57): printing the app page itself depended on print CSS and a timer, which produced a page with only the slide chips and, in the user's browser, left the guide hidden afterward. The guide now opens as its own page in a new tab: title, unit, talking points, then every slide with its teacher notes, student response, and the slide's content (vocabulary with definitions, big idea and facts, drawn picture, steps, worked examples with step traces, questions with answers). It has a Print button and works with the browser's own Print; the button in the app works every time. Test T19 opens it for a science deck and a math deck and checks every slide is present.
* **Deck navigation** (D-58): the goal box looked like a button and Next was small and above the slide. Every slide now ends with a large Next (or Finish) on the right and Back on the left, with "Slide n of N · arrow keys work too" between them; the top controls remain. Items on the Today's plan slide jump to that part when clicked, since they looked clickable. The goal box no longer shows a pointer cursor.

## 0000. Feedback round (v5.2): nine items, what changed, what could not be done

| # | Feedback | Change |
|---|---|---|
| 1 | Lessons opened with quiz questions on content students had never seen, and teacher notes were too thin to direct a conversation | Every science unit now carries authored talking points: a hook to open with, three say-lines, two examples, the misconception to listen for, and questions with expected answers. They drive the teacher notes on every slide (goal shows the hook; Big idea shows the say-lines and examples; Look at it shows the misconception; We do shows the questions with expected answers; Wrap-up shows an exit question). The first unit of a subject no longer quizzes: its warm-up is "What do you already know?" with two student-facing prompts, and the hook sits in the notes. Later units warm up with questions from the previous unit only. Talking points also appear on the Plan week card and in the Standards library |
| 2, 3, 9 | Boxes for ice/water/vapor and circles for grass/rabbit/hawk do not teach; use free images | The diagrams are now drawn pictures: an ice cube, a glass of water, a steaming pot; sun, grass tuft, rabbit, hawk; fox, mouse, worm, seeds in the food web; duck, giraffe, hawk, fish for structures; egg, caterpillar, chrysalis, butterfly and eggs, tadpole, frog for life cycles. Science vocabulary cards now carry a picture. For real photographs: every unit links to a Wikimedia Commons search filtered to public-domain/CC0 images and to the NASA image library (public domain), and the teacher can attach a free photo to the unit once (Plan card or Standards); it is stored with the class data and shows on the Look at it slide and the Plan card with its credit line. **What could not be done:** hot-linking verified photo files. This environment cannot query the Commons API for specific files, and I will not guess file URLs, so the app ships with drawn pictures plus one-click free-image searches and the attach feature rather than unverified links |
| 4 | Print all vocabulary at once | Assignments now offers, for math: all vocabulary cards for the grade (whole year) and all words from Kindergarten through the grade; for science: this unit, all words for the grade, and K through the grade. Cards print with the grade the word was introduced |
| 5 | Vocabulary should accumulate across grades, not repeat the same four words | Every science glossary term is tagged with the grade that introduces it. Each unit shows its new words as cards and lists earlier-grade words under them as "Words we learned before"; the Plan card lists both; the cumulative card sheets print in grade order |
| 6 | Far more questions, for all subjects | Science: six check questions per unit (288 total, up from 144). Every Kindergarten subject now has a question bank: ELAR (36), Social Studies (45), Health (42), PE (48), Art (12), Music (12), Theatre (15), Technology Applications (24). They flow into warm-ups, We do / You do, practice, exit checks, and sheets exactly like the science ones, and teachers can add more on any expectation |
| 7 | Balance machine tilted the wrong way | The heavier pan now goes down, the beam is drawn from the real values (no padding), and the readout says which side is heavier and what to add to balance |
| 8 | Read-aloud sounded like a robot regardless of speed | Removed entirely: buttons, settings, voice picker, automatic reading, stop control |
| 10 | The star counter was unexplained | It now has a tooltip, opens an explanation when clicked (class stars for correct answers in Practice and Exit tickets; a motivator, not a grade), and Home mentions it |

### Accuracy checks on the new material
Talking points were checked against the standard's own examples and the facts already audited (v5.1). Grade 1 unit 6 hook uses an ice cube and a toy with parts, which is the standard's own illustration; K unit 7 misconception (magnets pull all metals) uses an aluminum can, which is correct; Grade 4 unit 9 corrects the "Earth's shadow makes the phases" misconception with the lamp-and-ball model, which is the standard demonstration. K-subject questions use only the wording and examples in each standard (holidays, historical figures, senses, locomotor skills, elements of art, the five voices, dramatic play, decomposition).

### Bugs found in this round
| ID | Bug | Fix |
|---|---|---|
| D-52 | New icon library collided with the math engine's ICON object, breaking item-group drawings and step traces | Renamed |
| D-53 | First-unit warm-up displayed the teacher's hook as a student prompt | Student prompts on the slide, hook in the notes |
| D-54 | We do listed the same question twice in two wordings | Shows the expected-answer questions only |

### Remaining, stated plainly
Photographs still require the teacher's one click and attach. K-subject units have questions but not yet authored big ideas, facts, or pictures; that authoring uses the same format as science and is the next pass. Non-science glossaries do not exist yet, so K-subject vocabulary cards are empty until authored.

## 000. Science material build (v5.1): what was added, and the accuracy and UI audit

### Added
* **Authored teaching material for every science content knowledge statement, K–5** (48 units): a big idea in kid language, three or four key facts, vocabulary from the science glossary, a drawn visual, a hands-on activity built from the tools the standard itself lists (windsock, stream table, circuit parts, balance), two discussion questions, and three check questions with explanations (144 in all). Material appears on the Plan week card, in the lesson deck (Big idea with facts, a new "Look at it" slide, the activity as the I do, discussion in We do, questions in You do and the warm-up), in Practice and the exit check, on question sheets, and in the Standards library under each knowledge statement.
* **43 drawn visuals** in code (SVG, scale to any screen): day and night, seasons, the solar system in order, Sun and Moon, Moon phases, Earth's rotation and shadows, the water cycle, weather tools and a weather graph, states of matter, heating and cooling, reversible and irreversible changes, mixtures and solutions, magnets, push and pull, collisions, forces, balanced forces, energy forms, closed and open circuits, light paths, shadows, sound, soil and water, rapid Earth changes, landforms, fossil layers, earth materials, water conservation, reduce/reuse/recycle, resources and their uses, renewable vs nonrenewable, plant needs, plant parts, food chain, food web, ecosystem, animal structures, butterfly life cycle, inherited vs acquired traits, sorting by property.
* **Public image sources** attached to each visual for real photographs on a second screen: NASA Science and NASA Space Place, USGS Water Science School, NOAA SciJinks and the National Weather Service, Texas Parks and Wildlife education, USDA, the Bureau of Economic Geology, and Wikimedia Commons media searches (public-domain and Creative Commons). Links are to stable topic pages and searches, never to guessed file names.
* Subject drop-down shows subject names only.

### Accuracy audit of the material (checked line by line against the standard and general science references)
Verified: Moon phases repeat about every 29.5 days and moonlight is reflected sunlight; Earth rotates once in about 24 hours and shadows point away from the Sun and are shortest at noon; planet order Mercury to Neptune; the Sun is a star; solids keep shape, liquids and gases take the container's shape; matter is conserved in mixtures and solutions; metals conduct, rubber and plastic insulate; a circuit must be closed; light travels straight, reflects, refracts, is absorbed; sound is vibration; weathering breaks, erosion moves, deposition drops; weather vs climate; renewable vs nonrenewable examples match the standard's own list; producers use sunlight, water, and carbon dioxide; decomposers return matter; inherited vs acquired examples; instinctual and learned behaviors use the standard's own examples (turtle hatchlings, orcas). Two corrections made during the audit: the first shadow drawing had rays passing through the blocking object (D-45), and the first rotation drawing had shadows pointing toward the Sun (D-46).

### Bugs found and fixed
| ID | Found | Fix |
|---|---|---|
| D-45 | Shadow drawing: rays passed through the object | Blocked rays stop at the object; the shadow on the wall lies between the unblocked rays |
| D-46 | Rotation drawing: morning and evening shadows pointed toward the Sun | Reversed; Sun placed east in the morning and west in the evening |
| D-47 | Moon phase drawing: crescents and gibbous shapes were geometrically wrong | Redrawn from the lit-half plus terminator ellipse; waxing lit on the right, waning on the left |
| D-48 | Labels overlapping in eight drawings (seasons, solar system, states of matter, water cycle, light paths, collision, ecosystem in dark soil, plant needs) | Repositioned, staggered, or recolored |
| D-49 | The same check question appeared in We do and You do | You do draws from the remaining questions |
| D-50 | I-can statements cut mid-phrase ("movement of water above.") | Shortening now cuts only before a new verb clause |
| D-51 | Drop-down carried "(standards + generated plan)" | Names only |

### UI/UX findings, remaining
1. A unit's big idea combines all of its expectations into one sentence (Grade 4 Earth: water cycle, slow changes, weather vs climate). Per-day big ideas, one per expectation, would be better for students with LD. Authoring task.
2. The "Look at it" drawings are schematic. Real photographs open from the teacher notes, which means a second screen or a switch away from the deck. Embedding public-domain images offline would require shipping image files; the PRD's Phase 2 lists it.
3. Kindergarten non-science subjects still teach from the standard's own wording. The material format is proven for science and is the next authoring pass (Social Studies K first: flags, needs and wants, maps, jobs, rules).
4. Warm-up on week 1 of a subject uses the same unit's questions (there is no previous week). Acceptable; a "welcome" retrieval set is a nicety.

## 00. Multi-subject build (v5): what was built, what was tested, what was found

### Built
* **Standards library** (new view): all 12 chapters the State Board lists for K–5 (plus the Fine Arts disciplines split out), each with the TEA chapter index, the Subchapter A PDF, the compiled grade PDF (June 2024), the Texas Register web version, and the revision page. Loaded verbatim from the state documents: Mathematics K–5, Science K–5 (§112.2–112.7, 2021, effective 2024–25), and every Kindergarten subject (ELAR §110.2, Social Studies §113.11, Health §115.12, PE §116.12, Art §117.102, Music §117.103, Theatre §117.104, Technology Applications §126.6 as printed §126.1). 20 subject-grade packs, 755 student expectations, codes unique. LOTE (§114.4) and CTE (§127) recorded as informational with the reason.
* **Coverage tracking** per student expectation: not started, covering, covered, mastered, with date and evidence; auto-advanced by lessons (viewed → covering, taught → covered) with manual override that never regresses; roll-ups by strand; CSV export; printable report. Math coverage auto-populates from the existing 1,080 lessons.
* **Teacher-authored questions** on any expectation (multiple choice or short answer, three levels), persisted with everything else, flowing into the deck's We do / You do, practice, exit checks, and question sheets.
* **Generated year plans** for every loaded non-math pack: 36 weeks, one knowledge statement per week, one student expectation per day, practice standards paired daily, spring repeats to reteach; **concept lesson decks** using the same routine (plan, goal, retrieval, words, word check, big idea, steps, I do, We do, You do, find the mistake, wrap-up); subject-specific steps and watch-outs; a 70-term kid-language science glossary; rubric checks where no items exist.
* Subject switcher in the header; subject-scoped progress; subject-aware TEKS popovers; student window carries the subject.

### Tested, three perspectives
| Perspective | What was exercised | Result |
|---|---|---|
| Developer | Suite of 16 test groups (T1–T16): 627,600 generated math questions, 22,680 sets with no repeats, 11,250 arithmetic recomputations, 1,080 math decks, 560 concept decks across science K–5 and eight K subjects, coverage transitions, bank persistence, subject-scoped storage keys, student-window subject routing, standards integrity (20 packs, unique codes, math grouped, links well-formed) | all passing |
| Teacher | Switched subject to Science grade 3; opened Standards; changed a status and wrote evidence; added three questions to 2.8A/B; opened Plan (week cards with codes and paired practice standard), Teach (deck with the bank questions in We do / You do), Assignments (question sheet, vocabulary cards, rubric checklist), Progress (subject-scoped grid); exported coverage CSV; opened every state link | works; findings below |
| Student | Opened the science student window for a lesson; read the goal, words, big idea; answered bank questions with read-aloud; saw rubric text when no items | works; findings below |

### Bugs found in this pass and fixed
| ID | Found by | Bug | Fix |
|---|---|---|---|
| D-39 | Teacher | The agenda slide showed the week's first goal while Today's goal showed the day's expectation | Agenda now uses the day's goal |
| D-40 | Student | I-can statements built from long expectations ran to three lines | Automatic shortening at "such as", "including", and the second clause when over 90 characters |
| D-41 | Teacher | Coverage legend read "Mastered: 1 45 expectations" | Total labeled and separated |
| D-42 | Teacher | Practice standards (x.1–x.5 in science, social studies skills) showed "Not yet placed in the plan" although they are paired with every content day | Label reads "Integrated: paired with content lessons" |
| D-43 | Developer | Concept deck's Find-the-mistake slide reused the math slide type and crashed without a generated question | Own slide type with the steps as the fix |
| D-44 | Developer | Subject select population assumed a real `options` list | Guarded |

### Areas for improvement (not fixed in this pass, ordered by value)
1. **Generated plan sequencing.** Non-math plans cycle content knowledge statements evenly; a real scope-and-sequence (seasons in the right months, units of unequal length) needs teacher-editable order and week weights. Recommended next: drag-to-reorder weeks and a per-week "days" count.
2. **Item packs.** Non-math subjects have no authored questions yet; everything scored depends on the teacher bank. Phase 2 authors Science K–5 packs (≥3 items per expectation).
3. **Grades 1–5 for ELAR, Social Studies, Health, PE, Fine Arts, Tech Apps** are not loaded. The parser format is fixed; each compiled grade PDF is one ingestion. The status board in Standards shows exactly what is loaded so no one mistakes a missing pack for coverage.
4. **Tracking clarity.** Three status systems now exist (day taught, per-student exit scores, per-expectation coverage). They are consistent but shown on different screens; a single "What is left?" panel on Home listing not-started expectations per subject would answer the most common question in one place.
5. **Comprehension for students.** Concept decks explain from the standard's own words. For K–2 that language is above grade level; a per-expectation kid-language "What we do" line, like the math I-cans, is the next authoring task.
6. **Performance subjects.** PE, Music, Theatre, and Art checks are rubrics; the deck's I do / We do prompts are generic. Subject-specific cue-word libraries would make them teachable without prep.
7. **UI density in Standards.** Long grades (ELAR K has 12 knowledge statements with sub-items) produce long pages; collapse-by-strand and a "show only not started" filter would help.
8. **Read-aloud** of standards text is available but the text is legal language; pairing with the kid-language line (item 5) matters more than the voice.

## 0. Instructional review for students with learning disabilities (v4)

The honest finding first: the previous "Teach it live" was a question projector with an answer button. It had no vocabulary, no modeling, no step-by-step process, no memory devices, and no routine. A teacher would not learn how to teach the skill from it, and a student with a learning disability would learn little from it. Every module was re-reviewed against evidence-based practices for that population: explicit and systematic instruction, gradual release (I do, We do, You do), concrete-to-representational-to-abstract sequencing, pre-taught vocabulary with examples and non-examples, retrieval practice, mnemonics, immediate corrective feedback, and predictable routines.

### What changed, by module

| Module | Finding | Change | Test |
|---|---|---|---|
| Teach it live | Random questions, answer reveal only | Replaced by an 11-slide lesson deck with the same routine every day: Today's goal; Warm-up retrieval (last week's skills); Words we need (index cards: word, picture, kid-language meaning, example, "not this"); Word check (meaning to word); Remember it (memory device for the skill family, letter by letter, with a chant); How to do it (color-numbered steps and the common mistake); I do (worked example, one step revealed at a time, teacher thinks aloud); We do (same steps, class predicts each next step); You do (two problems with answer and steps revealed after whiteboards); Find the mistake; Wrap-up (goal, word cards, tomorrow). Every slide has a teacher script and a student response prompt. Teacher notes never appear in the student window. Print teacher guide prints the whole script | T13: 540 decks, 5,940 slides |
| Definitions | Vocabulary was a comma list | Glossary of all 325 terms in the plan: definition in kid language, example, "not this", and a picture for 250 of them. Cards in the deck, definitions listed on every Plan week card, printable index-card sheets in Assignments | T12: 325 of 325 |
| Memory devices | None | 28 devices covering every skill family (DMSB, PEMDAS with the left-to-right caveat, CUBES, the alligator, rounding rhyme, regrouping rhymes, N-Up D-Down, Split-Multiply-Add, and so on), each with letters, meanings, a chant, and a self-check. Every one of the 540 days carries at least one | T13: 540 of 540 |
| Step-by-step | Answers appeared with one explanatory sentence | A solution trace for every one of the 105 skills at every level (column addition and subtraction with regrouping named per place, partial products, DMSB per chunk including "can it go in?", common-denominator renaming, decimal placement with an estimate check, CUBES on every word problem, and so on). Traces drive I do and We do, appear under every wrong answer in practice, and are available on demand with "Show me the steps" | T12: 7,800 traces |
| Practice | Hint and answer | Hint, Show me the steps, Read aloud on every question; wrong answers show the full trace, not just the answer | T7 |
| Warm-up | Mixed difficulty | Retrieval at basic level from last week, so the first minutes succeed | — |
| Assignments | Worksheets only | Vocabulary index cards (front word and picture, back meaning); Steps and memory-device card to keep on the desk; "My steps" box under each problem | T13 |
| Plan | No definitions, no devices | Vocabulary with definitions and the week's memory devices on every card | T7 |
| Accessibility | None | Text size (normal, large, extra large); dyslexia-friendly text (wider spacing, cream background, no italics); high contrast; reduced motion; read-aloud button on every question and slide, plus automatic read-aloud of slides using the browser voice | T13 (read-aloud guarded when no voice) |
| Composing examples | Kindergarten "5 = 0 + ?" appeared as a taught example | Zero parts removed from examples; improper fractions are also shown as mixed numbers in step traces | Visual review |

### Review by role

* **Teacher (general education).** Can now teach from the deck without prior planning, and the year is complete (fall introduces, spring reteaches and applies): the script says what to say, the prompt says what students do, the guide prints. Remaining gap: pacing timers per segment are not built in.
* **Special education teacher or co-teacher.** Explicit routine, gradual release, vocabulary with non-examples, retrieval, mnemonics, corrective feedback, and accommodations are present. Remaining gaps: no IEP-goal tagging beyond the free-text note labels; no data on time-to-answer; no speech-to-text for student responses.
* **Student.** Same routine every day, one idea per slide, big text, pictures with words, color-numbered steps, read-aloud, "Not this" boundaries. Remaining gaps: no self-paced audio narration of steps in the student window; machines still require fine motor control on sliders (keyboard arrows work on all sliders).
* **Paraprofessional or aide.** Steps card and vocabulary cards give a paper anchor for small-group reteach. Remaining gap: no reduced-item worksheet preset (use Questions = 5 with the "My steps" box).
* **Parent.** The single file opens at home; the vocabulary cards and steps card are the homework companions. Remaining gap: no Spanish version of the glossary yet.

### Not done, stated plainly

Speech recognition, synchronized teacher-and-student windows, IEP goal reports, a Spanish glossary, and per-segment timers are all outside this build. Each is feasible without a server except live synchronization across devices.

## 1. Defect log

| ID | Reported by | Defect | Root cause | Fix | Verified by |
|---|---|---|---|---|---|
| D-01 | User screenshot (K week 7 exit ticket, "What shape is this?" × 3, all circles) | Same question repeated inside one set | Questions were generated independently; no set-level uniqueness; shape set had 4 answers and one question form | New `makeSet()` builds every set through a signature (prompt + picture + answer) and rejects repeats; a repeated MC answer is also discouraged; when a skill runs out of unique questions the set is shortened and the user is told — a repeat is never returned | T2: 11,340 generated sets, 0 duplicates |
| D-02 | Audit | Small answer spaces (banks of 3–5 items; `compose`, `maketen`, `halves`, `coinname`, `unitfrac`, `angle`, `benchmark`) made D-01 inevitable for 12-question practice | Content, not code | Every bank raised to 7–12 items; new question forms added (pick-the-picture, real-world object, how-many-sides, three equation forms, random unequal partitions on three shapes); set builder widens to the rest of the week's skills before shortening | T2 shortened-set count 41 of 11,340, all "All basic" whole-week 30-item worksheets in weeks with inherently small spaces (e.g., K week 1, counting to 5) |
| D-03 | User | Learn section was one example at one difficulty; plans "superficial" | No difficulty model | Three-level policy per generator (Basic / Core / Challenge, never above the grade's TEKS ceiling); Learn now shows Big idea → numbered "How to do it" steps → "Watch out" common mistake → three worked examples easy-to-hard with answers and reasoning, plus "Show three more examples"; practice is 12 items with mode selector (Easy-to-hard, All basic, Mixed, All challenge); exit ticket is one item per level | T3 (level scaling), T6 (every week has all four teaching fields) |
| D-04 | User | No way to save place or track progress | No persistence layer | Progress store in browser storage (`lwmg.progress.v2`): per-day viewed / taught / best exit-ticket score / attempts / date, per-week notes, last position, star total. Teacher dashboard shows an 18×5 grid per grade with status, percent taught, notes, right-click toggle, "Mark week taught", "Resume where I left off" | T7 storage round-trip |
| D-05 | User | No export/print of exercises | Not built | Worksheet builder: week, day or whole week, 10–30 items, four difficulty modes, pictures on/off, answer key on a separate page, level badges, hints; Print, Download HTML (standalone), Download CSV; progress Export/Import JSON; "Print overview" on dashboard | T7 worksheet render, manual print-CSS review |
| D-06 | Audit | Multiple-choice checked answers by comparing `innerHTML` strings, which browsers normalize (entities, SVG attributes) | Fragile comparison | Compare by option index | T1 (answer present in choices), T7 |
| D-07 | Audit | "Value of the digit 7 in 77,077" was ambiguous; place names stopped at thousands | Generator | Only a digit that appears once is asked; place names extended to billions | T1 fuzz |
| D-08 | Audit | `normRaw` stripped every comma, so `(3, 5)` failed to match `3,5` | Over-broad regex | Only thousands separators are stripped | T5 |
| D-09 | Visual review | Area-model picture showed the partial products the question was asking for | Visual leaked answer | Products hidden unless the prompt already lists them | Gallery render |
| D-10 | Visual review | Rounding number line labels wrong (6.00 / 6.50 / 7.00 for "round 6.099") | Label arithmetic | Corrected to 6.00 / 6.05 / 6.10 | Gallery render |
| D-11 | Visual review | Place-value chart labels clipped; area-model left labels clipped; long-division bracket depended on CSS grid; volume drawing unreadable | Layout | Two-line labels, left margin, SVG bracket, three-face unit-cube drawing | Gallery render |
| D-12 | Test suite | New bracket referenced an undefined color (`C.grape`) | Typo | Fixed | T1 caught it (3,960 flags → 0) |
| D-13 | User screenshot (Grade 5 week 5, division machine cells misaligned and drawn as pills) | Long-division grid cells rendered with borders, padding, and 100 % width | CSS class collision: the teacher-dashboard day cell and the division-machine cell were both named `.cell`, so the dashboard's button style applied to the machine once both lived in one file | Dashboard cells renamed `.dcell`, machine cells `.ld .ldc`; new test T9 parses the stylesheet and fails if any component class is redefined under another component | T9 |
| D-14 | Build audit | Single-file build died with `SyntaxError: Unexpected EOF` — a literal `</script>` inside a JavaScript string terminated the inline script block | HTML parser rule | String split so the sequence never appears literally; folder build unaffected | Headless render of the single file |
| D-15 | Compatibility audit | `NodeList.forEach`, `Array.fill`, `String.padStart`, `Number.isInteger` fail on older school-issued browsers | ES2015+ APIs | Replaced with ES5 equivalents across engine and app; code is now plain ES5 | Static grep, headless render on a 2014-era WebKit |
| D-16 | User | Three separate HTML files were confusing; no way to change the teacher's name; no roster; no assignment library | Product structure | One app with six views; Settings holds teacher name, class label, projector mode, rosters, backup; Teach records exit-ticket scores per student; Assignments saves generated sheets for identical reprints | T7 |
| D-17 | User | No way to unmark a day marked taught; the only toggle was an undiscoverable right-click | Missing affordance | Every day cell in Progress opens a menu: Open this lesson, Mark / Unmark as taught, Clear exit-ticket scores, Reset to not started. Week rows toggle Mark week taught / Unmark week. The teacher panel button flips between Mark and Unmark | T7 |
| D-18 | User | Progress did not survive moving the app to another folder or computer | Browser storage is scoped to the browser and, in Firefox, to the folder | Progress file: Settings links a JSON file through the File System Access API (Chrome, Edge); every change is written to it and a Reconnect bar loads it on the next open, newest-wins by timestamp. Browsers without the API keep Export / Import. Data from the previous storage key migrates automatically | T7 (timestamp, migration) |
| D-19 | User | Activities showed the same three tools regardless of grade or lesson, and was confused with Assignments | Not lesson-aware; no orientation | Activities takes week and day and rebuilds the projector set, practice round, and machines for that lesson; Division Factory appears for grades 4 and 5. A context bar under the header states the grade, the current job, and one line about what the screen does | T7 |
| D-20 | User | No onboarding; grade and view navigation unexplained | No Home, no tour | Home view (choose a grade, then one of five jobs, with progress and storage status). Thirteen-step guided tour with spotlight and tooltip: Esc, Skip, or Finish closes it; a checkbox in the tour and in Settings controls whether it opens on the next load; "? Tour" reopens it any time | T7 runs every tour step through the real render path |
| D-21 | User | "Grade:" label sat on the first header row while the grade buttons wrapped to the second | Single flex row | Header is now two explicit rows: brand + views + stars, then Grade: + grade buttons + week + For teachers | Render |
| D-22 | User | Plan required scrolling through 18 week cards | No index | Sticky "Jump to week" rail on the Plan page scrolls to the card and flashes it | T7 |
| D-23 | User | Machines existed only for division and sharing; long-division machine defaulted to two-digit divisors | Two ad-hoc machines | 24 machines covering every strand K-5 with a generator-to-machine map; every one of 540 days has at least one; the long-division machine has a 1-digit / 2-digit divisor toggle on every grade | T10 |
| D-24 | User | Screen sharing exposed teacher-only material | No student surface | Student window: the same app opened by URL in student mode (no header, navigation, TEKS chips, teacher panel). Pop-out buttons on the Teach bar, on Teach it live, on every machine, and on "all machines" | T11 (5 modes) |
| D-25 | User | "Close" item in the day menu did nothing visible | Redundant control | Removed; click outside or Esc dismisses, and the menu says so | T7 |
| D-26 | User | One note box per week | Single string | Any number of notes per week, each labeled General, a day, or a roster student, dated, deletable; old single notes migrate into the list | T11 |
| D-27 | User | Print overview printed empty note boxes and "Mark week taught" buttons | No print rules | Print shows a header (title, class, date), the status grid, and every note as a list; buttons, selects, and forms are excluded; "No notes." prints where a week has none | Print CSS review |
| D-28 | User | TEKS chips showed a "?" cursor and no reliable information; process standards (5.1E) had placeholder text | Tooltip only; placeholder | Chips are buttons: click opens the rule text, whether it is a process standard, the weeks that teach it, and links to the TEA PDF and Chapter 111 index. All seven process standards now carry their official wording | T11 |
| D-29 | User | Only one tour, from the Home page | — | Six page tours (Plan, Teach, Assignments, Activities, Progress, Settings) from "? Tour of this page"; the Home "? Full tour" and first-run tour remain the full walkthrough | T11 runs every step of every page tour |
| D-30 | User | Title hard-wired to one teacher | — | Title is "Learning with my teacher"; an optional name in Settings makes it "Learning with my teacher, Name" on every screen, printed sheet, and the Division Factory | T11 |
| D-31 | User | Pictures overflowed their cards (place-value chart in a vocabulary card, index-card fronts) | Fixed-size SVG | Every drawing keeps its viewBox and now scales to its container (`svg{max-width:100%;height:auto}`); stacked algorithms scroll instead of spilling | Render |
| D-32 | User | Read-aloud could not be stopped and sounded robotic | No stop control; first available voice used | Every Read-aloud button toggles to Stop, and a floating Stop-reading button appears while speaking. The app now scores the computer's installed voices and picks the most natural one (Edge and Chrome on Windows and Chromebooks ship natural voices; Firefox on Linux only has a robotic one). Settings has a voice picker with a test sentence, speed, a plain note about which browsers sound natural, and a switch to hide all read-aloud buttons. No internet service is used; voices come from the computer, so quality cannot be improved beyond what the browser provides | T14 (guard), manual |
| D-33 | User | Teach it live gave students no preview of the lesson | No agenda | Slide 1 is now "Today's plan": every slide listed in order with a one-line description. A clickable strip of all slides sits above the deck showing done, current, and upcoming | T14 |
| D-34 | User | Steps in I do / We do were all visible at once and the "Show step" button changed nothing | CSS: `.steps2 li{display:flex}` outranked `.hid{display:none}` | `.hid` is now `!important`; steps reveal one at a time as designed | Render |
| D-35 | User | Finish did nothing | Placeholder text | Finish shows a completion card with Go to independent practice (scrolls there, or opens the student lesson window), Restart the lesson, and Mark this day taught (teacher) or Close this window (student) | T14 |
| D-36 | User | Assignment type did not control the form (Vocabulary cards still asked for a question count and difficulty) | Static form | The type drives the form: Vocabulary cards show only week, title, and pictures; Steps card shows week, a single day, and pictures; question sheets show everything. A one-line description explains each type | T7 |
| D-37 | User | "Review: this week + last week" produced almost nothing from last week | Specs concatenated this-week-first, so the first 15 draws were all this week | Specs are interleaved (this week, last week, this week...) and the fallback pool covers both weeks | T14: a 15-item review drew from both weeks |
| D-38 | User | Only a fall semester existed | 18 weeks per grade | Full year: 36 weeks per grade, 1,080 daily lessons. Fall (1-18) introduces every standard, as before. Spring (19-36) runs reteach-extend-apply cycles over the fall units (reteach A, reteach B, connect, apply in word problems, check), STAAR readiness weeks for grades 3-5 (test vocabulary, timed mixed sets, distractor analysis), and a year-end celebration week. Each spring week cites its fall source weeks, inherits their TEKS, vocabulary, materials, steps, and watch-out, and reuses their skills at the higher levels. Plan filters Fall / Spring; rails, selects, and progress are grouped by semester; totals are out of 180 | T6, T13 |

## 2. Architecture (v3)

```
content (Python, build time)              shipped files (static, no server, no build step for teachers)
────────────────────────────              ─────────────────────────────────────────────────────────────
teks_k2.py / teks_35.py  ─┐               data.js     6 grades × 18 weeks × 5 days, TEKS text, focal areas
plans_k2.py / plans_35.py ├─ build_app ─► engine.js   105 generators, 27 banks, SVG builders, level policy, makeSet()
map_k2.py / map_35.py     │               app.js      Plan · Teach · Assignments · Progress · Activities · Settings
watch.py                  ┘               styles.css  one stylesheet, component-scoped class names (T9)
                                          index.html  shell; manifest + sw.js make it installable and offline when hosted
                                          activities/division.html  Division Factory (embedded as a template in the single file)
```

* **Deployment options with zero dependencies:** double-click `index.html`; or host the folder on any static host (GitHub Pages, Netlify Drop, an nginx web root) and share one link with other teachers, where it installs like an app and works offline; or `python3 -m http.server` for a classroom LAN. The single-file build is the same app for email or USB.
* **Data model:** one JSON document per browser (`lwmg.v3`): settings, rosters, per-day status, per-week notes, per-student exit-ticket results, saved assignments, last position. Export/Import moves it between machines. Progress from the previous version (`lwmg.progress.v2`) is migrated automatically.
* **Naming:** Settings → Teacher name rewrites the title, assignment headers, and the Division Factory copy, so the same build serves any teacher.

* **Content is data.** 108 weeks × (I-can, big idea, 3–4 steps, watch-out, 5 days × skill specs). A day is a list of `[generator, params]`. Nothing in the views knows about a specific grade.
* **Generators are pure functions** `params → {q, type, a, choices?, hint, explain, vis}` and are testable in Node without a browser.
* **Difficulty is a policy, not a rewrite.** `LVL[generator](params, level)` narrows or widens params; the week's spec is the ceiling.
* **Sets are built, never sampled.** `makeSet(specs, count, levels, pool)` guarantees uniqueness and reports when the space is exhausted.
* **Progress is a JSON document** that can be exported and imported between devices; nothing depends on a server.

## 3. Automated test matrix (final run)

| Test | What it checks | Result |
|---|---|---|
| T1 | Every skill spec in all 540 days × 3 levels × 40 draws: no exception, answer present in choices, no `undefined`/`NaN` in prompts, answers non-empty | **PASS** — 81,840 questions, 0 exceptions, 0 flags |
| T2 | Practice (12), exit ticket (3), and whole-week worksheet (30) sets for every day, 10 trials: no duplicate question in any set | **PASS** — 11,340 sets, 0 duplicates, 41 honestly shortened |
| T3 | Challenge level is never easier than Basic for scaled generators; long division only has remainders at Challenge | **PASS** — 15 generators × 300 draws per level |
| T4 | Answers recomputed independently for arithmetic generators (add, subtract, multiply, divide, decimals, fractions, order of operations, volume, perimeter, unknowns) across all levels | **PASS** — 11,250 problems, 0 mismatches |
| T5 | Answer matcher accepts `76 R 5`/`76r5`, `3/4`/`6/8`, `2 2/3`/`8/3`, `(3, 5)`/`3,5`, `$4.80`, `4,896`; rejects wrong values | **PASS** — 15 positive, 6 negative |
| T6 | 6 grades × 18 weeks × 5 days; every week has I-can, big idea, steps, watch-out; every TEKS code resolves to official text | **PASS** |
| T7 | Full app executed against a fake DOM: Plan (4 tabs), Teach, drawer, Assignments, Progress, Activities, Settings for all six grades; roster scores recorded; teacher rename; saved-assignment serialization; storage round-trip | **PASS** |
| T7 (extended) | Home view; day menu mark / unmark / clear; Activities rebuilt for two different week-day selections; all 13 tour steps executed; save() timestamps; migration from the v2 storage key | **PASS** |
| T10 | Every day has a machine; all 24 machines build; every generator and knowledge bank maps to a machine; machine drawings balanced and free of NaN | **PASS** |
| T11 | Student window in all five modes; multi-note cell and migration; TEKS text present for every chip including process standards; all six page tours; generic and named title in the app and on worksheets | **PASS** |
| T12 | Glossary covers every plan term; every picture renders; a step trace exists for every generator at every level (7,800 checked) | **PASS** |
| T14 | Review sheets draw from both weeks; agenda slide lists every slide; nav strip renders; spring plan shape (STAAR and year-end weeks in place) | **PASS** |
| T13 | Lesson deck builds for all 1,080 days with a script on every slide; Teach and student live views render; index-card and steps-card sheets generate | **PASS** |
| T15 | Standards library: 14 chapters with TEA links, 20 subject-grade packs verbatim, codes unique, math grouped by knowledge statement | **PASS** |
| T16 | Subject mode: 36-week generated plans place every content standard; 560 concept decks build; views render; coverage auto-advances and manual wins; teacher bank flows into decks and persists; student window carries the subject | **PASS** |
| T17 | Authored science material: every content knowledge statement K–5 has a big idea, facts, activity, discussion, glossary vocabulary, a rendering visual, https image links, and valid check questions; material flows into decks and practice (48 units, 144 questions, 43 visuals) | **PASS** |
| T18 | Talking points on every science unit; six or more questions per science unit; question banks for every K subject standard; first-unit warm-up activates; cumulative vocabulary; balance tilts toward the heavier side; read-aloud removed; year and cumulative vocabulary sheets | **PASS** |
| T19 | Teacher guide opens as its own printable page with every slide, notes, and talking points; big bottom Back/Next on every slide; Smithsonian code removed | **PASS** |
| T20 | Students: rosters migrate; labels apply to existing and new; cross-grade sessions; once-per-day logging; exit scores and help notes attach; completion and coverage per student; CSV; views render | **PASS** |
| T21 | Social Studies K, ELAR K, Character Traits K-5: verbatim standards, full material with talking points, six questions per unit, glossaries with pictures, drawn visuals, decks and views render (48 units, 288 questions) | **PASS** |
| T21 | Student selection locks views to their grade; Mark taught marks the class day and the student's completion together; clearing restores | **PASS** |
| T22 | Live sync: teacher deck publishes; student deck follows slides, reveals, steps, and finish; followers never publish; other lessons ignored | **PASS** |
| T23 | Subject sheets never repeat and widen by scope; no math machines under other subjects; multiplication levels never collapse to single digits; two-digit divisors at the top level | **PASS** |
| T24 | Social Studies and ELAR K-5: standards loaded for every grade; questions on every knowledge statement; whole-grade pools of 40+; decks and views render; no duplicate choices | **PASS** |
| T25 | Every subject offers homework, quiz, exit ticket, bell ringer, and in-class practice with keys, hints, badges, titles, and a library; counts to 100; empty subjects removed | **PASS** |
| T26 | Every non-math subject and grade fills 100 distinct questions for every type; vocabulary sheets max at the glossary; subject list follows the grade | **PASS** |
| T9 | Stylesheet parsed: no component class defined bare and again under another component (the `.cell` collision) | **PASS** |
| T8 | Share of practice questions carrying a graphic | 62 % overall (K 60, G1 50, G2 69, G3 62, G4 65, G5 64) — up from 37 % |
| SVG | 204 generated pictures from 68 drawing generators parsed as XML | 0 malformed |
| Visual | Rendered galleries reviewed by eye | D-09 to D-12 found and fixed |

## 4. Known limitations (stated, not hidden)

1. Some TEKS are discussion or performance standards (K.9C job skills, 1.9D charitable giving, 5.10D financial records). They are represented as multiple-choice sorts; the planner's materials and formative check carry the hands-on part.
2. "All basic" whole-week worksheets in weeks with a tiny basic space (K week 1: counting to 5) cap at the number of unique questions available and say so on screen.
3. Data lives in the browser that opened the app; there is no server. Use **Export all data** to move it between machines. Sharing one hosted link with several teachers gives each teacher their own data. A shared class database across devices would need a small backend, which is a deliberate non-goal for a zero-dependency deployment.
4. Binary questions (even/odd, yes/no equivalence) necessarily repeat answers across a set; prompts and pictures still differ.
5. Fonts load from Google Fonts; offline the app falls back to system fonts.

## 5. How to extend

* New skill: add `GEN.name` in `gen_b.js`, optionally a `LVL.name` policy, then reference `["name", {...}]` in a day's spec. The build refuses unknown generator or bank names.
* New week text: `map_*.py` (I-can, big idea, days) and `watch.py` (steps, watch-out).
* Re-run: `python3 build_app.py`, then `node qa3.js`. The 24 machines were also rendered to images and reviewed by eye.
