# Current directory
dir0 <- getwd()

# Set current working directory
setwd("C:/Users/wanke/Documents/Rprog/")
dir1 <- setwd("C:/Users/wanke/Documents/Rprog/")

#-----------------------------------------------------------------------------
# R built-in data sets
#
# http://www.sthda.com/english/wiki/r-built-in-data-sets
# To see the list of pre-loaded data, type the function data():
data()

#Select CO2 uptaken by trees
data(CO2)
head(CO2, 10)
?CO2

#--------------------
# Tutorials from CO2

require(stats)
require(graphics)

# plot 3x4 grid plots
coplot(uptake ~ conc | Plant, data = CO2, show.given = FALSE, type = "b")

## fit the data for the first plant
fm1 <- nls(uptake ~ SSasymp(conc, Asym, lrc, c0),
           data = CO2, subset = Plant == "Qn1")
summary(fm1)

## fit each plant separately
fmlist <- list()
for (pp in levels(CO2$Plant)) {
  fmlist[[pp]] <- nls(uptake ~ SSasymp(conc, Asym, lrc, c0),
                      data = CO2, subset = Plant == pp)
}
#-----------------------------------------------------------------------------

# save EXCEL Spreadsheet
# install.packages("xlsx")

library(xlsx)

# write.xlsx(CO2, "C:/Users/wanke/Documents/Rprog/CO2.xlsx", row.names=FALSE)

file <- paste(dir1, "/CO2_paste.xlsx", sep="")
write.xlsx(CO2, file, row.names=FALSE)  

# ExCEL > Returns a data frame
# install.packages("gdata")

library(gdata)
# help(read.xls) # manual for the functions in gdata lib

mydata = read.xlsx("CO2.xlsx", 1)
