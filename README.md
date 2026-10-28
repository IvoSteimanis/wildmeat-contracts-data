# Data: Temporary voluntary compensation contracts reduce wild meat sales in a zoonotic disease hotspot

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23734932.svg)](https://doi.org/10.5281/zenodo.23734932)

De-identified data for the working paper by Ivo Steimanis, Natalie Struwe, Julian Benda, Cyrille Doho,
Esther Blanco and Björn Vollan. This first version contains the cleaned datasets used in the paper. The full
replication package (code to reproduce every table and figure) will be added to this record once the paper
is accepted.

## Study

A field experiment with owners of informal restaurants (*maquis*) in Yopougon, Abidjan, Côte d'Ivoire
(2025), with a twelve-month follow-up survey (2026), and a companion online donation experiment with
European participants recruited through Prolific (2025). Owners who attended an accounting workshop were
randomly offered either a poster contract (*poster*) or a poster contract with weekly compensation for not
selling wild meat (*poster + compensation*). The study was pre-registered on the Open Science Framework
and approved by the ethics committees of the University of Innsbruck (Certificate 125/2024), the School of
Business and Economics of Marburg University, and CSRS (Abidjan).

## Files

All files are provided as Stata (`.dta`, with variable and value labels) and CSV (codes only). Each has a
codebook in `codebooks/` (variable name, type, variable label, value label name).

| File | Unit | Rows | Content |
|---|---|---|---|
| `data/field_survey_2025` | owner x survey wave | 546 | Baseline (2025) and endline surveys of restaurant owners; assignment (`participation`: 0 non-participant, 1 poster, 2 poster + compensation) and contract take-up (`started_project`) |
| `data/accounting_daily` | restaurant x day | 2,087 | Daily accounting records (sales, revenues, expenses, profit, wild meat sales); `est_sample == 1` marks the estimation sample of the paper (53 restaurants, 2,062 days) |
| `data/accounting_dishes` | dish line | 13,542 | Dish-level accounting records: dish category, wild meat indicator, species group, number sold, price |
| `data/followup_2026` | owner | 161 | Twelve-month follow-up survey, including the multiple price list (`accept_10000` ... `accept_65000`, CFA per week) |
| `data/donation_experiment` | participant | 2,131 | Online donation experiment: donation (GBP, endowment 1.50), beliefs, demographics |

Monetary values in the accounting files are in CFA francs (1 EUR = 655.957 CFA). In the string variable
`treatment`, "Affiche" is the poster arm and "Pas de viande de brousse" the poster + compensation arm.

Not included: the 2024 consumer survey behind the Supplementary Information section on wild meat consumption in
Yopougon. It will be released with the companion paper on wild meat consumption.

## Linking files

`release_id` identifies a restaurant consistently across the four field files (`field_survey_2025`,
`accounting_daily`, `accounting_dishes`, `followup_2026`). It is a random identifier created for this
release; it cannot be linked to the project's internal identifiers. `day_id` links `accounting_dishes` to
`accounting_daily`. The donation experiment is a separate sample (`participant`).

## De-identification

- All names (owners, restaurants, contacts, enumerators), telephone and mobile-money information, GPS
  coordinates, device identifiers, consent-photo links, survey timestamps and platform metadata
  (KoboToolbox, oTree, Prolific identifiers and session codes) were removed.
- Every free-text field was removed. Multiple-choice questions are kept as 0/1 indicator variables.
- Enumerators are numeric codes. Restaurant identifiers were replaced by random release identifiers.
- Dish names were replaced by a species group derived from them.

## License and citation

Data released under CC BY 4.0 (see `LICENSE`). Please cite this record using its Zenodo concept DOI (see
`CITATION.cff`) and the paper.

## Funding

We are thankful for financial support by the Volkswagen Foundation (Ref. 9C 446) and the Austrian Science Fund (FWF,
Grant DOI 10.55776/F63).

## Contact

Ivo Steimanis, Philipps University Marburg.
