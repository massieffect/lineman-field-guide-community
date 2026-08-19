# A deck list for the Lineman Field Guide app

This is one list among however many exist. **Anyone can publish their own** — a school, a
local, an apprenticeship programme, one lineman with good cards. Nobody approves them and
the app's developer is not involved.

## Publish your own list

1. Put your exported `.fieldbook-deck.json` files (from **My decks → Share**) anywhere that
   serves files over **https**: a public GitHub repo like this one, your school's website, a
   public shared folder.
2. Next to them, put a file called `index.json`:

```json
{
  "app": "lineman-field-book",
  "kind": "community-index",
  "version": 1,
  "updated": "2026-08-19",
  "notice": "Decks from Local 640's apprenticeship class.",
  "decks": [
    {
      "id": "unique-id",
      "title": "Year 1 code questions",
      "author": "Local 640 JATC",
      "cards": 40,
      "file": "decks/year1.fieldbook-deck.json",
      "tags": ["code", "year1"]
    }
  ],
  "notes": []
}
```

3. Hand out the link to `index.json`. In the app: **Apprentice → Shared decks → Follow a
   list**, paste, done.

`app` must be `lineman-field-book` and `kind` must be `community-index` — that is how the app
knows the file is meant for it. File paths are relative to `index.json`; absolute paths, `..`
and anything not https are refused.

## Sharing with one person

You don't need a list at all. In **My decks**, tap a deck, tap **Share**, and send the file by
AirDrop, text, email, or anything else. They tap **Import a deck file**. Phone to phone, no
server, nobody in the middle.

## What the app does with a list

Fetches `index.json` when the user taps Refresh, caches it so it still works with no signal,
and installs a deck into that user's own **My decks** when they choose to. Nothing is ever
uploaded from the app and there are no accounts.

Every deck is shown under its author's name and labelled as coming from the list it came
from. It is not app content and the app's provenance line does not apply to it. A list is
only as trustworthy as whoever gave you the link.

## Limits

Index capped at 2 MB and 500 entries; every field length-capped; malformed entries dropped.
Users can follow up to 10 lists.

## This particular list

Run by the app's developer, and it is optional — a user can remove it and follow only their
school's. It carries one sample deck so the mechanism can be seen working.
