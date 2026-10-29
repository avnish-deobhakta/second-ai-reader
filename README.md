# A second AI reader catches more missed disease when trained on different data

Code for the study by Deobhakta, Rosen, Tai, Tsai, Harris and Pasquale (New York Eye and Ear Infirmary of Mount Sinai). Every notebook is published as it was run on Google Colab, with its outputs. The plan, lock and results files sit in `plans_and_results/`; each confirmatory plan was written, dated and hashed before the data it tests were examined.

## Layout

- `notebooks/01_eyepacs/`: splits, training of the 33 EyePACS models, the held-back test set, the primary analysis (`09_lock_v3_and_fresh_eval`), partner choice (lock v4), exploratory analyses and the harm-weighted secondary analyses (`18`, `18b`).
- `notebooks/02_ddr/`: DDR intake, inference and the confirmatory DDR analysis (lock v5.1); training of the 12 DDR-trained models.
- `notebooks/03_brset/`: BRSET download, inference and the confirmatory BRSET analysis (plan v6), with follow-ups.
- `notebooks/04_skin/`: skin intake, training of the 24 skin models, the confirmatory analysis and exploratory follow-ups.
- `notebooks/05_similarity/`: degradation fingerprints and predicting shared misses from the models.
- `notebooks/06_figures/`: figure notebooks.
- `plans_and_results/`: plans, locks and aggregate results.

## Where each main result comes from

| Result | Notebook |
|---|---|
| Primary: net severe misses against the better member, EyePACS | `01_eyepacs/09_lock_v3_and_fresh_eval` |
| DDR results, and the copied 25% share | `02_ddr/DDR_analysis_v5_1` |
| BRSET results, training-data effect, sibling test | `03_brset/BRSET_analysis_v6`, `03_brset/BRSET_exploratory` |
| Skin results and training-data effect | `04_skin/DERM_analysis` |
| Choosing by error overlap (partner-choice test) | `01_eyepacs/CONFIRM_lock_v4`, with `EXPLORE_frontier_v2` and `EXPLORE_buying_rule_v2` |
| Starting weights against architecture | `01_eyepacs/STARTING_WEIGHTS_part2` |
| Sibling agreement and local partner choice | `01_eyepacs/SIBLINGS_detector`, `PARTNER_choice_calibration`, `ENRICHED_calibration` |
| Degradation fingerprints | `05_similarity/BALLISTICS_*` |
| Floor of shared misses among EyePACS-trained models | `05_similarity/PREDICT_from_models_v2` |
| Harm-weighted analysis and the two bounds | `01_eyepacs/18_literature_weighted_secondary_v2`, `18b_two_bounds_v2` |

## Notes

- `TRAIN_ddr_v2_pilot` is the full training run of the 12 DDR-trained models; the name is kept as run.
- `03b_aptos_inference_allseeds_v2` made predictions on APTOS 2019. APTOS was not analysed because it releases no patient identifiers, so patient-level analysis is impossible.
- BRSET is available to credentialed users from PhysioNet. No BRSET record-level data are in this repository; credentialed users can regenerate the predictions with these notebooks.
- Per-image predictions for the openly available test sets, the split files and the model checkpoints are archived at Zenodo: [DOI to be added].
