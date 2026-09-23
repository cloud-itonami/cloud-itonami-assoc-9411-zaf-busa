# cloud-itonami-assoc-9411-zaf-busa

Industry rule/history catalog for **Business Unity South Africa**
(BUSA) — the SEVENTH entry aligned to **ISIC 9411** (activities of
business, employers, and professional membership organizations),
alongside
[`-9411-sau-fsc`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-sau-fsc)
(Saudi Arabia),
[`-9411-aut-wko`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-aut-wko)
(Austria),
[`-9411-irl-ibec`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-irl-ibec)
(Ireland),
[`-9411-nzl-businessnz`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-nzl-businessnz)
(New Zealand),
[`-9411-cze-spcr`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-cze-spcr)
(Czech Republic), and
[`-9411-ind-cii`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-ind-cii)
(India). Part of the
[`cloud-itonami`](https://github.com/cloud-itonami) compliance-fact
family (ADR-2607141700, `cloud-itonami-compliance-fact-federation`,
in `com-junkawasaki/root`).

## Sourcing note

This repo fills South Africa's previously-open association-axis gap
(one of 22 countries identified with country+municipality coverage
but no association entry, per tick 141's gap analysis). South Africa
now has real, individually verified facts across all three axes:
country
([`cloud-itonami-iso3166-zaf`](https://github.com/cloud-itonami/cloud-itonami-iso3166-zaf)),
municipality
([`cloud-itonami-municipality-zaf-cape-town`](https://github.com/cloud-itonami/cloud-itonami-municipality-zaf-cape-town)),
and association (this repo).

Eleven of the twelve entries cite `busa.org.za` itself (About BUSA,
How BUSA Works, Strategic Objectives, Vision/Mission/Ethos, Membership
Information, and the 1 July 2026 media statement on the UIF). The one
exception is the merger that formed BUSA (Business South Africa + South
African Chamber of Business): no `busa.org.za` page checked describes it,
so that entry cites `en.wikipedia.org`, and says so in its
`:url-provenance`.

## Scope

A **read-only reference/archive** catalog — not an Advisor⊣Governor
actuation actor. It proposes or executes nothing on BUSA's behalf.

Coverage is reported honestly (see `association.facts/coverage`): an
association not in `catalog` has **no spec-basis**, full stop — never
fabricate one.

## Data

- `data/datascript-tx.edn` — the catalog, **source of truth**. Facts are
  authored here and nowhere else. Query it alongside other
  `cloud-itonami`/`etzhayyim` compliance-fact sources via
  `com-junkawasaki/root`'s `scripts/compliance-fact-query.cljk`.
- `src/association/facts.kotoba` — the Clojure reading, **generated**.
- `src/association_facts.kotoba` — the Kotoba port, **generated**; compiles
  with `amu compile --target js|wasm32-browser|x86_64-linux|aarch64-macos`.
- `schema/association-rule.edn` — DataScript schema.

Every entry carries the page it came from (`:source-article`) and the
verbatim span the claim rests on (`:source-quote`). To change the catalog:

```bash
# 1. edit data/datascript-tx.edn, then regenerate both readings
kbb --backend sci scripts/gen-kotoba-port.cljk
kbb --backend sci scripts/gen-kotoba-port.cljk --check   # exit 1 if either reading drifted

# 2. check the catalog against its own sources
kbb --backend sci scripts/verify-catalog.cljk            # structural, offline
kbb --backend sci scripts/verify-catalog.cljk --live     # fetch every :url, require every quote
```

`verify-catalog` exits `0` (checked, nothing wrong), `1` (findings
printed) or `2` (REFUSED — could not check, e.g. a source did not
answer 2xx). A `2` is not a pass.

Every page on `busa.org.za` also carries a sidebar of the latest media
statements. A span copied from it is "on" every page of the site and
supports nothing about the page it is cited from, so quotes are taken
from each page's own body.

`kbb -M:test` finds no test namespace in this repository (the tests are
`.kotoba` files since the 2026-09-10 rename), so it does not exercise
`test/`. `--check` above is what keeps the two generated readings tied to
the data.

## License

AGPL-3.0-or-later (matches the `cloud-itonami-iso3166-*` /
`-municipality-*` / `-assoc-*` / `-lei-*` convention). Policy text
itself remains BUSA's; this repo stores citation metadata
(id/title/url/dates) and the short verbatim span each claim rests on,
not full text.
