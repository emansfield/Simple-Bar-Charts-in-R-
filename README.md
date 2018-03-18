# Simple-Bar-Charts-in-R-
A beginner's guide to making simple, exportable bar charts in R. This guide is ideal for someone who is already using Excel and Tableau but is trying to transition to R, or someone who wants to learn basic functions of R. 

### To start, install the tidyverse package
This is the main package for making graphics in R. You'll use the command install.packages("tidyverse") to install, and then the command library(tidyverse) to pull it up so you can use the tidyverse. 

### Set your working directory 
Set your working directory. You should have already created a folder on your computer for where you want to access your data and save your outputs. An easier way to set the wordking directory is by going to the bottom righthand corner, clicking "files" and finding the folder you want to use. From there, click "more" and then "set as working directory." 

### Then, bring your data in through a .csv file
After you've set your working directory, use read.csv("File name.csv") to bring in your data. For the purposes of this tutorial, we're going to assume your data has already been cleaned. If you need help cleaning your data in R, use another tutorial first. 

### Set your data as a variable in R 
Use the following line of code to assign a variable name to your data. Use a name that's short and one word long.  
  
variable <- read.csv("File name.csv")  

### Start with the basic code for a bar chart 
The code below will make you a basic bar chart, no colors and no legend. 
  
ggplot(data = variable) +  
geom_bar(stat = "identity", aes(x = column name1, y= column name2, fill=TRUE, show.legend=FALSE)) +  
ggtitle("Chart Title") + 
xlab("Label for Horizontal Axis") +  
ylab("Label for Vertical Axis")   

### Make changes to your bar chart to make it more visually appealing 
The code below will make a bar chart with teal bars and remove the gray background. This may be more visually appealing for printing.  
  
ggplot(data = variable) +  
geom_bar(stat = "identity", aes(x = column name1, y= column name2, fill=TRUE, show.legend=FALSE)) +  
ggtitle("Chart Title") +   
xlab("Label for Horizontal Axis") +  
ylab("Label for Vertical Axis") +  
theme_minimal() +  
scale_fill_manual(values=c("turquoise4"))  

### Customize the color of your bars
Go to this website (http://sape.inf.usi.ch/quick-reference/ggplot2/colour) or download the .jpg file in the .zip file to find a color you want. Then pick the color and put the name inside the quotation marks in this line of code -- scale_fill_manual(values=c("limegreen")) -- at the bottom of this chunk of code. For example, this will make you a chart with lime green bars instead of teal bars.  
  
ggplot(data = variable) +  
geom_bar(stat = "identity", aes(x = column name1, y= column name2, fill=TRUE, show.legend=FALSE)) +  
ggtitle("Chart Title") +   
xlab("Label for Horizontal Axis") +  
ylab("Label for Vertical Axis") +  
theme_minimal() +  
scale_fill_manual(values=c("limegreen"))  

### Keep the gray background if you want
To keep the gray background, get rid of -- theme_minimal() -- from the chunk of code. Or copy and paste the code below.  
  
ggplot(data = variable) +  
geom_bar(stat = "identity", aes(x = column name1, y= column name2, fill=TRUE, show.legend=FALSE)) +  
ggtitle("Chart Title") +   
xlab("Label for Horizontal Axis") +  
ylab("Label for Vertical Axis") +  
scale_fill_manual(values=c("limegreen"))  


Credits: R for Data Science (Wickham, Grolemund), SAPE Research Group 
