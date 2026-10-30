# Guinea-Bissau: law history in git

The law of Guinea-Bissau as a git history: one file per provision, one commit per law on the day it took effect, and the law that made each change as the commit's author. `git blame` names the law behind every paragraph; `git log` lists every change; picking a date gives the text in force that day.

It follows the shared design of [lexifina/global-law](https://github.com/lexifina/global-law).

**What is in it now (a first build, not complete)**

| Folder | Act | Versions | History |
| --- | --- | ---: | --- |
| `treaties/` | Treaty actions of Guinea-Bissau recorded by WIPO Lex (name, administering organisation, dates; no treaty text) | one per action date | From the earliest recorded action to the latest |
| `un-treaties/` | Treaty actions of Guinea-Bissau on multilateral treaties deposited with the UN Secretary-General (UN Treaty Collection; no treaty text) | 42 | One version per action date, 1974 to 2021 (55 treaties) |
| `catalogue/` | Catalogue of laws of Guinea-Bissau recorded by WIPO Lex (title, subject, date, link; no law text) | one per recorded date | Dated by the date WIPO Lex records for each law |
| `legal-system/` | Legal system of Guinea-Bissau: constitution, legislature, courts, official languages (Wikidata, WIPO Lex) | 1 | Oldest version available, 30 October 2026 |

**Language.** English. This repository holds metadata only.

**Source.** Metadata only, no law text, because no official online source for Guinea-Bissau's laws was found, and its copyright code (Decree-Law No. 46 980 of 27 April 1966, extended to the territory by Decree 679/71) has no clause excluding laws from protection, so no third-party copy of a constitution or statute is used. Treaty actions, the list of laws and the constitution date come from the WIPO Lex member profile (https://www.wipo.int/wipolex/en/members/profile/GW); open facts on the legal system come from Wikidata (CC0). Both retrieved 30 October 2026. The `un-treaties` act is facts only (treaty names and the dates of signature, ratification, accession, succession, acceptance or approval) from the status pages of 78 multilateral treaties at the [UN Treaty Collection](https://treaties.un.org/), read the same day.

## Dates

Each commit is dated at noon local time. A UN treaty action is dated by the depositary's record for the day. A WIPO Lex treaty is dated by the country's own action: its ratification, accession or similar instrument, else its entry into force for the country, else signature. A catalogue entry is dated by the date WIPO Lex records for the law (promulgation, entry into force, commencement or adoption); where WIPO Lex gives only 'January 1' of a year, that date is a placeholder, not a known date. A law with no recorded date is added on 30 October 2026, the retrieval date.

## How it is checked

Every version is read back from git on the day it took effect and on the day before (`tools/check_repo.py`) and must match `corpus.json`; results are in `REPRODUCE.md`.

## What "author" means

The author of a commit is the law that made the change, with an e-mail address that cannot exist (`<law key>@wipo-int.invalid`). Each treaty action or catalogue date is credited to a key that names the record (treaty-<WIPO id>, catalogue-<date>); these are not laws. The committer is always Lexifina.

## Limits

Metadata only: the Constitution, statutes and treaties are named, not reproduced. The treaty list is what WIPO Lex records and omits any treaty it does not track. The next step is an official Boletim Oficial copy with a text layer and a date.
