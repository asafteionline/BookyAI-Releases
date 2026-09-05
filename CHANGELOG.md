# BookyAI Changelog

<!-- Source of truth for the in-app What's new dialog and the GitHub release
     bodies. Format per entry: '## <version> — <YYYY-MM-DD>' then markdown. -->

## 1.9.3 — 2026-09-03

**Appendices that keep up with your chapters**
- When chapters are added, regenerated or reordered, BookyAI now flags the appendices and references as out of date and offers to regenerate them with one click, so endnotes, glossary and discussion guide always describe the current book. Every written chapter now gets its continuity summary (imported manuscripts get theirs on demand), and a full regeneration only rewrites sections BookyAI wrote itself: a preface you imported or wrote by hand is never overwritten
- Front and back matter can be generated for imported manuscripts too: open the book and click Generate appendices

**No more name-dropping, no more invented sources**
- Appendices no longer open with "I, [author], along with [publisher]". Names appear only where a printed book carries them (a preface signature, acknowledgments), at most once, and two new tickboxes in Book details let you decide whether the author and the publisher may be mentioned at all
- Further Reading and Endnotes may only cite works that genuinely exist; anything attributed to your own publisher or to you as a source is removed automatically. The references generator follows the same rule

**Fixed**
- Bold lines or a sub-heading placed right under a chapter title no longer vanish from PDF, EPUB and other exports

## 1.9.2 — 2026-09-03

**Reorder chapters**
- A new Reorder button in the book workspace lets you drag chapters into a new order (or move them with arrows), preview the numbering, and apply. Chapter headings are renumbered automatically, and everything attached to a chapter moves with it: version history, originality and grammar reviews, references, story threads, the audiobook order and every translated edition. One atomic step, with a rollback if anything fails

**Appendices**
- The Introduction (and every other front or back matter section) no longer echoes Chapter 1. The AI now sees Chapter 1 only as a style sample it must not reuse, gets a summary of what the chapters cover instead, and a section that still repeats Chapter 1 is written again automatically
- Edit appendices like chapters: a visible Edit button next to each section opens it in the full editor, with AI rewrite, version history, image insertion and a "Regenerate section" button that rewrites only that section

**Your book remembers its AI engine**
- Books now keep the AI engine they were created with (OpenRouter, Claude, Grok, Gemini or Ollama), and every later operation uses it: regeneration, appendices, references, Quality checks, the editor's AI tools, Codex and translations. Change it any time in Book details under "AI engine for this book". Error messages now name the engine that actually failed instead of pointing at Gemini

**Fixed**
- Tables written a little loosely by the AI (a column mismatch, an unusual divider row, or a table right after a list) now render as real tables in EPUB, Kindle, PDF and HTML instead of a row of pipes and dashes
- The Originality panel in the workspace now opens the Quality review, and the header button is labelled "Quality review", so the originality and grammar checks are easy to find for imported books too

## 1.9.1 — 2026-09-01

**Chapters that never retell the previous one**
- Every chapter is now written with an explicit rule: begin where the previous chapter ended, and never re-narrate a scene, conversation, description or explanation the reader already has. Each chapter's continuity notes record exactly where it ends, so the next one picks up in the right place
- **Non-fiction books get real memory**: BookyAI now keeps a ledger of what every chapter covered — points, examples, advice — and later chapters build on it instead of re-explaining it (previously only chapter titles were carried forward)
- **Automatic repetition check**: after writing a chapter, BookyAI compares it with the previous one; if it repeats passages, the chapter is written again with the copied passages called out, and the less repetitive draft is kept. Applies to first generation and to regeneration
- **Expand and Rewrite in the editor no longer borrow lines**: the AI now sees the text around your selection as off-limits rather than as a style sample, and a result that copies whole sentences from it is redone

## 1.9.0 — 2026-09-01

**Your book, in every language — Editions**
- **Translate a book chapter by chapter** into any of 60 languages from the new *Editions* card in the book workspace. Every edition is a full book of its own in your Library: export it, narrate it, polish it, design it — nothing is left out
- **The editions map**: one row per language, one cell per chapter — translated, pending, failed, or flagged when you've edited the original since (re-translate just those chapters with one click). The map also shows which chapters already have **audio in each language**, with a direct jump to the Audio studio for that edition
- **Translate at creation**: "Also translate into…" in the New Book and Import screens queues languages that start automatically as soon as the book is ready
- Translation is careful by design: chapters translate in passages with continuity between them, character names from your Codex are kept, headings, images and captions are preserved, and a passage is only accepted when it is complete — a chapter is never replaced by a partial translation
- **DeepL as a second engine**: add your DeepL API key in Settings (the free plan covers about one book a month) and pick DeepL per edition. Names are pinned through a glossary, and languages DeepL doesn't offer are translated by your AI provider instead — automatically

**Addressing the reader — "Sie" or "du", "vous" or "tu"**
- Books in a language with formal and informal address get a new option next to the language: Formal, Informal, or let the AI pick one. Whatever you choose is enforced in every sentence of every chapter — and in appendices, Extend, Polish, Rewrite and translations — so texts no longer switch back and forth. Existing books: set it once in Book details

**Import & export polish**
- A manuscript's original title page, copyright line and leftover "Table of Contents" heading are now recognized at import and suggested as "Don't import" — no more duplicate title blocks or a second table of contents in the DOCX
- Captions written across several italic lines now become one centered caption; books imported earlier are healed automatically at export
- Pictures without a caption are no longer shrunk in the PDF — they come out at full width, matching the Word export

## 1.8.5 — 2026-09-01

**Choose your book's trim size — and never fix a stranded heading again**
- **Trim sizes**: pick from eight standard print sizes in Book design — 5×8, 5.25×8, 5.5×8.5, A5, 6×9 (the default), 7×10, 8.5×11 and A4 — each with proper print margins. Your choice drives the PDF pages, the covers and the Word document exactly; images and layout scale to fit. EPUB and Kindle remain reflowable, as they should be
- **Guaranteed formatting at any trim size**: a section heading can no longer be left as the last line of a page — headings always stay with the text that follows them, and no paragraph leaves a single lonely line at a page edge. This is enforced by the layout engine in both PDF and Word, so nothing needs manual placement
- **Page preview**: a new button next to the trim selector renders your real print pages at the chosen size and opens them instantly — see exactly how the book lays out before exporting
- **Re-check originality anytime**: chapters that already have an originality score now offer a *Re-check* button — after a rewrite or expansion, re-run the evaluation with one click (the book-wide check re-scores everything, as before)

**Import & captions**
- **Author comes from your Word file**: importing a manuscript now pre-fills the Author field from the document's own metadata — no more accidental "Anonymous" books (you can always override it in Book details)
- **Manually-centered Word captions are now real captions**: a short italic line under a picture — how captions look when centered by hand in Word — is recognized as that picture's caption and rendered centered in PDF, EPUB, HTML and Word. Books that already imported such captions are healed automatically at export, no re-import needed

## 1.8.4 — 2026-08-31

**Word import & export — verified against a real 26-chapter illustrated manuscript**
- **Fixed the DOCX garbling for good**: pictures that were **bolded** in Word arrived in a form the exporter didn't recognize, so their raw data spilled into the document as endless text — that was the garbling AND the "Word not responding" stalls. Bolded and mid-sentence images now embed as real pictures, books that already imported them are healed automatically on their next export, and a safety net guarantees image data can never appear as text again
- **Front matter finally has a home**: when importing a manuscript, every section now has a destination selector — Chapter, Preface, Introduction, Dedication, Prologue, Acknowledgments, Epilogue, Glossary, or Don't import. Front matter is detected and pre-filled from your section titles, lands in the book's editable matter pages, and **never shifts your chapter numbering or the table of contents**. Text before your first chapter heading is captured too, instead of silently disappearing
- Title page, copyright and table-of-contents pages are suggested as "Don't import" — BookyAI regenerates them at export

## 1.8.3 — 2026-08-28

**Regeneration can no longer destroy your work**
- A failed chapter regeneration now **keeps your existing text untouched** — it no longer replaces a good chapter with a failure notice
- Failures finally **tell you why**: the real error (API quota, key, network) is shown per chapter and in the final status, instead of a silent "pending"
- **Chapter version history**: BookyAI now snapshots a chapter before every regeneration and before edits. The new *Versions* button in the chapter editor lists them — one click restores any previous version (and even restoring is reversible)

**Fixed**
- **DOCX garbled from the first image onward**: an imported image in a format Word can't decode (e.g. WebP) corrupted the export — such images are now converted automatically, at export and at import
- The DOCX export now includes a real **Word table of contents** (hyperlinked; Word fills in the page numbers when you open the file)
- **Word "Insert Caption" captions** are now recognized at import and attached to their image — centered under it in every export, instead of appearing as plain left-aligned text

## 1.8.2 — 2026-08-28

**Your work is safe now**
- **Imported Word manuscripts bring their images along** — pictures arrive automatically into the book (with their alt text as captions), so nobody has to re-insert them one by one. Unsupported or oversized images are skipped with a clear note
- **Vanished books come back**: a book whose internal data file was damaged (crash, full disk, antivirus) used to silently disappear from the Library while all its chapters, images and covers sat safely on disk. It now reappears automatically, rebuilt from its own files — nothing to re-do
- **Deleting a book or series now moves it to the Recycle Bin / Trash** instead of removing it permanently — an accidental delete is no longer a catastrophe

## 1.8.1 — 2026-08-28

**For novelists**
- **Heat level for romance** (1 Sweet → 5 Scorching), set in the wizard or Book details and enforced while writing — level 3 explicitly tells the AI that kisses aren't enough. Note: very explicit levels also depend on your AI provider's content policy; local Ollama models are the most permissive
- **Narration control** for fiction: third person, first person, or **first person alternating between your two leads** — the alternation is enforced chapter by chapter for the whole book, no more drifting back to third person after chapter 3
- **Story-craft outlines**: fiction outlines are now built like a novelist plans — three acts, escalating stakes, no episodic repetition — plus your genre's conventions (fair-play mystery clues and red herrings, romance beats to a satisfying ending, thriller pressure, consistent fantasy rules)
- Chapter recaps now track **where each character is** at the chapter's end, so nobody teleports between chapters
- **Romantic Suspense** is now listed under Romance too

**Fixed**
- **DOCX exports garbled from some chapter onward** on manuscripts imported from Word: invisible Word break characters corrupted the file and Word's "repair" mangled everything after them. Fixed at the source and at export — already-imported books heal automatically on their next DOCX export
- **Image captions now appear in PDF, EPUB and HTML** (they only showed in DOCX) — styled like a book: italic, centered under the image, staying attached to floated images

**BookyAI Audio**
- **Search your books** in Create audio — plus an "Only books without audio" filter and an N-of-M counter, instead of arrow-only scrolling

## 1.8.0 — 2026-08-28

**Characters with real depth**
- Character cards grow up: **profession**, **backstory**, **desires**, **struggles**, **secrets** and a **future arc** — secrets shape behavior in every scene but are never revealed until the story itself does it, and the future field is the destination the AI builds toward without rushing
- **Relationship Network**: define who is what to whom — wife, boss, enemy, mentor… with nuance notes ("estranged for ten years") — and the AI keeps every interaction true to it
- **Relationship map**: your cast drawn live — portraits in circles, directed arrows for every relation, zoom/pan — and a one-click **high-resolution PNG export** with the series title on top
- **Extract from manuscript** now maps the cast AND the relationships in one click, professions and backstories included
- **Arc milestones** (series): anchor character events to volumes — "gets sick and dies in Book 3", "marries in Book 4". Earlier books only foreshadow it, that volume makes it happen, and every later book treats it as permanent fact: a dead character stays dead

**Tables, lists & structure (non-fiction)**
- The AI may now use clean bulleted/numbered lists and tables where they serve the reader — and exports render them beautifully: book-grade table typography in PDF/EPUB/HTML, real Word tables and numbered lists in DOCX
- **Structure button on every chapter**: tell the AI exactly which information to present and in what structure ("compare the 5 tools in a table; end with a checklist") — followed exactly, on generation and regeneration alike

## 1.7.0 — 2026-08-28

**Codex — your book's story bible**
- **Characters, world & knowledge the AI never contradicts**: structured character cards (age, personality, fears…), world entries (places, factions, objects, hard rules) and your own knowledge — paste notes or add .md/.txt files. Everything is sent with every chapter, regeneration, Extend with AI and the outline
- **Extract from manuscript**: one click and the AI reads your chapters and drafts the character cards (your own edits are never overwritten) — works on imported books too
- **AI character portraits** (uses your OpenAI or Gemini key, like covers)
- **Open story threads**: the AI keeps a ledger of promises made to the reader — mysteries, looming conflicts — and honors them chapter after chapter; you can edit the list any time
- **Point of view per chapter**: write any chapter strictly through a chosen character's eyes
- **Consistency check**: the AI rereads your finished chapters against the story bible and flags contradictions ("her eyes were grey in chapter one…") — click a finding to jump straight to it in the editor
- **Timeline**: the whole story so far, chapter by chapter — across a whole series

**Book series**
- **Plan a saga before the first word**: the new *Start a series* flow sets the name, premise, planned arc and writing style; every volume is generated knowing where the story is going
- **Shared series codex**: characters and world travel across volumes; `{{f:key}}` names resolve in every book
- **Previously in the series**: each new volume remembers what happened in the earlier ones — and inherits their unresolved story threads
- Series shelves in the Library, a series workspace page, "Write the next book" pre-filled with the series style
- The wizard can also start a series from any single book, and has a new optional **story bible** box — facts you type there shape the book from the very first outline

**Book design**
- **5 new interior designs**: Storyteller, Scholar, Romance, Noir — and **Ming**, made for Chinese/CJK books (Song/Ming typefaces, wide line spacing, true two-character indents)
- **Custom design studio**: pick the fonts for titles, sub-headings and paragraphs (including Chinese typefaces), text size, line spacing, accent color, chapter openers, indents and drop caps — with a live page preview. Applies to PDF, EPUB, HTML and DOCX

**Also**
- *New Series* and *Extra Device* entries in the sidebar
- Regenerating a chapter now remembers the plot of the chapters before it, not just their titles

## 1.6.6 — 2026-08-25

- **License stability**: a momentary license-server problem could wrongly sign you out and demand your key again at every launch. Server hiccups now never touch your stored license — you get a 30-day offline grace instead — and error messages say what actually happened ("server problem, your key is fine") rather than implying your key is wrong

## 1.6.5 — 2026-08-24

- **What's new dialog**: click the version number in the sidebar to see what each release fixed and added — and when an update is waiting, its notes are shown before you install
- Release notes for every version back to 1.5.0 are published and readable in the dialog

## 1.6.4 — 2026-08-24

**Google Gemini — clearer failures, truthful model list**
- Retired Gemini 1.5 models removed from the automatic rotation (they return 404 for new API keys)
- Error messages now lead with what happened to **your selected model** (e.g. quota exceeded), instead of showing the last fallback's error
- The Gemini model picker loads live from Google using your key — you see exactly the models your key can call

**New**
- **Suggest for this book** (Voice step): AI recommends a writing style & tone from your topic, genre and audience — fully editable
- **Character name variables** for novels: define `john → Jonathan Smith` once, write `{{f:john}}` in chapters; exports and audiobook resolve the names, renaming is a single edit
- **Working title** separated from the content prompt — long prompts never become your book's title; bigger, resizable prompt box
- Older books whose title is the full prompt get a one-click **Suggest short titles** helper

**Fixed**
- Series volumes with continued chapter numbering ("Chapter 21…") now print the right numbers on PDF/HTML chapter pages, matching the table of contents

## 1.6.3 — 2026-08-23

**BookyAI Audio**
- Fixed the "Peak −2.x dB — outside the retail spec" failure that no re-render could clear
- Fixed missing words at the ends of sentences (note: the first render after updating recreates all chapters once — that's the fix cleaning out clipped audio)
- New **Start fresh** button clears cached narration and rendered files safely, keeping your voice settings

**Editing**
- **Front/back matter editor**: edit the Preface, Introduction, Epilogue and other sections in-app (pencil icon in the "Include in book" list)
- **Grammar issues are clickable**: jump from Review straight to the highlighted passage, or work through the new Proofreading panel in the chapter editor with one-click Apply (undo works)

## 1.6.2 — 2026-08-21

**BookyAI Audio**
- Broken narration can no longer be cached: if the voice engine fails, you get a clear error naming the chapter instead of silent audio that fails the retail spec forever
- Re-rendering a chapter now truly regenerates it

**Local models (Ollama)**
- Long chapters no longer stop mid-sentence: BookyAI detects the model's output cap and automatically continues where it stopped
- Generation is streamed continuously — no more timeouts on large (30B+) models on slower hardware

**New**
- **OpenRouter** support: one key in front of 400+ hosted models; default `openrouter/auto` routes each request automatically

## 1.6.1 — 2026-08-18

- **Book language is editable**: click the genre badge on a book's page → Language; regenerating chapters rewrites them in the new language, and AI title suggestions follow it
- **References editor**: review, correct, delete or add bibliography sources per chapter before exporting (References card → Edit references)
- **Export button** on the outline review step (saves the outline as Markdown)
- Stored API keys can now be **removed** (clear the field → the button becomes Remove)
- Clear, actionable error when your OS blocks secure key storage (keys no longer vanish silently on save)

## 1.6.0 — 2026-08-16

- **Extend with AI**: add AI-written chapters that continue any book — including imported manuscripts (your own chapters are never touched)
- **Export PDF for KDP**: the cover wrap builder now exports a print-ready PDF at the exact trim + spine + bleed size Amazon requires
- **Line breaks fixed everywhere**: press Enter once for a line break (e.g. a quote's —Author line); works identically in EPUB, PDF, DOCX, Kindle and HTML

## 1.5.1 — 2026-08-16

- API keys that fail to store now show the real reason (OS secure-storage issues) instead of clearing the field silently
- **Book metadata editor**: genre, sub-genre and target audience are editable on the book's page (click the genre badge)

## 1.5.0 — 2026-08-13

- **Outline review step**: pause after the outline, edit chapters and beats, refine with AI instructions, then approve — the book is written from exactly your outline
- **Voice preview**: hear a ~150-word sample of your book's opening in the chosen style/tone before generating
- Cover wrap fixes: uploaded covers now appear in the gallery (including retroactively), direct front/back upload on the Covers page, and a warning when both wrap sides use the same image
- Book covers now work with a **Gemini key alone** (OpenAI no longer required)
