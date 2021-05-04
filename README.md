# Interactive Katacoda Scenarios (PLEASE READ THE NOTE)

[![](http://shields.katacoda.com/katacoda/kimberlywolf/count.svg)](https://www.katacoda.com/kimberlywolf "Get your profile on Katacoda.com")


## Project Overview

In this project, we have created a basic tutorial in Katacoda. In this repo however, it includes several "test files" that were meant as a template for 
us to create our final project. Here, we only want to focus on the FinalProject folder. In this folder, we create a simple Docker program that can teach 
students: how to write the files needed to run Docker, the basic commands to create and run a docker container, and other basic commands that can show 
the basic fundamentals of Docker.

## Setup

To create a Katacoda scenario, a lot needs to be done. For starters, you will need to create a free Katacoda account on Katacoda's website. From there, 
you will be promted to follow a tutorial. While the following information is stated in that tutorial, we found some discrepancies while following it and 
make note of it here. You will need to follow along with the Katacoda tutorial in order to access Katacoda's website. After you create your new account, 
you will need to install the Katacoda CLI, which requires Node.js to already be installed on your system. The Katacoda website provides the link needed 
download Node.js. Once Node.js is installed, you will need to run the following command in the terminal: ***sudo npm install katacoda-cli --global*** The 
command ***sudo*** needs to included in this line of code, otherwise the Katacoda CLI will not install. Katacoda does not state this on their website however. 
Once Katacoda is officially installed on your system, you will need to link your GitHub account to the Katacoda website via a Webhook. Thankfully, the 
Katacoda website provides this as part of their tutorial after you create your account. 

After all of that is step up, we can finally create our first scenario. You will need to run the following command in the terminal: ***katacoda scenarios:create*** From there, you will be prompted to type in a "Friendly URL" or the name of the directory you are creating. Next, it will prompt you for the title of your 
scenario, followed by the description of the scenario. Then, you will be asked to select a difficulty from *Beginner, Intermediate,* and *Adavnced*. You can 
select them with your arrow keys. Next, you will be asked for the "Estimated Time" needed to complete your tutorial. You will then be asked for the number 
of steps in the program, not included the intro and finish sections of the program. From there, you will be prompted for the "Image," or the programming 
language you want to write in. In this scenario, we have used "python:3.8." Finally, it will ask for the layout of the tutorial. This layout indicates whether 
or not you want just the terminal, a text editor program (similar to Atom) along with the terminal, and much more.  Once that is all done, you now have a basic 
template of a Katacoda tutorial.

If you open up the directory you have just made, you will notice several markdown files labeled step.md, intro.md, finish.md, along with an index.json file. 
This index.json file incudes all of the information you put in when creating the scenario just moments ago. There, you can add features to the program, such 
as adding files from your own computer into the program, so they can be utilized in your tutorial. Unfortunately, we were not able to get that to work in our 
tutorial. In all of the markdown files, this is where you will put all of the text and commands that the student needs to go through the tutorial. Katacoda 
has a pluggin that allows for you to execute lines of code in the terminal just by clicking on the text, as well as a copy feature. The execute command can be 
run like this: ***`TERMINAL LINE OF CODE`{{execute}}***. The copy command can be run like this: ***`LINE OF TEXT OR CODE`{{copy}}***. 

Once you have made any changes to the markdown and json files, you will need to send it over to GitHub. You will run ***git add .*** , then run the 
***git commit -m "Commit message"***, and finally, run ***git push***. You should be able to go to your Katacoda account and notice that your program, with 
all the changes that were made, is there and ready to be used. Note, we found that running ***git push origin*** or ***git push origin BRANCH_NAME*** does 
**NOT** update the Katacoda website. The program will not be created nor updated if those lines are run. We have not found a way to work around that, nor 
do we know why that occurs.

## Technologies Used/ Background

Here are the links we used in order to install, create, and run our program:

<https://www.katacoda.com>

*This link is the direct download page of Node.js. This was provided from Katacoda themselves:*

<https://nodejs.org/en/download/>

<https://hub.docker.com>


### NOTE:

When creating and pushing files to GitHub, using "git push origin" does NOT create or update the program on Katacoda. I am not sure why that happens!
Using "git push" is the only way to combat that. I am not sure if this effects creating branches or not. Testing that has been done in a separate
repo shows that creating a branch and using "git push origin -*branch name*-" does NOT add it to Katacoda.

-Kim
