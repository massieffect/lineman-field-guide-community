# Lineman Field Guide — community decks

This repository is the list the **Lineman Field Guide** app reads for its Community
section. It is public because the app fetches `index.json` with no credentials, over
plain HTTPS, on a phone that may be on a truck in a field.

Nothing here is app content. Every item is a contributor's own study material, shown
under their name, and the app's provenance line does not apply to it.

## What's listed

One sample deck, so the feature can be seen working end to end. Everything else comes
from what people send in — see **Submitting** below. The list is curated, not open: a
person reads every submission before it appears here.

## How the app uses this

1. `index.json` is fetched when the user taps **Refresh list**, and cached on the phone
   so the section still works with no signal.
2. Deck and note files are resolved **relative to `index.json`**. The app refuses
   absolute paths, `..`, and anything that is not `https:`.
3. Installing a deck copies it into the user's own "My decks". Nothing is uploaded from
   the app, ever, and no account exists.

## Submitting

Export a deck or your notes from **My decks** in the app and email the file to the
address on the Community screen. Include the name you want shown.

**Study aids only.** Not your employer's standards, not company procedures, not a
copyrighted test bank, not text copied from a handbook or another app. Cards must be
your own words. Cite the app page or the OSHA paragraph where a rule lives rather than
restating a rule as law.

**What you keep and what you give.** You keep ownership of what you write. Submitting it
grants the developer a worldwide, royalty-free, perpetual, irrevocable, non-exclusive,
sublicensable and transferable licence to publish, edit, translate, adapt and build on
it in the app and any future version, including a paid one, with your name on it. It is
unpaid and cannot be withdrawn once granted. The full wording is clause 9 of the app's
terms of use, shown in the app under Settings › Terms of use, and stated on the Community
screen where you submit. Send only your own work.

The curator may edit, relabel, refuse or remove anything at any time, and is under no
obligation to list a submission.

## Curator: adding an item

1. Drop the exported `.fieldbook-deck.json` or `.fieldbook-notes.json` into `decks/` or
   `notes/`.
2. Add an entry to `index.json` with a unique `id`, the author name, the card or note
   count, and the file path relative to `index.json`.
3. Bump `updated` at the top level. The app shows that date as "Updated ...".
4. Commit to `main`. The raw URL is served immediately; no build step.

`app` must stay `lineman-field-book` — it is the app's slug and the parser rejects an
index without it, regardless of the app's display name.

## Safety

The app caps the index at 2 MB, the number of entries at 500, and the length of every
field. A malformed entry is dropped rather than rendered. That is a backstop, not a
substitute for reading what you list.
