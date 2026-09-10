(ns association.facts
  "Industry rule/history catalog for Business Unity South Africa
  (BUSA) -- a 49th industry-association-level source (see
  cloud-itonami-assoc-9411-sau-fsc, -9411-aut-wko, -9411-irl-ibec,
  -9411-nzl-businessnz, -9411-cze-spcr, -9411-ind-cii for the first
  six) per ADR-2607141700 (cloud-itonami-compliance-fact-federation).
  The SEVENTH entry aligned to ISIC 9411 (activities of business,
  employers, and professional membership organizations). Fills South
  Africa's previously-open association-axis gap (one of 22 countries
  identified with country+municipality but no association entry, per
  tick 141's gap analysis) -- South Africa now has real, individually
  verified facts across ALL THREE axes (country:
  cloud-itonami-iso3166-zaf statute.facts; municipality:
  cloud-itonami-municipality-zaf-cape-town; association: this
  entry).

  busa.org.za's own 'About BUSA' page
  (https://www.busa.org.za/about-busa/), directly read, states
  verbatim: 'BUSA was formed in October 2003 and began operating in
  January 2004.' en.wikipedia.org's own article on Business Unity
  South Africa additionally quotes verbatim: 'BUSA was founded in
  October 2003, through a merger of Business South Africa and the
  South African Chamber of Business' -- the October 2003 date is
  therefore independently confirmed by BOTH the official primary
  source and Wikipedia, and the merger detail (not present on the
  busa.org.za About page checked) is Wikipedia-sourced. No personal
  names of office-holders are persisted here.

  An association not in `catalog` has NO spec-basis, full stop; never
  fabricate one.")

(def catalog
  "association-slug -> vector of association-rule entries."
  {"busa"
   [{:association-rule/id "busa.founding-2003-merger"
     :association-rule/title "Business Unity South Africa (BUSA) formed in October 2003 through a merger of Business South Africa and the South African Chamber of Business (Wikipedia merger detail, October 2003 date independently confirmed by busa.org.za's own About BUSA page)"
     :association-rule/association "busa"
     :association-rule/isic "9411"
     :association-rule/country "ZAF"
     :association-rule/kind :governance-program
     :association-rule/url "https://www.busa.org.za/about-busa/"
     :association-rule/url-provenance :official-busa-org-za
     :association-rule/established-date "2003-10"
     :association-rule/retrieved-at "2026-07-17"
     :association-rule/topic #{:governance}}
    {:association-rule/id "busa.operations-began-2004"
     :association-rule/title "BUSA began operating in January 2004, becoming the formally recognised representative of business at NEDLAC (South Africa's National Economic Development and Labour Council) (busa.org.za official About BUSA page)"
     :association-rule/association "busa"
     :association-rule/isic "9411"
     :association-rule/country "ZAF"
     :association-rule/kind :governance-program
     :association-rule/url "https://www.busa.org.za/about-busa/"
     :association-rule/url-provenance :official-busa-org-za
     :association-rule/established-date "2004-01"
     :association-rule/retrieved-at "2026-07-17"
     :association-rule/topic #{:governance}}]})

(defn spec-basis [association] (get catalog association))

(defn coverage
  ([] (coverage (keys catalog)))
  ([associations]
   (let [have (filter catalog associations)
         missing (remove catalog associations)]
     {:requested (count associations)
      :covered (count have)
      :covered-associations (vec (sort have))
      :missing-associations (vec (sort missing))
      :note (str "cloud-itonami-assoc-9411-zaf-busa Wave 0 (ADR-2607141700): "
                 (count (get catalog "busa")) " BUSA entries seeded "
                 "with busa.org.za official + Wikipedia merger-detail corroboration. "
                 "Extend `association.facts/catalog`, never fabricate an id/url.")})))

(defn by-topic [association topic]
  (filterv #(contains? (:association-rule/topic %) topic) (spec-basis association)))
