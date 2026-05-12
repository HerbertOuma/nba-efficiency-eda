# NBA Playoff Competitiveness: Efficiency Differential vs. Seeding
Herbert Ouma — Choose Your Own Hypothesis EDA Project

Hypothesis Question

Does a team's regular-season efficiency differential (ORtg − DRtg) predict playoff series competitiveness better than seeding alone?


Hypothesis
H₀: Regular-season efficiency differential between two playoff opponents has no stronger association with series competitiveness (games played) than their seeding differential.
H₁: Efficiency differential is a significantly stronger predictor of series competitiveness — teams closer in net rating produce longer, more competitive series regardless of seed.
Intuition: The NBA seeds teams 1–8 within each conference based on win-loss record. But two teams can have the same seed gap and wildly different efficiency profiles. This project tests whether the efficiency gap — how far apart two teams are in points per 100 possessions, both offensively and defensively — is a truer predictor of how competitive their series will be than the seeding number printed next to their name.

Data Sources
FileDatasetUsed ForTeam Summaries.csvNBA Stats 1947–present by sumitrodattaRegular-season ORtg, DRtg, Net Rating per team per seasongame.csvNBA Database by wyattowalshGame-by-game results used to build playoff series outcomes


Main Findings

Net rating gap is a stronger predictor of series competitiveness than seed gap: r = -0.346 vs r = -0.258
Both correlations are statistically significant, but the efficiency signal is measurably stronger
Permutation test confirms the difference is statistically significant (p < 0.05, 10,000 permutations)
The 2026 playoffs validate the model in real time: OKC's +8.9pt gap over LAL predicted a sweep (3-0); SAS and MIN's near-equal efficiency (+4.2pt gap) predicted their dead-even 2-2 series
NYK/PHI is the most interesting outlier — PHI's 7-seed implied a competitive matchup, but their net rating (+1.4) already told the true story

Methods Summary
StepApproachData loadingTwo Kaggle CSVs: team ratings + game-by-game resultsSeries Grouping playoff games by season + matchup, count wins to determine series outcomeSeason alignmentgame.csv uses season-start year; Team Summaries.csv uses season-end year — applied +1 offsetAbbreviation fixesBKN→BRK, CHA→CHO, PHX→PHO across datasetsSeed derivationRanked playoff teams within each conference by regular-season winsModelingnet_rtg_gap = absolute difference in net ratings; seed_gap = absolute seed differenceEDAScatter plots, boxplots by quartile, Pearson correlationsHypothesis testPermutation test on Δ|r| (10,000 shuffles)Study2026 playoffs mapped onto historical trend as live validation

Limitations

Observational data only — no causal claims
Seed derivation by wins is a proxy for official seeding (excludes tiebreakers and play-in)
Dataset covers 2015–2022; missing 2023–2025 due to game.csv cutoff
Net rating reflects regular-season opponents, not playoff-caliber competition
Games played (4–7) is ordinal; average margin of victory would be a stronger metric
2026 case studies illustrate but are not part of the statistical test
