# Did Patch 5 Causally Increase Player Engagement in Baldur's Gate 3?

## Overview
`Baldur's Gate 3` is an RPG game that was released for PCs on the 3rd of August 2023 and saw unprecedented acclaim.<br>
With this project, rather than studying the launch effects of the game, I'll estimate the causal effects of the post-launch content update of Patch 5 on engagement using a Difference-in-Differences framework.

#### Library Dependencies:
jsonlite<br>
ggplot2<br>
dplyr<br>
lubridate

# Project Objectives
This project will estimate the impact of `Baldur's Gate 3` Patch 5 on player engagement on Steam. Patch 5 was specifically chosen for our treatment, as it is a major update to the game, far enough from the launch date so that the initial launch spike had already decayed and the player counts had reached a stable trajectory.<br>
With this in mind, engagement might still be affected by word-of-mouth growth and the award season buzz.

**Hypothesis**: Patch 5 had **no effect** on average player engagement for `Baldur’s Gate 3` relative to the control game.<br>
**NULL Hypothesis**: Patch 5 had a causal effect on average player engagement for Baldur’s Gate 3 relative to the control game.<br>
**Alpha**: All statistical inference is conducted using conventional significance thresholds (α = 0.05), though results are interpreted cautiously given data limitations.<br>

The estimated treatment effect may partially capture increased visibility from awards that coincided with the post-treatment period, notably the *Golden Joysticks Awards* on November 11, 2023, and *The Game Awards* on December 7, 2023, and these awards can be classified as confounders.

# Dataset
The data used on this assignment was downloaded as `.json` files for each game from [Steam Charts](https://steamcharts.com/).

## About the Dataset
Each file contains only two columns, one for the time, in milliseconds, and one for the average number of players of the game that the file corresponds to.<br>
*Data Limitation*:
Unfortunately, after getting the data from Steam Charts and wrangling it for a while, I came to the conclusion that the two games previously chosen, `Divinity: Original Sin 2` and `Disco Elysium` didn't have representation within the timeframe used in this project, so a new control group had to be found. After some scoping of potential games, `Hogwarts Legacy` was chosen, as it follows the same premises as the two previous games, albeit with different gameplay style. `Hogwarts Legacy` doesn't have any major updates or DLCs released within the treatment window, doesn't have major sales, and is still within the RPG genre, meaning the general audience should be similar, and has data available for the time period we're interested in.

# Conclusion
Overall, the analysis suggests that Patch 5 was associated with an increase in player engagement for `Baldur’s Gate 3` relative to the control title, `Hogwarts Legacy`. While the graphical evidence shows a clear divergence in trends following the patch release, the results should be interpreted with caution. The post-treatment period coincides with external events, such as major award announcements, which may have contributed to higher player counts alongside the patch itself. As a result, although the findings are consistent with a positive treatment effect, part of the observed increase may reflect broader visibility and publicity rather than the patch alone.<br>
Going forward, it would be interesting to redo this project with access to higher-frequency data, as the data collected only allowed for a monthly analysis, having a weekly analysis might yield different results.<br>
Expanding the control group would also allow for a different analysis, especially with similar games as the intended `Divinity: Original Sin 2` and `Disco Elysium`, unfortunately data for these two games wasn't available for the period that this project was interested in analysing.<br>
An extension of this project could also be examining engagement effects over a longer time period.
