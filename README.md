# nasa-engines
NASA Jet Engine Degradation Prediction Using scikit-learn


#NASA_Jet_Engine_Degradation_FD001.ipynb
My initial attempts with the FD001 files.

I used SQL to clean up the training data, removing invalid columns, as well as columns that displayed no variance, as they would not contribute to the lifespan of the engines.

I also calculated the "Remaining Useful Life" or RUL, of the engines at each time cycle by subtracting the current time from the maximum lifespan of each unit.

I then tried linear regression to find the correlation between the different parameters and the RUL, which led to promising, but less than ideal results.

The Random Forest method boosted the R^2 value to ~0.95, creating a much better fit.

When testing the Random Forest method on the testing data, however, the R^2 score was closer to 0.31. Visualizing the real and predicted data, however, strongly suggests a correlation between them.

I checked for which parameter was affecting the RUL most strongly, and found that it was whatever Sensor 11 was reading, which previous literature on this data agrees with.
