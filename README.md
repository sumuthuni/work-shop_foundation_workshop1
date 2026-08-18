# work-shop_1_Foundation
Introduction
#Workshop1#Programming fundamental
#S.Sumuthuni
#This workshop introduces the fundamental concepts 
#of R programming and the RStudio environment for scientific data analysis. It focuses on developing essential skills in data manipulation, basic coding, and data visualisation to support reproducible and efficient research workflows

#run the calculation
``{r} 2+1
1:30
#Incomplete line of code
6*2 
#Error unexpected 
6%2
#corrected 
6/2
#Functions and arguments
``{r} year_old <- 25.7
round (year_old)
floor(year_old)
# For instance, round has an argument that lets you specify how many decimal places you want to round a number to
 ``{r} year_old<-25.765
 round (year_old, 2) #comma after the object to specify argument.

#Object and the assignment operator
#Saving a single value 
``{r} coral_count <- 42
#saving a vector of multiple fish lengths (in mm)
``{r} fish_lengths <- c(124, 152, 98, 221, 146)
#Manipulating objects
``{r} coral_count + 1
coral_count + coral_count
Coral_Count <- 1 #Note that Cases Matter
coral_count + Coral_Count

#Object naming rules
01_age <- 25 # starts with a number cause unexpected error
!_age <- 25 # no special symbols
Error: unexpected input in "!_"

``{r} coral count <- 25 # no spaces
Error: unexpected symbol in "coral count"

``{r}`coral count` <- 25 # spaces used but with back ticks

#Debugging code
# Field survey data
``{r} quadrat_area_m2 <- 0.25
number_of_quadrats <- 16
total_area_surveyed <- quadrat_area_m2 * number_of_quadrats

#Spelling mistake 'tolal_area_surveyd'
``{r} print(total_area_surveyed)

#Installing and Loading packages
# library(tidyverse) # load into current session
library (dplyr)
library (ggplot2)

#Data types
# Assign variable values
site_name <- "Heron_Island"
transect_depth_m <- 12.5
bleaching_present <- TRUE

# Check using function class()
class(site_name)
class(transect_depth_m)
class(bleaching_present)

# Check using function str()
str(site_name)
str(transect_depth_m)
str(bleaching_present)

#Exercise: rounding numbers
# Tracking the age of an old-growth Porites coral colony
years_old <- 25.765

# Clean this up for our summary report
round(years_old, 2)#spelling mistake _olld

#data structure
fish_lengths <- c(124, 152, 98, 221, 146)
coral_spp <- c("Porites", "Acropora", "Montastrea")

notes <- c("Acropora", 27.5, TRUE)
#List
notes <- list("Acropora", 27.5, TRUE)

notes[[1]]

#Data frames and tibbles
``{r} my_dataframe <- data.frame (no = c(1,2,3), c("Plectropomus", "Scarus", "Pomacentrus"), c(TRUE, FALSE, TRUE)
my_dataframe
str (my_data_frame)

#get the table to be saved in output folder
``{r} getwd()
write.csv(
+     my_data_frame,
+     "C:/Users/user/Downloads/my_data_frame.csv",
+     row.names = FALSE
+ )

#do this by accessing the column and changing its type:
``{r} my_data_frame$no = as.factor(my_data_frame$no)
str (my_data_frame)
