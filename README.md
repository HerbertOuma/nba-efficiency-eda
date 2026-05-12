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
