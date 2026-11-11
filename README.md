# Nawafith gazette data

Records built from the Official Gazette of the Syrian Arab Republic and published as pages on [gov.nawafith.net](https://gov.nawafith.net). Built on 2026-11-11 from gazette issues up to 2026/42 (28 October 2026).

Every row ends with `nawafith_url`, the page for that record. The page carries what these files leave out: the notice or decree text in Arabic, the English translation, and the link to the gazette issue.

## Files

| File | Rows | One row is |
|---|---|---|
| `nawafith-companies-since-2024-12.csv` | 3,042 | a company with a notice in the gazette since December 2024 |
| `nawafith-decrees-gazette-2025-2026.csv` | 4,162 | a decree, decision or other instrument printed in a 2025 or 2026 gazette issue |

UTF-8 with a byte-order mark, comma separated, one header row.

## Companies

`slug`, `name_ar`, `name_en`, `notice_type`, `legal_form`, `governorate_en`, `governorate_ar`, `sector`, `subsector`, `capital_as_printed_syp`, `foreign_capital_percent`, `founders_named`, `gazette_issue`, `founded_at`, `nawafith_url`

- `notice_type`: 2,543 are new registrations (`company_new`), 498 are amendments to a company's statute (`company_amendment`), 1 is a dissolution. A company appears once.
- `governorate`: stated for 2,570 (84%). `sector`: classified for 2,969 (98%); the classes are Nawafith's own, assigned from the stated purpose.
- `capital_as_printed_syp`: present for 2,196 (72%), in Syrian pounds as the notice prints it. Syria redenominated its currency during this period, so amounts from different issues are not comparable without conversion. This file does not convert them.
- `founders_named`: how many founders the record names. Their names are on the company page, not in this file.
- `founded_at`: present for 1,849 (61%). `foreign_capital_percent`: present for 1,275 (42%).
- `name_en` is a translation or transliteration made by Nawafith. The Arabic name is the one in the gazette.

## Decrees and decisions

`id`, `type_en`, `type_ar`, `number`, `date`, `date_precision`, `issuing_body_en`, `issuing_body_ar`, `title_ar`, `title_en`, `gazette_year`, `gazette_issue`, `nawafith_url`

- Metadata only. The text of each instrument is on its page.
- `type`: Decision 3,787; Decree 143; Instructions 7; Law 3; Constitutional Declaration 2; empty for 220 where the record does not say.
- `date` is the date written in the instrument. `date_precision` says how much of it is known: day 3,191, month 417, year 554. 197 instruments carry a date before December 2024 because the gazette printed them later.
- `title_en` is a machine translation. `title_ar` is missing for 145 rows.

## Limits

- The source is scanned print read by OCR. Names and numbers can be wrong; the page links to the issue so they can be checked.
- Counts are pages a reader can open, not totals from a ministry. A company registered without a gazette notice is not here, and individual traders in the commercial register are not here.
- Nothing before 2025 gazette issues is included.

## Licence and citation

[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/). Credit Nawafith and link to gov.nawafith.net.

> Nawafith (2026). Syrian Official Gazette records: companies and decrees, December 2024 to October 2026. Zenodo. https://doi.org/10.5281/zenodo.24122383

The live counts and method are at https://gov.nawafith.net/en/numbers. Also on [Zenodo](https://doi.org/10.5281/zenodo.24122383), [GitHub](https://github.com/karam2022/nawafith-gazette-data), [Hugging Face](https://huggingface.co/datasets/Zendetta/nawafith-gazette-data) and [Kaggle](https://www.kaggle.com/datasets/karamalhamad/syria-official-gazette-companies-and-decrees).

Corrections: see https://gov.nawafith.net/en/access
