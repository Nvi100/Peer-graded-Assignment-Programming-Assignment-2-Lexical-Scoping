# Peer-graded-Assignment-Programming-Assignment-2-Lexical-Scoping
Peer-graded Assignment: Programming Assignment 2: Lexical Scoping
# Getting and Cleaning Data Project

This is my repo for the Coursera "Getting and Cleaning Data" final project. The goal here was to take a messy, raw dataset from smartphone fitness trackers and clean it up into a tidy format that's actually easy to analyze.

## What's in here?

* **`run_analysis.R`**: This is the main R script that does all the heavy lifting. You just run it, and it cleans the data.
* **`tidy_data.txt`**: This is the final, clean dataset that gets spit out by the R script. 
* **`CodeBook.md`**: A quick guide explaining all the variable names in the tidy dataset and the exact steps I took to clean things up.
* **`README.md`**: This file!

## How to use it

1. Make sure you have the `dplyr` package installed in R.
2. Put `run_analysis.R` in your working directory.
3. Source the script (`source("run_analysis.R")`). 

You don't even need to download the data yourself—the script checks if you have the files, and if you don't, it downloads and unzips them for you automatically.

## How the script actually works

If you look inside `run_analysis.R`, it basically does things in 5 steps:

1. **Merges the data:** It reads the training and test text files from the UCI HAR dataset and stacks them together into one big dataset. It also attaches the subject IDs and activity codes to the main data.
2. **Filters the data:** The original dataset has hundreds of columns. The script drops everything except for the measurements that deal with mean and standard deviation. 
3. **Names the activities:** It replaces the confusing number codes (1, 2, 3...) with actual words (WALKING, SITTING, etc.) so you know what the person was doing.
4. **Cleans up the column names:** It fixes the variable names so they make sense. For example, it gets rid of weird typos, changes "Acc" to "Accelerometer", and "t" to "Time".
5. **Averages it out:** Finally, it groups the data by each person (subject) and what they were doing (activity), calculates the average for each measurement, and saves this final summary as `tidy_data.txt`.
