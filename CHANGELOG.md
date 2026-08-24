# BookyAI Changelog

<!-- Source of truth for the in-app What's new dialog and the GitHub release
     bodies. Format per entry: '## <version> — <YYYY-MM-DD>' then markdown. -->

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
