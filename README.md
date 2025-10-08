# CCAM Tunneling Project

Current project aimed at understanding tunneling as a phenomenon based on a hitter's observation of pitches along their path.

Tunneling metric is quantified by creating a lattice between subsequent pitch types, measuring points across 200 timestamps across the trajectory of each pitch type (measured using
9-pitch parameters from baseball savant data. The bounds for this are between pitch release and hitter reaction point (150 ms before pitch crosses home plate).

To test this metric, I created a "swing decision model" which attempts to isolate a hitter's swing decisions away from how effective a pitch is on its own.
The swing decision metric takes into account pitch speeds, movements, approach angles, release points, hitter and pitcher handedness, count, among a multitude of other factors.
These factors are used in multiple binary classification lightgbm models to predict the event that is most likely to occur from this pitch's individual characteristics. These events are mapped
to run values, and then compared to the actual outcome of the pitch. This model predicted the correct event ~64% of the time. After, real outcome and predicted outcome are compared, the
difference between the two is meant to represent the discrepancy between a hitter's swing decisions and the effectiveness of the individual pitch, hoping to quantify the effects of factors
outside of how effective the individual pitch was.

