# BookyAI Changelog

<!-- Source of truth for the in-app What's new dialog and the GitHub release
     bodies. Format per entry: '## <version> — <YYYY-MM-DD>' then markdown. -->

## 1.9.17 — 2026-09-20

**New: the Guide. BookyAI shows you around**
- A "Guide" button sits at the bottom left of the app. It opens "Your first book, step by step": five steps (connect an AI engine, start a book, let BookyAI write the chapters, give it a cover, export it) that tick themselves from what you have really done, with the next one opened and a "Show me how" button. Nothing opens by itself, and every part closes with Escape
- A guided tour for every page: the screen dims, a light moves from one button to the next and a short card explains what it does and when you need it, with tips where they save a mistake. 18 tours: BookyAI in two minutes, the AI engine, the rest of Settings, the Library, the New Book form field by field, importing a manuscript, the book's page, the chapter editor, the Codex, Quality review, the Index, Cover Studio, Authors, Research, planning a series, a series page, Audio and Listen. The tours drive the app for you: the New Book tour walks through all four steps, the Codex tour opens the Codex and goes from section to section. Arrow keys move, and a tour of the page you are on is marked "this page"
- API keys, explained for someone who has never seen one: every key in Settings has step-by-step instructions (what a key is, which page to open with one click, which button to press there, what the key looks like, what to do when something goes wrong). Gemini, Ollama, OpenAI, Claude, Grok, OpenRouter, and the optional keys for covers, translations and fact-checking. With no engine connected, Settings says where to start: the free Gemini key, about two minutes, no card
- The first time BookyAI opens with no book and no engine, a welcome card offers the two-minute tour. If you already use BookyAI you only see the new button

**About the Author is now a section of your book**
- It used to be added at the end of every export from your author profile, whatever you ticked. It is now a row under "Front & back matter" like the others: untick it under "Include in book" to leave it out of this book, move it among the back matter, or edit it for this one book without touching your profile. The edited text is saved as about_author.md in the book's folder; emptied, the book follows your profile again. A book you never touched prints the profile's bio, exactly as before. BookyAI never writes this section
- Translated editions get About the Author in their own language, and what you left out of a book stays out of its translations

**Covers**
- Words on the back cover: the book description and your author bio can now be set over the back cover artwork by BookyAI itself, so every word is spelled exactly as you wrote it, accents included. Under the back cover, "Text" opens them: "Write it with AI" drafts the description from your book, the bio comes from your author profile (or the book's own About the Author), and one tick switches the text off if you add your own in another program. The artwork is always kept on its own, so changing the words never costs a new image. An uploaded or gallery cover is a finished design: text is off for it unless you switch it on
- "Save image" under each cover saves it wherever you want

**Book page**
- The subtitle can be edited in place, like the title; emptied, the book has no subtitle. A file name (from a recording, for example) no longer ends up as a subtitle

## 1.9.16 — 2026-09-19

**OpenAI (ChatGPT models) as a writing engine, and any compatible server**
- OpenAI is now a writing engine like Claude, Grok and OpenRouter: add your OpenAI key in Settings, pick a model (the list loads from your account) and choose OpenAI in the new-book wizard or under "AI engine for this book". Until now an OpenAI key was only used for covers
- New "Base URL" field for OpenAI and for Claude: leave it empty to use OpenAI or Anthropic themselves, or fill it in to use any server that speaks the same API, such as LM Studio, vLLM, llama.cpp, DeepSeek, Mistral, Together or a company gateway. The model list loads from that address, and you can type any model name. A server on your own computer or network needs no key
- Your keys stay where you put them: a key is only ever sent to the address it was saved for. If you change the Base URL, the saved key is not sent to the new address until you save it again, and the field tells you so. The page shows which host your requests and key go to, plain http is refused for addresses on the internet, and errors say what is wrong ("no chat endpoint at this address", "the server rejected the key", "could not reach localhost:1234, is the server running?")
- Covers always use OpenAI itself. Under Extra tools, Covers, there is now a key just for covers; if your OpenAI engine uses the official address, its key is used and that field can stay empty
- As with every paid engine: never used as a silent fallback, "Stay on my engine" is respected, models that think before they write get room on top of the chapter budget, and each chapter shows which model wrote it

**Settings: sections instead of one long page**
- A bar at the top: AI engines, Extra tools, Book defaults, Audio, Listen. Inside AI engines you pick one engine (Gemini, Ollama, OpenAI, Claude, Grok, OpenRouter) and see only what belongs to it, together: key, Save, Test, model and its own options. A dot on each button shows whether it is connected, needs a model, holds a key that is not saved yet, or is not set
- Extra tools holds the three optional keys, each for one feature: Covers (OpenAI), Translations (DeepL) and Fact-check (Perplexity). Nothing else in the app needs them
- "If my engine fails" stays visible under every engine. The Ollama URL moved from Book defaults to the Ollama panel. Buttons elsewhere in the app that lead to Settings open the right section

**Lists that match the app**
- Every drop-down list in the app now uses the app's own menu instead of the one the system draws: same colours everywhere, long lists scroll (an OpenAI or OpenRouter account lists dozens to hundreds of models), typing filters the list, and the arrow keys, Enter and Escape work. Model fields still accept a model name typed by hand, and the OpenRouter list keeps its groups (Free, Discounted right now, A to Z) and prices
- In every menu, the row under the pointer turns green

**Audiobook: the narrator no longer reads citations and leftover codes**
- Source citations are left out of the narration, as in a professionally produced audiobook: "(Covey, 2006)", "(Smith & Jones, 2019, p. 44; Lee et al., 2018)", "Smith et al. (2021, p. 44)", numbered sources such as [1] or [3, 7], and the recording citations of books written from recordings, "(Episode 12, 14:05)". The voice used to read them out, which sounded like a four-digit number added to the end of a sentence. Years that are part of your prose stay: "In 2019", "the film (1995)", "World War II (1939–1945)"
- Formatting codes that come along with text pasted or imported from Word or the web (an invisible space, a special hyphen, a curly apostrophe written as a code) were read aloud as numbers. Every such code is now decoded, and invisible characters are dropped
- Your book and its exports keep their citations; only the narration changes. To apply it, render the affected chapters again: only the sentences that changed are synthesised, the rest comes from the cache

**Authors**
- "Replace" and "Remove" under the author photo and the publisher logo are now two matching buttons side by side

## 1.9.15 — 2026-09-19

**New: a back-of-book index**
- A new Index page (the "Index" button at the top of a book) builds the alphabetical index readers expect at the end of a non-fiction book: people, places, organisations, works, events and ideas, with where each one is discussed. BookyAI reads the book the way a professional indexer would and proposes the headings, with people filed family name first and every wording the text uses for them. A heading the book does not contain never reaches the list, and the subject of the whole book is switched off, as an index never lists it. People and places from your Codex are included for free
- You stay the editor: search and filter the headings, see how often and in which chapters each one is mentioned, rename it, teach it another wording, file it under a broader heading ("taxes: deductions"), merge two headings, add "See also" links, or add a heading of your own and see its mentions at once. Every mention is shown in context, and a click opens the editor on that passage. A preview shows the index as it prints
- It is never out of date: where each heading occurs is worked out from your text at every export. Edit, add or reorder chapters and the index follows. When you add chapters, "Read new chapters" looks at those only and keeps every decision you made
- In the PDF the index prints real page numbers, each one a link to the passage, in two columns with letter headings and subentries. Word gets a native index that Word itself keeps up to date (choose Yes when Word offers to update the fields). EPUB links every entry to the passage; Kindle and Markdown list the chapters. The index sits last in the book, appears on the contents page, and can be unticked or moved under "Include in book"

**Front and back matter: the publishing order, and your own**
- The front matter now follows the publishing standard: Dedication before the contents page, then Preface, Acknowledgments, Introduction and Prologue. Existing books get this order at their next export
- Under "Include in book" every section has a drag handle and arrows: arrange the front matter and the back matter in any order you like. The contents page is part of that list, so you decide where it sits in PDF, Word and HTML. "Standard order" puts everything back
- Three new sections: Epigraph, Foreword and Author's Note. A foreword is written by someone else and an epigraph is a quotation, so BookyAI never writes those two: add them from "Add your own" and paste or type the text. The Author's Note can be written by the AI, and only when you tick it. An imported manuscript's Foreword, Epigraph and Author's Note now land in their own sections
- Acknowledgments and the Author's Note can go after the chapters, as fiction usually has them: move them across the "Chapters" line with the arrows or by dragging
- The card, the dialog and the wizard now say "Front & back matter" instead of "Appendices"

**Front and back matter in the manuscript list, with instructions**
- The Preface, Introduction, Glossary and the other sections now appear in the manuscript list, above and below the chapters, with the same three actions a chapter has: Instructions, Edit and Regenerate
- Instructions are new for these sections: tell the AI exactly what a section must contain and in what structure ("only the 20 most important terms, as a table"). They are followed the next time the section is generated or regenerated; saving them changes nothing by itself

**Editor: a formatting toolbar**
- Familiar icons above the editor: Bold, Italic, Underline, Heading, Bulleted list, Numbered list, Quote, Center, Align right, Scene break, Undo and Redo. Select the text and click; click again to remove it. Cmd/Ctrl+B, I and U work too. A few words selected inside a paragraph and then Heading or Quote become a heading or a quotation of their own
- Underline, centred and right-aligned paragraphs are new and come out in every format: PDF, EPUB, Word, Kindle and HTML. The alignment of ordinary paragraphs still comes from your book's design

**Editorial review: real errors, exact fixes**
- The proofread now separates real errors (grammar, spelling, punctuation) from optional style suggestions, and only errors count. It reads the whole chapter, not just its beginning, no longer looks for a fixed number of problems, and a clean chapter is reported as clean
- "Fix" on an error, or "Fix N errors" for a chapter, replaces exactly the words that are wrong and nothing else, so a fix can no longer introduce new mistakes; the previous text is kept in Versions. "Ignore" dismisses a finding for good. "Polish chapter" now works from the findings and leaves every correct sentence as it is
- The originality score is explained as what it is: an AI opinion on how fresh the writing is, not a plagiarism check
- The "Rewrite with AI" buttons in the editor say that they switch on once you select text and need no extra key

**Word export**
- Page numbers: the DOCX now has a page-number footer, matching the PDF
- Quotations: consecutive lines starting with ">" stay together as one quotation, one line under the other, as in the PDF. Each line used to become a paragraph with space above and below, so verses came out double spaced
- The section break line is now a thin rule that sits close to a heading above it, instead of taking a full blank line

**Translations pick up chapters added later**
- When a book was extended after an edition had been translated, the refresh button did nothing for the new chapters. An edition now takes over the chapters added to its source and translates only those; the finished ones are left untouched. A refresh with nothing left to do says so

**BookyAI Listen**
- "Save to" now starts with "Listen library (no book yet)": transcribe first and decide later which book a recording belongs to. The choice is remembered
- Recordings can be renamed, in the list and in the transcript viewer. The name is updated in the Codex too
- Removing a recording that lives in the Listen library also removes its transcript

## 1.9.14 — 2026-09-18

**New add-on: BookyAI Listen, Speech to Book**
- A new Listen page turns podcasts, interviews, lectures, coaching calls, voice memos and videos into clean transcripts with time stamps, on your own computer. Nothing is uploaded, and there is no per-minute cost. Add files (MP3, WAV, OGG, FLAC, M4A, M4B audiobooks, MP4, MOV and more), a whole folder, a podcast feed with an episode picker, a direct audio link, a public YouTube link, or record straight from the microphone. 99 languages, detected automatically
- Every transcript is filed in the Codex of the book or series you choose, as a knowledge source the AI writes from. With the AI clean-up on, fillers and false starts are removed, punctuation is fixed, and each recording gets a summary, key points, quotable lines with their minute, and chapters. The word-for-word transcript is always kept next to the cleaned one
- A transcript viewer with a synced player: click any paragraph to hear it, the current paragraph lights up while it plays. Export as TXT, DOCX, SRT or VTT
- "Write a book from these": tick finished recordings and the wizard plans the outline around them. Each chapter is written from the passages that match it and cites the recording and the minute, for example (Episode 12, 14:05). Any book whose Codex contains recordings now writes from them the same way; a tickbox in the Codex turns the citations off
- "My recording" or "Research source": your own recordings are written from freely, in your words. Someone else's video or podcast is research: the book learns the subject from it, credits the facts, and is written in your own words, angle and structure, never reproducing the source. Links are filed as research sources by default; switch it in the transcript viewer or in the Codex
- Built for long recordings: a 16-hour M4B audiobook went through in one go, 122,000 words, transcribed and cleaned in about an hour and three quarters on a recent Mac. Very long recordings are filed as parts of up to three hours, each with its own summary and chapters, so nothing is cut off
- Two engine sizes in Settings (Standard for the best accuracy, Fast for older computers), an option to pin the spoken language, and a button to free the disk space used by the engine
- BookyAI Listen is a paid add-on (monthly, yearly or lifetime). If you bought it with your BookyAI account it unlocks by itself; otherwise enter its key on the Listen page

**Thinking models on OpenRouter and Grok write the whole book**
- Models that reason before they answer (GLM, DeepSeek R1, Grok and many others) spend output tokens thinking, and those tokens counted against the chapter budget. A chapter could come back empty, be treated as a failure and be written by the Gemini rotation instead. These models now get room to think on top of the chapter budget, an answer that was all thinking is retried on the same model before anything else is tried, and slow models get more time: 20 minutes for an answer, and a streamed answer runs as long as the model keeps sending data
- New setting "If my engine fails": "Continue with another engine" (the default, as before) or "Stay on my engine". With "Stay on my engine" BookyAI never switches engines: yours is tried again after a pause, a chapter that still fails is marked as failed, the book moves on, and the failed chapters get one more pass at the end

**A book whose outline failed can be started again**
- When the outline request failed (a rejected key, an outage), the book page kept showing "Generating outline…" although nothing was running, and there was no way to start it again. The page now says the outline was not generated, keeps the reason even after a restart, and offers "Generate the outline", which starts the same book again with your Codex, author notes and series untouched

**Settings: Test checks the key you typed**
- The Test button checked the key that was already saved, so a freshly pasted key that had not been saved yet could be reported as "API key not valid". Test now saves the key in the field first, then checks it, and a field that holds an unsaved key says so

**Series: rename a series**
- The series name on the Series page is now editable: click the pencil next to it, type the new name and save

## 1.9.13 — 2026-09-16

**BookyAI Audio: files that pass ACX's loudness check**
- ACX measures loudness (RMS) over the whole file, pauses included, while earlier versions measured and reported only the spoken parts. A chapter could show -20 dB in the app and read -24 dB for ACX ("RMS is too low"). Every chapter is now finished on the same measure ACX uses and lands between -23 and -18 dB with a safety margin; the RMS chip next to each chapter shows that whole-file value. Re-render existing chapters (or Start fresh and Render) to apply

**OpenRouter: free, discounted and paid models, with prices**
- The OpenRouter model picker in Settings and in the book wizard is now grouped: OpenRouter Auto, then Free, then Discounted right now, then all other models A to Z, each with its input and output price per one million tokens. Under the picker you see the price of the chosen model and an estimated cost for a 50,000-word book
- New "OpenRouter fallback model": a second OpenRouter model that takes over when your main one fails mid-book (rate limit, empty answer, outage), before the Gemini rotation. Each chapter shows which model wrote it

## 1.9.12 — 2026-09-11

**Audiobook: no more duplicate tracks after the section list changes**
- If a section was added or switched on before the Prologue after your first render, re-rendering chapters could leave the old Prologue and Epilogue rows at their previous track numbers next to the new ones, with the old files still in the folder. Sections are now recognised by what they are, not by their position: a moved section is re-mastered from its cached narration under the right track number, file name and tags, and files that no longer belong to any track are removed after every render
- "Start fresh" now rebuilds the track list from the book's current sections immediately, instead of after the next render

## 1.9.11 — 2026-09-10

**Word export: a clean chapter list in Kindle Create**
- The title page (title, subtitle, author) and the Contents heading no longer appear in Kindle Create's "Suggested Chapter Titles" after importing the DOCX. Only your chapters and front and back matter sections are offered, verified against Kindle Create 1.114
- The title page keeps its look, with a small ornament between the subtitle and the author name

## 1.9.10 — 2026-09-10

**Word export: chapters that Kindle Create recognises**
- Each chapter opener is now a single heading that holds "Chapter N" and the title together and carries its own page break. Kindle Create (and Word's navigation pane) now see one numbered chapter per chapter, instead of "Chapter 1" stranded alone on a page and the title on the next page without its number
- No stray page-break paragraphs remain in the file, so importing into Kindle Create no longer produces blank pages. Full-page images still start on their own page
- Sub-headings inside chapters are left-aligned and only a step above the body size, so Kindle Create's "Suggested Chapter Titles" stops offering every sub-heading as a chapter

## 1.9.9 — 2026-09-10

**Word export: same paragraphs, same spacing as the preview**
- Consecutive lines now stay in one paragraph with a line break, and only a blank line starts a new paragraph, exactly as the Page preview and the PDF do. Earlier versions made every line its own paragraph, which added space between everything
- Scene-break rules (three asterisks or dashes on their own line) now span the full text width like the preview, with tighter spacing
- A heading marker on an empty line (for example "##" used as a spacer) is rendered as a gap, not printed as text

## 1.9.8 — 2026-09-09

**Word export, same as the preview**
- Bold and italic nested inside each other, backslash escapes, inline code and typographic quotes now come out in DOCX exactly as the Page preview shows them. Three asterisks (or dashes) on their own line become a scene-break rule instead of literal asterisks, and quoted lines come out indented in italics

**Import: replace the file in place**
- Picked the wrong or an outdated manuscript? A "Replace file" button next to the file name swaps the chapter list for the new file while everything you filled in stays: author, genre, language, profile, series and translations. The title follows the new file unless you typed your own

## 1.9.7 — 2026-09-09

**Change a book's voice after creation**
- A new Voice card in the book workspace lets you change the writing style and tone at any time, hear a short sample in the new voice, and either regenerate chapters one by one or rewrite all of them in the new voice with one click. Every chapter's previous text stays in its Versions

**Word export finally looks like the book**
- DOCX exports now follow the book's design: the template's font (one Word actually has), text size, line spacing, justified paragraphs, first-line indents, chapter openers with the chapter kicker and ornament, and proper heading styles, instead of Word's flat defaults

**Covers: describe the cover you want**
- Both the book's cover card and the Cover Studio have an "Art direction" choice: leave it to BookyAI as before, or switch to "My prompt" and describe the cover in your own words. Your description replaces BookyAI's genre art direction (a tickbox keeps it as secondary guidance), while the title, author name and the technical cover rules stay automatic. "View prompt" shows exactly what was sent, and the prompt is saved with the book for Redo

**Bring your own manuscript into a series**
- When importing a manuscript you can make it the next book of an existing series or start a new series with it, and each series page has an "Import a manuscript as Book N" button. Right after, BookyAI prepares the story so far (a continuity summary per chapter) and, for fiction, maps the characters into the series codex, so the next AI-written volume continues your book instead of only knowing its chapter titles. Standalone books can now also join an existing series from the Series card

**Fixed**
- PDF page numbers sat 0.23 inches from the bottom edge, inside the zone where Amazon KDP allows no text, so uploads were flagged. They now sit about 0.48 inches from the edge on every trim size
- A full-page image with a caption no longer leaves a nearly blank page after it in PDF and ebook exports

## 1.9.6 — 2026-09-08

**Authors page: pen names, bios and imprints as profiles**
- A new Authors page in the sidebar holds one profile per pen name or imprint: author name, bio, photo, publisher name, logo and legal notice. Pick the profile when you create or import a book, or switch it any time in Book details; the exported book takes its copyright page, logo and About the Author page from it. Profiles can be duplicated, one is the default for new books, and a profile in use cannot be deleted by accident. Your current settings became the first profile automatically

**Choose which appendices to write**
- Ticking "Generate appendices" in the wizard now shows the twelve sections with a tickbox each, and only the ticked ones are written: fewer sections, less time, fewer tokens. The same tickboxes appear when you generate or regenerate appendices later, preselected with your choice for that book
- The "Include in book" ticks in the workspace are now saved with the book, so they stay as you left them through edits, reloads and restarts

**Chapters follow their own beats**
- Each chapter is now written from its own outline beats, marked as binding, with the following chapters declared off-limits, so a chapter no longer runs ahead into the events of the next ones. The per-chapter "Structure" button is now "Instructions" and covers plot beats and scenes as well as lists and tables
- Every chapter now shows which AI engine and model wrote it. When the free chain has to fall back from Gemini to Ollama, the chapter is flagged and the progress bar says so

**Fixed**
- Code blocks in technical books: a clean-up pass was removing the indentation from code, and exports had no styling for code, so long lines ran over the page in ebook readers. Code keeps its indentation, wraps inside a shaded monospace box in EPUB, PDF, Kindle and HTML, and Word exports get proper code paragraphs. Chapters generated before this update need to be regenerated or have their code pasted back

## 1.9.5 — 2026-09-08

**BookyAI Audio on Intel Macs**
- The narration engine never started on Intel Macs: the Intel build was missing one native image library the engine loads at startup, so every voice preview or render ended with "Narration engine failed to start". The library is now included in the Intel build, and the release pipeline checks both Mac builds for it. Update to 1.9.5, then preview a voice again; the engine downloads as usual on first use
- If the engine ever fails to start again, the message now names the cause (exit code or signal and the error line) instead of a bare "failed to start"

**Fixed**
- The Test button next to the OpenRouter and Grok keys reported "Empty response" on a valid key when a reasoning model was selected: the tiny test request left the model no room to answer after thinking. The test now uses a proper allowance, a reasoning-only reply counts as a pass, and a model that spends its whole allowance thinking gets a message that says so instead of "Empty response"

## 1.9.4 — 2026-09-07

**Your hand-written appendices stay yours**
- Regenerate appendices now shows a confirmation first: exactly which sections will be rewritten, which are written for the first time, and which are kept as they are. Sections you edited by hand after BookyAI wrote them are kept by default, with a tickbox to include them on purpose
- Before a full regeneration, every current section is copied to an "appendices-backup" folder inside the book folder (one file per section), so the originals can be opened outside the app. The previous text also stays in each section's Versions

**Ollama with thinking models (Qwen 3, Gemma 4 and friends)**
- Thinking is now off by default for Ollama: reasoning tokens counted against the output budget, so short edits came back as "Empty Ollama response" and a chapter could take hours on local hardware. A new tickbox in Settings lets thinking models think if you want that
- New "Ollama context window" setting: Automatic, Ollama's own setting (BookyAI sends no context size, so a daemon you run at 128k is never reloaded), or a fixed size from 8k to 128k
- A model that spends its whole budget reasoning now gets a clear message instead of "Empty Ollama response", and a large model still loading is no longer reported as "not reachable"

**Fixed**
- Third-person narration is now enforced. Books set to third person, or fiction with no choice, received no narration instruction at all, so a memoir-like topic could pull the whole book into first person. A per-chapter viewpoint character no longer forces first person either

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
