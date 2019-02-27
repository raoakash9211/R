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
`Outliers[c("Country","GNI",FertilityRate")]`   ->This will show these three values for the countries in Outliers subset.  


## Video 6: Data Analytics - Plots and Summary Tables

`hist(WHO$CelllularSubscribers)`     ->To create histogram of a value.  
Histogram is useful for understanding the distribution of a variable.  
`boxplot(WHO$LifeExpectancy ~ WHO$Region)`    ->Useful for understanding the statistical range b/w the first & third quartiles with the middle line marking the median value.  
The dashed lines at the top and bottom of the box often called whiskers show the range from the minimum to maximum values including any outliers, which are plotted as circles.  

```
boxplot(WHO$LifeExpectancy ~ WHO$Region,xlab="",ylab="LifeExpectancy",main="LifeExpectancy of Country by Region")       ->xlab for x-axis
                                                                                                                        ->ylab for y-axis
                                                                                                                        ->main for title of graph
```
`table(WHO$Region)`     ->To make table of Region variable.  
`tapply(WHO$Over60,WHO$Region,mean)`     ->This splits the observation by Region and then computes the mean of the variable Over60.  
`tapply` splits the data by the second argument & then apply the third argument function to the variable given as the first argument.  
`tapply(WHO$LiteracyRate,WHO$Region,min,na.rm=TRUE)`    ->This will give the minimum value and will leave the blank entries.  
If we do not apply `na.rm=TRUE`, the the result will be `NA` if there is any blan entry in that row.  


## Video 7: Saving with Script Files

All the commands can be saved in a file and we can run all at one time by selecting all the commands and then by pressing `Control+R`. We can also add comments in the script file.

Comments in R   ->`# Enter comment here`



# Understanding Food : Nuritional education with Data(Recitation)

## Video 2 - Working with Data in R

- Download and import USDA.scv.  
- `getwd()` - To view the current working directory.  
- `USDA=read.csv("USDA.csv")` - To read the info from a dataset.  
- `str(USDA)`   - To view structure.  
- `summary(USDA)` - To view summary.
                    - 1st quartile  
                    - Median  
                    - Mean  
                    - 3rd quartile  
                    - Max  
                    - NA's - blank cells  

## Video 3 - Data Analysis  

- `USDA$Sodium` - To view all entries in a sodium table.  
- `which.max(USDA$Sodium)`  - Tells that which row has max entry.  
- `names(USDA)`     - Names the variables stored in USDA.  
- `USDA$Description` [row. no.]   - To view Description of a perticular row.  
- `HighSodium = subset(USDA, Sodium>10000)` - This will store all the entries which has sodium concentration more than 10000 in a new dataframe HighSodium.
- `nrow(HighSodium)`    - To get no. of rows in HighSodium.
- `HighSodium$Description   - To get Description of the data in HighSodium.  
- `match("CAVIAR",USDA$Description)` - To get desc of the salts in HighSodium.
- `USDA$Sodium [row no.]`   - To get the sodium level of a salt.  
- `USDA$Sodium[match("CAVIAR",USDA$Description)]`  
- `summary(USDA$Sodium)`    - To get summary.
- `sd(USDA$Sodium, na.rm=TRUE)  - To get standard deviation. If we don't use `na.rm=TRUE`, we will get NA as it will remove all Non Availabe entries.  

## Video 4 - Creating Plots in R
```
plot(USDA$Protein,USDA$TotalFat)
plot(USDA$Protein,USDA$TotalFat,xlab="Protein",ylab="Fat",main="Protein vs Fat",col="red")  - To plot the graph.
hist(USDA$VitaminC,xlab="Vitamin C (mg)",main="Histogram of Vitamin C levels")  - To plot histogram.
hist(USDA$VitaminC,xlab="Vitamin C (mg)",main="Histogram of Vitamin C levels",xlim=c(0,100))
hist(USDA$VitaminC,xlab="Vitamin C (mg)",main="Histogram of Vitamin C levels",xlim=c(0,100),breaks=100)
boxplot(USDA$Sugar, main="Boxplot of Sugar levels",ylab="Sugar (g)")
```

## Video 5 - Adding Variables

- `HighSodium = USDA$Sodium = USDA$Sodium>mean(USDA$Sodium,na.rm=TRUE)`  - This will save the value as logical means TRUE/FALES.  
- `str(HighSodium)`  
- `HighSodium = as.numeric(USDA$Sodium>mean(USDA$SOdium,na.rm=TRUE))`   - This will convert TRUE as 1 and FALSE as 0.  
- `USDA$HighSodium = as.numeric(USDA$Sodium>mean(USDA$SOdium,na.rm=TRUE))`  - To add HighSodium to USDA dataframe.  
Repeat the ablve with Fat, Carbohydrates and Proteins.  

## Video 6 - Adding Variables

- `table(USDA$HighSodium)`  - This will show the number of TRUE & FALSE values.  
```
ex:      0       1  
        4884    2090  
```
- `table(USDA$HighSodium,USDA$HighFat)`  
```
ex:      0       1  
0       3529    1355  
1       1378    712  
```
- `tapply(USDA$Iron,USDA$HighProtein,mean,na.rm=TRUE)`  - This will give us the mean value of common TRUE and FALSE i.e. 1 & 0 entries of Iron & Protein.  
```
ex:         0           1  
        2.558945    3.197294  
```
- `tapply(USDA$VitaminC,USDA$HighCarbs,max,na.rm=TRUE)`  
```
ex:       0       1  
        1677.6  2400  
```
- `tapply(USDA$VitaminC,USDA$HighCarbs,summary,na.rm=TRUE)`  
```r
print(hellp)
```
