1. How to Import SAS XPORT files into R with the foreign package?

library(foreign)
write.foreign(mydata, “c:/mydata.txt”,
“c:/mydata.sas”, package=”SAS”)

#export data frame to stata binary format
library(foreign)
write.foreign(mydata, “c:/mydata.dta”)


2. How to Import SAS Files into R with the Haven package?

#Save SAD dataset in the trasport format
libname out xport ‘c:/mydata.xpt’;
data out.mydata;
set sasuser.mydata;
run;

#in R
library(Hmisc)
mydata<-sasxport.get(“c:/mydata.xpt”)

3. How to read Weka Attribute-Relation File Format (ARFF) files in R?
library(RWeka)

read.arff(system.file("arff", "contact-lenses.arff",
                      package = "RWeka"))


4. How to read a heavy csv/tsv file using readr package?
install.packages("readr") # installing readr package

library(readr) # loading the package 

read_csv(file, col_names = TRUE)  # Read comma (",") separated values

read_csv2(file, col_names = TRUE)  # Read semicolon (";") separated values

read_tsv(file, col_names = TRUE)  # Read tab separated values 
