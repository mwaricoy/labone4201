#To make your clone. To do this, use this code in Terminal

cd ~/Desktop

git clone https://github.com/mwaricoy/labone4201.git

cd labone4201

ls

#Next you need to open the enviroment in R by setting a working directory. Type this code into the console:

setwd("~/Desktop/labone4201")
renv::restore()

#After this, you can now run the scrip with this command in the console

source("scripts/analyze2.R")

#The output should be this:

#(Attaching package: ‘dplyr’ The following objects are masked from ‘package:stats’: filter, lag The following objects are masked from ‘package:base’: intersect, setdiff, setequal, union)
