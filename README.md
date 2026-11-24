# Crypto Advertising and Promotion Rules by Country

Global dataset of how regulators treat crypto ads, finfluencers and promotions.

**Version 1.0 (2026-Q4) · License: CC BY 4.0 · DOI: to be added with the Zenodo release**

> This dataset is information, not legal advice. Rules change, and the summaries here are simplified. Check the linked primary source and take local legal advice before relying on any row.

## Summary

The dataset lists 58 advertising and promotion rules for crypto-assets across 37 jurisdictions: 36 countries and territories plus the European Union. Every row gives the regulator, the instrument and its status, how it treats crypto advertising, and whether it requires licensing, risk warnings, influencer disclosures or limits on incentives. Each row links to its source and is marked verified or unverified.

## Why it exists

Crypto advertising rules are spread across securities laws, consumer laws, central bank notices and self-regulatory codes, often in different languages. Researchers, compliance teams, journalists and platform policy teams need a single, citable table that can be filtered and compared across countries. This dataset gives one row per jurisdiction and rule in a fixed schema, so the rules can be counted, mapped and tracked each quarter.

## Coverage (v1.0)

| Item | Count |
|---|---|
| Rows (rules) | 58 |
| Jurisdictions (ISO codes, incl. EU) | 37 |
| Verified rows | 39 (67%) |
| Tier 1 jurisdictions covered | 32 of 32 (52 rows, 73% verified) |
| Tier 2 jurisdictions covered so far | 5 (6 rows) |

Coverage is organised in tiers:

- **Tier 1** (covered in full): United States (federal and New York), United Kingdom, EU (MiCA), Germany, France, Italy, Spain, Netherlands, Ireland, Switzerland, United Arab Emirates (Dubai VARA, ADGM, federal), Saudi Arabia, Singapore, Hong Kong, Japan, South Korea, India, Australia, Canada, Brazil, Türkiye, Thailand, Indonesia, Philippines, Vietnam, Malaysia, Nigeria, South Africa, Kenya, Israel, Mexico, Argentina.
- **Tier 2** (started): China, Russia, Taiwan, Pakistan, Qatar. The other EU/EEA member states and the rest of APAC, Latin America, MENA and Africa will be added in later releases.
- **Tier 3** (planned): every other UN member state. A row will say `no_specific_rule` only after the regulator's own site has been searched.

Sub-national and free-zone rules (New York, Dubai VARA, ADGM) are separate rows. Their `iso_code` is the country's code.

## Files

| File | Description |
|---|---|
| `data.csv` | The dataset (UTF-8, comma-separated, header row) |
| `codebook.csv` | Column definitions, types and allowed values |
| `README.md` | This document |
| `CHANGELOG.md` | Version history |
| `CITATION.cff` | Citation metadata |
| `metadata.json` | DataCite-style metadata |

## Schema

| Column | Allowed values / format | Meaning |
|---|---|---|
| record_id | e.g. `GB-001`, `US-NY-001` | Unique row ID |
| jurisdiction | text | Country, EU, or sub-national/free-zone jurisdiction |
| iso_code | ISO 3166-1 alpha-2, or `EU` | Country code |
| region | Africa / Americas / Asia-Pacific / Europe / Middle East | World region |
| regulator | text | Issuing or enforcing body, with acronym |
| rule_name | text | Official name of the instrument |
| instrument_type | law / regulation / guidance / ban / proposal | Legal form |
| status | in_force / adopted_not_in_force / proposed / repealed | Status on `last_checked` |
| effective_date | YYYY-MM-DD or blank | Blank where not confirmed |
| crypto_ads_status | allowed / restricted / banned / no_specific_rule | Treatment of crypto ads |
| authorisation_required | Y / N / unclear | Licence or approval needed to advertise |
| risk_warning_required | Y / N / unclear | Risk warning or disclaimer required |
| influencer_rules | Y / N / unclear | Specific duties for influencers or paid promoters |
| incentive_restrictions | Y / N / unclear | Limits on bonuses, airdrops, referral rewards |
| summary | max 300 characters | Plain-language summary in our own words |
| source_name | text | Source document or page |
| source_url | https URL | Link to the source |
| last_checked | YYYY-MM-DD | Date the row was checked |
| verification_status | verified / unverified | See Method |
| notes | text | Edge cases, pending changes, reasons for unverified status |

Full definitions are in `codebook.csv`.

## Method

1. **Finding rules.** For each jurisdiction we searched regulator websites, official gazettes, legislatures and central banks, plus law firm and news trackers. Trackers were used only to find rules. No competitor marketing agency content was used.
2. **Verifying rules.** A row is `verified` when its key facts were confirmed from a primary source: a regulator, official gazette, legislature, central bank, or the self-regulatory body that issued the rule (e.g. ASCI in India). The `source_url` of a verified row points to that primary source.
3. **Unverified rows.** Where only secondary sources were available, the row is kept but marked `unverified`, and `notes` explains what was not confirmed.
4. **Coding fields.** Y/N fields are set to `Y` or `N` only when the source supports it; otherwise they are `unclear`. `effective_date` is left blank when the date was not confirmed.
5. **Writing.** Summaries and notes are written in our own words. The dataset does not reproduce regulator or statutory text.
6. **Quality checks.** A validation script checks the header, allowed values, date formats, ISO codes, record ID format and duplicates, empty sources, summary length, and that every unverified row has a note.

## Limitations

- Coverage is not yet global. Tier 2 and Tier 3 jurisdictions will be added in quarterly releases.
- One row may stand for a larger body of law. EU member state rows note the national MiCA framework; the marketing content rules for those states are in the EU-level rows.
- Many Y/N fields are `unclear` where the source did not settle the point. `unclear` means "not confirmed", not "no".
- Some sources are only in the local language and were read through summaries or translations.
- Rules change often. Each row shows its `last_checked` date.
- General consumer protection, unfair competition and platform ad policies (such as Google or Meta crypto ad policies) apply in many places but are not included unless they are crypto-specific.

## Not legal advice

This dataset is provided for research and information only. It is not legal advice and should not be relied on as such. Laws and regulator positions change, and summaries leave out detail. Always check the primary source and seek qualified local legal advice.

## License

[Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/). You may share and adapt the data for any purpose, provided you give credit.

## How to cite

> Kamala Santhanath, A. (2026). *Crypto Advertising and Promotion Rules by Country* (Version 1.0) [Data set]. Blockchain App Factory. https://github.com/blockchainappfactory-data/crypto-advertising-rules-by-country

BibTeX:

```bibtex
@dataset{kamala_santhanath_2026_crypto_ads,
  author    = {Kamala Santhanath, Arun},
  title     = {Crypto Advertising and Promotion Rules by Country},
  year      = {2026},
  version   = {1.0},
  publisher = {Blockchain App Factory},
  url       = {https://github.com/blockchainappfactory-data/crypto-advertising-rules-by-country},
  note      = {Landing page: https://www.blockchainappfactory.com/blog/crypto-advertising-rules-by-country/}
}
```

## Update schedule

The dataset is updated quarterly. Each quarter every source is re-checked, changed rules are updated, new jurisdictions are added and the version number is raised (1.1 = 2027-Q1). Changes are listed in `CHANGELOG.md`.

## Maintainer

Arun Kamala Santhanath (ORCID: [0009-0001-5683-523X](https://orcid.org/0009-0001-5683-523X)), Marketing Head, Blockchain App Factory.

Maintained by Blockchain App Factory: https://www.blockchainappfactory.com/blog/crypto-advertising-rules-by-country/

Corrections and suggestions: marketing@blockchainappfactory.com
