For this lab, I used Microsoft Copiolot to troubleshoot and give suggestions for some of the errors I encountered.

When creating my data file, I was unable to add my empty file using the git command data/empty.

fatal: pathspec 'data/empty' did not match any files

I pasted the error into AI and asked for an explanation. I thought the error was saying that my file did not exist. But the AI explained that git cannot stage a file that is truly empty. I asked if there was another route because I didn't want to add a random file in there and it said to use the command data/

I used AI's suggestion, it said that command accounts for everything in that folder without having to write it out. I used this method to make my other directory as well (scripts) Before adding the files to my directories, I used git status to make sure that I had everything that I needed there.

When typing up my README.md, I also used AI to clarify on what I should include. I typed and pasted an outline of my file to ask if it was apropiate but, I had typed up a lot that would be considered "tribal knowledge," as this was my first time creating a README file. Originally, I put a lot of itital set up code in Terminal and Github, that was uncessary. The AI told me to take the set up code out of my file and only keep the code on reproducing the enviroment, which is what I did. To sanity check, I googled README file samples and tried to understand and simulate the outline they did.

I also used AI to help me write additional script after what I had originally practiced in the Week 1 demo. The code AI suggested I add was to labone4201.Rproj and then command renv::restore():

Open file "labone4201.Rproj"
Once project loads, type in renv::restore()

However, I noticed that the project file was not in the rubric and that I could not use that path to open the enviroment. So I asked AI again for a different way and it gave me a command to set a working directory in R from folder, and then do the restore command.

setwd("~/Desktop/labone4201")
renv::restore()

Also during my practice, when I typed the command source(analyze2.R script), I got an error when practicing the cloning step of the repo on my device. 

Attaching package: ‘dplyr’
The following objects are masked from ‘package:stats’:
    filter, lag
The following objects are masked from ‘package:base’:
    intersect, setdiff, setequal, union
Error in check_for_XQuartz(file.path(R.home("modules"), "R_de.so")) : 
  X11 library is missing: install XQuartz from www.xquartz.org

I asked AI to explain what the error meant, and it said that it was because I incldued the command View(df) in my script. The AI suggested to remove it because I was working in a GUI window without the visualization component I needed to complete that command, which ended up working. To sanity check this, I used one of my old renv.lock projects that I checked the script did not have the View command, before I went back and changed the script in my repo.

