# How this repository was made (Guinea-Bissau)

This file is written by the build on 2026-10-30, the day the source data was retrieved.

## Sources

| Source | Address | Retrieved | Licence |
| --- | --- | --- | --- |
| WIPO Lex member profile | <https://www.wipo.int/wipolex/en/members/profile/GW> | 2026-10-30 | WIPO content: CC BY 4.0 (https://www.wipo.int/web/terms-of-use); only facts copied |
| Wikidata | <https://www.wikidata.org/> | 2026-10-30 | CC0 |
| UN Treaty Collection (MTDSG status pages) | <https://treaties.un.org/> | 2026-10-29 | Facts only (treaty action, date, depositary); no text copied |

Every word of law in this repository comes from these sources. Lexifina reads them and records each act's dated versions, and the laws that made each change, in one corpus file. This repository is built from that file.

## What is in it

| Act | Title | Versions | Span |
| --- | --- | ---: | --- |
| `treaties` | Treaty actions of Guinea-Bissau recorded by WIPO Lex (facts only; no treaty text) | 32 | 1974-02-21 to 2025-06-09 |
| `catalogue` | Catalogue of laws of Guinea-Bissau recorded by WIPO Lex (title, date, link only; no law text) | 3 | 1966-04-27 to 1997-02-25 |
| `legal-system` | Legal system of Guinea-Bissau: open facts (Wikidata, WIPO Lex) | 1 | 2026-10-30 to 2026-10-30 |
| `un-treaties` | Treaty actions of Guinea-Bissau on multilateral treaties deposited with the UN Secretary-General (UN Treaty Collection; no treaty text) | 42 | 1974-07-29 to 2021-12-15 |

The build made 125 commits:

| Commits | Kind |
| ---: | --- |
| 4 | first version of an act |
| 121 | one law on its in-force day |
| 0 | changes no amendment note explains, credited to the publisher |

Other counts:
- 0 commits on the branch `future`: laws not yet in force on 2026-10-30.
- 1 commits dated 1 January 1970: in force before 1970, with the real day in their `In-force` trailer.
- 126 laws in the record.
- 201 tags.

## Dates

Each commit is dated at noon (Africa/Bissau) on the day the change took effect. The other dates, enacted and published, are trailers.

When a law gives no date of its own, the default rule applies: This repository holds metadata only, no law text. Each treaty is dated by the party's own action (ratification, accession or similar instrument; failing that its entry into force for the party, then signature); each catalogue entry by the date WIPO Lex records for the law. https://www.wipo.int/wipolex/en/members/profile/GW

## How the history is built

`tools/build.py` turns the corpus into this history in one pass: one commit per law, on the day it took effect. The same corpus always gives the same commit hashes. `tools/check_repo.py` reads every version back from git and compares it with the corpus. `tools/on.py` shows the law as it stood on any date. The corpus format is described in `tools/SCHEMA.md`.

- Corpus: sha256 `d736f3fde0c0405705dc9972d12aea7c79e462983daba9c6b5365bce6c445ee3` (621584 bytes).
- Builder blob hashes (`git hash-object`): `build.py` `a4faa25af85facb64b956b372f6b528aafdd7ec1`, `check.py` `3e59cb6f05eccb94a9ec14431a7f6781221e83ef`, `on.py` `644a6c0857fbcc72562032b58d57aa113fee0641`.
- Python 3.12.10; git version 2.46.0.windows.1.

## Checks

Not yet run for this build.

No second build of this corpus has been compared yet.

## Decisions made by hand

- Metadata only, no law text: no official online source for the constitution or statutes was found, and the copyright code that applies (Decree-Law No. 46 980 of 27 April 1966, extended to the territory by Decree 679/71) has no clause excluding laws from protection, so third-party copies of law text were not used.
- Treaty versions are dated by the party's instrument date (ratification, accession or similar), else its entry-into-force date for the party, else signature; treaties with none of these are left out.
- Catalogue entries use the date WIPO Lex records (promulgation, entry into force, commencement or adoption, in that order); WIPO Lex gives some laws only "January 1" of a year, which is a placeholder, not a known date; a law with no date is added on the retrieval date.
- No treaty or law text is included: titles, dates, administering organisation and links only.
- UN Treaty Collection: 55 multilateral treaties deposited with the UN Secretary-General, with the state's signature, ratification, accession, succession, acceptance or approval dates. Facts only; one version per action date, with the first version credited to the action. Treaties outside the 78 status pages read are not listed.

## What AI did and did not do

The scripts that read the sources and build this repository were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- none
