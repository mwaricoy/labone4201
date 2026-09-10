The first step is making a a new folder in your device. This can be done through clicking create a new folder in Mac, or can be done through terminal

pwd
ls
cd Desktop
mkdir labone4201

Need to make another directory in folder in order to connect it to github

mkdir README.md

Next, we are going to make a repo in Git hub with the same name as this folder.

cd ~/Desktop/labone4201
git init
git status

The return should be an empty :

git remote add origin https://github.com/YOUR-USERNAME/labone.git
git push -u origin main

Enter your username and use this link to generate a token to use as a password:

Still in your labone4201 folder, create a .gitignore

git add .gitignore
git commit -m "Add .gitignore"
git push

Because this project does not involve importing any datasets, you can do the something similar done above and leave the folder empty.
In (base) DEVICE:labone4201 USERNAME$ ..

mkdir data

Make an empty file (I called mine empty) and I manually added it to my data folder. Or you can use Terminal ..

cd data
add empty

Then add it to git hub

git add data/ 
git commit =m "Add data"
git push

Now make a reproducable enviroment in R. Swtich from terminal to RStudio and click Creaet Project under File.
In the new window, click exiting directory. Click browse and search through Files and add your folder labone4201 as the working directory (or whatever folder name is conencted to your repo)


dir.create("~/repro-demo/renv-version2")
setwd("~/repro-demo/renv-version2")
renv::init()

This should initialize a lockfile shown in your renv-version2 folder in R.
Now we install an R package that we are going to analyze (dplyr).

install.packages("dplyr")

The system will ask if you want to proceed, say/type Y for yes.
It should give you a list and at the end say the pacakages were successfully installed.
Next code:

library(dplyr)
df <- data.frame(patient_id = c("P001", "P002", "P003"), age = c(54, 61, 47))
View(df)
summary(df)

Take a note of the summary, as these numbers must be the same when we run our check test (the min, mean, and max ages numbers).

Now in the top left corner there is an icon with a white page and a green plus sign, click this and in the drop down menu create a new script. 
Save this script as analyze2.R
Copy and paste these lines that you just entered to the console (or terminal) into the script and save it.

library(dplyr)
df <- data.frame(patient_id = c("P001", "P002", "P003"), age = c(54, 61, 47))
summary(df)

Then in the console take a snapshot

renv:: snapshot()

To check that we snapshotted the right thing, we need to run a check using this code:

renv::deactivate()
unlink("renv/library", recursive = TRUE)
renv::activate()
renv::restore()
source("analyze2.R")

You should see the same numbers (max min, and mean). This means your enviroment worked!

If there's an error after runnning source("analyze2.R"), then go back and run lines 59-62 again and try saving the lines again in analyze.R and take the snapshot after. 

Save everything 
