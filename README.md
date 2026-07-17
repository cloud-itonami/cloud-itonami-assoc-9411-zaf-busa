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

`busa.org.za`'s own "About BUSA" page renders successfully and
directly states the October 2003 founding / January 2004 operations
start; `en.wikipedia.org`'s own article on BUSA additionally
corroborates the October 2003 date and supplies the merger detail
(Business South Africa + South African Chamber of Business) not
present on the official page checked.

## Scope

A **read-only reference/archive** catalog — not an Advisor⊣Governor
actuation actor. It proposes or executes nothing on BUSA's behalf.

Coverage is reported honestly (see `association.facts/coverage`): an
association not in `catalog` has **no spec-basis**, full stop — never
fabricate one.

## Data

- `src/association/facts.cljc` — the catalog, source of truth.
- `schema/association-rule.edn` — DataScript schema.
- `data/datascript-tx.edn` — derived DataScript tx-data (query this
  alongside other `cloud-itonami`/`etzhayyim` compliance-fact sources via
  `com-junkawasaki/root`'s `scripts/compliance-fact-query.cljs`).

Both entries directly WebFetch-verified: the October 2003 founding of
BUSA (via merger of Business South Africa and the South African
Chamber of Business, per Wikipedia, with the date independently
confirmed by busa.org.za's own official page), and BUSA beginning
operations in January 2004 as the formally recognised representative
of business at NEDLAC.

## License

AGPL-3.0-or-later (matches the `cloud-itonami-iso3166-*` /
`-municipality-*` / `-assoc-*` / `-lei-*` convention). Policy text
itself remains BUSA's; this repo stores only citation metadata
(id/title/url/dates), not full text.
