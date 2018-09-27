# The Analytics Edge

## Video 4: Loading Data Files

Firstly import WHO.csv file in R studio and then perform the following commands.

```
str(WHO)            ->To view structures of dataset.
summary(WHO)        ->To view summary of each variable.
                      ->This will give us:
                                        -Min
                                        -1st Quartile
                                        -Median
                                        -Mean
                                        -3rd Quartile
                                        -Max
```

`WHO_Europe = subset(WHO,Region=="Europe")`     ->Create a new dataset with only the countries in Europe.

`write.csv(WHO_Europe,"WHO_Europe.csv")`        ->Save the data to a csv file.WHO_Europe.csv is th ename of the file to which we want to save.
`ls()`      ->To list all variables.
`rm(WHO_Europe)`        ->To delete WHO_Europe variables.


## Video 5: Data Analysis - Summary Statistics and Scatterplots

```
WHO$Under15             ->This outputs the Under15 vector of the dataframe WHO.  
mean(WHO$Under15)       ->To get mean.  
sd(WHO$Under15)         ->To get standard deviation.  
summary(WHO$Under15)    ->To get summary.  
```

1st Quartile    ->It is the value for which 25% of the data is less than that value.  
3rd Quartile    ->It is the value for which 75% of the data is less than that value.  

`which.min(WHO$Under15)`    ->This will give row number of minimum value in Under15.  
`WHO$Country[row.no]`        ->To view the name of a country in a specific row.  
`which.max(WHO$Under15)`    ->This will give row number of maximum value in Under15.  
`plot(WHO$GNI,WHO$FertilityRate)`   ->To plot a graph.  
                                    -GNI on x-axis  
                                    -FertilityRate on y-axis.  

`Outliers=subset(WHO,GNI>10000 & Fertility>2.5)`        ->This will save the content in outliers which satisfies both conditions.  
`nrow(Outliers)`        ->This will give the number of rows in outliers and since each row contains only one country so the number of rows will tell us the number of country.  
`Outliers[c("Country","GNI",FertilityRate")]  








