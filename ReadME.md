# Using R to Compare Annual Precipitation between Southern Coal Fields and Valley and Ridge Regions of West Virginia (2000-2010)

The objective of my final project is to compare annual precipitation amounts from 2000 to 2010 between the Southern Coal Fields region of West Virginia and the Valley and Ridge region. Landslides are more prevalent in the southern parts of West Virginia compared to the north and I want to see if differences in precipitation amounts are a factor. I will utlize R to implement exploratory data anaylses techniques to explore more about the data sets. These data are coming from 4 stations: BECKLEY RALEIGH CO AIRPORT, WV US GHCND:USW00003872, PRINCETON, WV US GHCND:USC00467207, GLADY 1 N, WV US GHCND:USC00463464, and KEYSER 2 SSW, WV US GHCND:USC00464840. These stations were from the Annual Observational Data Map from NOAA https://gis.ncdc.noaa.gov/maps/ncei/cdo/annual.

## Getting Started

Begin by cloning this repository to retrieve the csv files containing total annual precipitation amounts for 4 stations. Two are in the Valley and Ridge region and the other two are in the Southern Coal Fields region.

### Prerequisites

#### Packages
* library(ggplot2)

### Installing
install.packages("ggplot2")

### Read in the data using 'read.csv()'
Where are the data from?  A stronger project would have included a bash script or read.cv from the url rather than providing data.
Read in more efficiently using apply().  What if you had 50 stations?
```
Princeton <- read.csv(file="Princeton.csv")
Beckley_Raleigh <- read.csv(file="Beckley_Raleigh_Airport.csv")
Keyser <- read.csv(file="Keyser.csv")
Glady <- read.csv(file="Glady.csv")
```

## We will begin by producing boxplots for each of the datasets to learn more about the data.
Could be more efficient with apply()
```
Princeton_boxplot <- boxplot(Princeton$PRCP, main= "Princeton Annual Precipitation")
BeckleyRaleigh_boxplot <- boxplot(Beckley_Raleigh$PRCP, main= "Beckley_Raleigh Annual Precipitation")
Glady_boxplot <- boxplot(Glady$PRCP, main= "Glady Annual Precipitation")
Keyser_boxplot <- boxplot(Keyser$PRCP, main= "Keyser Annual Precipitation")
```


## Next we can create some barplots to look at the frequency.
```
Barplot Script
Glady_Precip_bar <- barplot(Glady$DATE, main = "Glady Precipitation", xlab = "Total Annual Precipitation (mm)", col= "darkred")
Keyser_Precip_bar <- barplot(Keyser$PRCP, main = "Keyser Precipitation", xlab = "Total Annual Precipitation (mm)", col= "darkred")
Princeton_Precip_bar <- barplot(Princeton$PRCP, main = "Princeton Precipitation", xlab = "Total Annual Precipitation (mm)", col= "darkred")
BeckleyRaleigh_Precip_bar <- barplot(Beckley_Raleigh$PRCP, main = "Beckley_Raleigh Precipitation (mm)", xlab = "Total Annual Precipitation", col= "darkred")
```
Insert example image here.


## Finally, we can plot the data to look at trends. 
Again, could be more efficient with apply()
```
Princeton_plot <- ggplot() + geom_line(aes(y = PRCP, x = DATE), data = Princeton)
BeckleyRaleigh_plot <- ggplot() + geom_line(aes(y = PRCP, x = DATE), data = Beckley_Raleigh)
Glady_plot <- ggplot() + geom_line(aes(y = PRCP, x = DATE), data = Glady)
Keyser_plot <- ggplot() + geom_line(aes(y = PRCP, x = DATE), data = Keyser)
```


## Authors
?????
* **Billie Thompson** - *Initial work* - [PurpleBooth](https://github.com/PurpleBooth)

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.


## Acknowledgments
????
* Hat tip to anyone whose code was used
* Inspiration
* etc
