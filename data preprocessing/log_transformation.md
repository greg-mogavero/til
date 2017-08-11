# Log Transformations

### What are they?

Log transformations are simply the application of the logarithm function to (usually) continuous data. Any logarithmic base can be used, but the natural logarithm is most common. The effect this has is to bring the data into a more normal distribution while still retaining much of the underlying trends and correlations.

### When should they be used?

Log transformations should be used when your data is very skewed, i.e. the mean and median differ significantly. They are especially useful in linear regressions because the log-scale represents _relative_ change, rather than absolute change. This means an exponential trend in the data will become linear, and linear regression will be able to fit a line to the data much better.

### Why should they be used?

Machine learning algorithms tend to work better with normal distributions -- they often converge faster and make more accurate predictions.

### When should they _not_ be used?

Log transformations should not be used to make outliers "fit" into the rest of the data. Outliers should be handled on their own and either removed if they are the result of error, or analyzed further to discover why they exist.