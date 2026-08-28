# BookyAI Changelog

<!-- Source of truth for the in-app What's new dialog and the GitHub release
     bodies. Format per entry: '## <version> — <YYYY-MM-DD>' then markdown. -->

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
