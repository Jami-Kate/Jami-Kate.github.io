---
layout: default
---


## Introduction

This course was an introduction to all things terminal and command-line related that could be useful for linguistics. While the specific applications were all linguistics related, most, if not all, of the skills can be extended to many analytic and data-driven tasks.

## Week One: Command Line Basics

The primary focus for week one was, unsurprisingly, setting up the command line for your given system. In my case, this involved installing Ubuntu for Windows.

Example Code:
```
cd KIK-LD211
cd..

nano example.txt
```
This code sample shows some navigation and file opening

## Week Two: Navigating a UNIX System

Now that we had our command lines running, this week gave a background to how one actually uses the system. This included navigating the system, file management, access to remote servers, and managing processes.

Example Code:
```
ls
ls KIK-LD211
ls -a

ssh [servername]
ssh [username@servername]
```
This code includes several options for the all-important ls command, as well as some basics for connecting to a remote server.

## Week Three: Basic Corpus Processing

This week involved applying the prior skills onto text files. This also involved commands like grep & how to navigate a csv or other similarly formatted file.

Example Code:
```
dos2unix example.txt
egrep '\bhad [a-z]*ed\b'
```
This shows two types of processing, one on the document as a whole and then egrep to search for a specific instance in the code.

## Week Four: Advanced Corpus Processing

Building on last week's skills, this week involved more complex text processing. We used the sed command primarily, but also worked on creating stronger sequencing of tasks.

Example Code:
```
sed -E 's/that/which/g' example.txt > exampleWhich.txt

cat example.txt | tr -s '\n\r\t ' '\n' | tr -dc "A-Za-z0-9\n" | sort | uniq -c | sort -nr > example.freq
```

This sample includes a simple find/replace with sed, then a more complex pipeline to generate a frequency list for the file opened with cat 

## Week Five: Scripting and Configuration Files

This week took a related tangent to scripting. These scripts mainly served to achieve more automated versions of the text processing we had been doing. This week also invluded a tangent into changing environment variables and setup.

Example Code:
```
#! /bin/bash


if [ $# -ne 1 ]
then
        echo "ERROR: must input a file to read"
        exit 1
fi



while read -r line;
do
        output=$(echo $line | sed -E 's/(.*)/\1er/')
        echo "$output"
done < $1
```
A script to add comparative endings to a file of adjectives

## Week Six: Installing and Running Programs

This week we took another step towards practical usage, installing and using various useful software. This began with Python. This also included the ability to use MakeFiles for better file management and automation of processing tasks.

Example Code:
```
results/%.sent.txt: data/%.no_md.txt
        src/sent_per_line.sh $< > $@

```
A Sample from the Makefile used this week, which is used to create a sentence-per-line txt file for each book listed

## Week Seven: Version Control

This week involved learning about version control, with a particular focus on GitHub as the primary version control hub used worldwide.

Example Code:
```
git add .
git status
git commit -m "[message here]"
git status
git push
```
Given that the final week was all about git, the best example of code used is the sequence of basic git commands used 

## Final Project

The final project is this website here, which involved installing and understanding Jekyll and GitHub pages.

## Concluding thoughts

This is a course that I will forever be annoyed was not offered to be in the first semester of my BA in Computer Science. I always knew enough about how to google to navigate the terminal well, but it seemed we were all just expected to understand how the terminal and its various possibilities worked without ever being given instruction on it. I found it endlessly frustrating, and am angry on behalf of younger Jami that we didn't have this. That being said, I'm very glad to have had the chance to do this course now. Many thanks.
