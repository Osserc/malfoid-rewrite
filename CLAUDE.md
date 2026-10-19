# Malfoid Rewrite — Series Bible

A rewrite of all seven Harry Potter books in the "Malfoid" tradition: Draco Malfoy is a girl, **Dracaena Malfoy**, and she is Harry's tsundere love interest. It is not a cosmetic genderswap. The change carries real thematic weight, so we rewrite plot beats, magic and setting wherever that serves the story.

This repo is the series bible, the single record of everything we decide. The finished prose will live here too, in `manuscript/`.

@core/premise.md

## Roles

The user is the author and has the final word. Claude is co-writer and continuity editor: propose freely and push back when something doesn't hold together, but only the user settles or locks a decision.

## Repo map

| Path | Contents |
|---|---|
| `core/premise.md` | The pitch, plus the locked pillars as one-liners (loaded above) |
| `core/themes.md` | What the rewrite argues, overall and per book |
| `core/style.md` | POV, language, tone, prose rules |
| `continuity/divergences.md` | **The ledger.** Every departure from canon, as `DIV-###` |
| `continuity/open-questions.md` | Undecided points and unresolved ripples, as `Q-###` |
| `continuity/timeline.md` | Chronology from backstory to epilogue |
| `continuity/reveals.md` | Who knows what, and when: reader, Harry, Dracaena, others |
| `characters/` | One file per significant character; `_roster.md` lists everyone |
| `threads/` | Arcs that span books: beats per book, setups and payoffs |
| `setting/` | Magic, society, history, places |
| `problems/` | Canon elements that break the plot or the ethics, with the reasoning behind how we deal with them |
| `books/bN/` | `outline.md` (arc, acts, chapters) and `canon-delta.md` (what happens to each canon beat) |
| `scenes/bN/` | Key scenes as beat outlines; `scenes/unplaced/` for scenes not yet slotted |
| `manuscript/bN/` | Final prose, one file per chapter (`ch01.md`, …). Not started |
| `templates/` | Starting point for every file type above |
| `inbox.md` | Raw ideas. Nothing in it is canon |

## Rules

1. **Canon by default.** Anything the ledger doesn't override follows the original books. Before relying on canon for anything, check the ledger. Don't document canon for its own sake; document what changes.
2. **Locked means locked.** Never alter a 🔒 item. If something conflicts with one, stop and raise the conflict with the user rather than resolving it yourself.
3. **One home per fact.** Each fact is written out in full in exactly one file. Everywhere else gets at most a one-line summary and a link. To change a fact, change its home first, then fix the summaries.
4. **Trace the ripples.** Every decision has consequences. When one is made, follow its effects through characters, threads, the timeline and reveals. Anything that can't be resolved yet becomes a `Q-###`; don't leave it implicit.
5. **Ideas go to the inbox.** Loose ideas that aren't part of active work go in `inbox.md`, not into bible files.
6. **Our own words only.** Never reproduce text from the original books. Canon gets summarized in our own words, and the manuscript is original prose.
7. **Conflicts are bugs.** When files disagree, the precedence is 🔒 locked > settled > draft, then ledger > home file > summaries, then bible > manuscript. Fix the conflict or raise it; never leave it standing.

## Status

Every content file has `status:` in its front matter. Items inside a file can carry their own status: 🔒 for locked, *(settled)* for settled. An item tagged with a `DIV-###` has that entry's status. Anything unmarked has the file's status.

| Status | Meaning | Set by |
|---|---|---|
| 🔒 `locked` | Set in stone | User only |
| `settled` | Agreed. Changes only on purpose, after a ripple check | User only |
| `draft` | Work in progress, free to change | Claude or user |

Files in `problems/` use `open` / `resolved` instead. Ledger entries carry their own status.

## IDs

- `DIV-###` is defined only in `continuity/divergences.md`, and `Q-###` only in `continuity/open-questions.md`.
- IDs are permanent: never renumber or reuse them. Answered questions move to the Answered section and stay there.
- Refer to them by bare ID (e.g. `DIV-003`) so they're greppable. Refer to books as `B1`–`B7`.

## Workflows

### Recording a decision

1. If it changes canon, add or update the `DIV-###` entry: canon, ours, home, ripples, status.
2. Write it out in full in its home file.
3. Update the one-line summaries it touches: threads, character arcs, book outlines, timeline, reveals.
4. If it's 🔒, add a one-liner to the pillars in `core/premise.md`.
5. Move the questions it answers to Answered, and open new `Q-###` entries for ripples that can't be resolved yet.
6. Tell the user which files changed and which new questions came up.

### Handling a canon problem

The problem file holds the analysis: what canon does, why it matters to us, the options considered. The chosen fix goes through *Recording a decision* as a `DIV`, and the problem file links to it and switches to `resolved`.

### Planning a book

1. Create `books/bN/canon-delta.md` from the template. List every beat of the original book in our own words and mark it keep, alter or cut. Then add new beats.
2. Build `outline.md` from the delta: logline, acts, chapter beats.
3. Check that every decided beat for the book is placed and every thread has a beat in it.

### Scenes

Scenes are named by slug, never by chapter number. Placement in the front matter stays tentative until the book outline is settled. A scene file holds beats, not prose.

### Manuscript

Chapters are written from the settled outline and scene files. If drafting turns up a better idea that contradicts the bible, raise it rather than quietly diverging. If it's accepted, update the bible first.

## Conventions

- File names in kebab-case; characters by full name (`dracaena-malfoy.md`). Meta files start with `_`.
- New files start from `templates/`.
- Relative Markdown links between files.
- British English and canon terminology unless a `DIV` changes it.
- Commit messages lead with the IDs they touch: `DIV-009, Q-021: …`.
