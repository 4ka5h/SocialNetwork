# Social Network
Bash and git based social network tool "sn" for LAN/Intranet environments

# Social Network based on git commands

## Overview
"sn" is a bash script based social network tool using git under the hood. This script enables you to share progress on file, updates, posts and messages in a Local Area Network scenario among other developers. Once installed, you can use "sn --help" for help regarding available options, which is also described later in this page. 

## Getting started
Clone this repo to your local terminal, extract the zip file and execute ```installsn```. Following are the dependencies required for setting up "sn"
1. Install git and execute the ```installsn``` from zip file at each terminal:
    ```
    sudo apt-get update	
	sudo apt install git -y
	sudo apt install tar -y
	```

2. Configure IP address of the rest of the terminals from your networks who can have repos at their end.


## Provided problems 

**The question refer to the following subcommands and characteristics in the order they appear.**

	1. Working subcommand: create
	2. Working subcommand: join
	3. Working subcommand: pull
	4. Working subcommand: log
 	5. Working subcommand: show
	6. Working subcommand: post
	7. Working subcommand: like
	8. Working subcommand: push
	9. Working subcommand: members
	10.Working subcommand: follow
	11.Working subcommand: unfollow
	12.Optional subcommand #1
	
**Based on Git**
**Code split into functions, most of which are smaller than 25 lines**
Most functions of important code blocks start with a comment explaining their functionality.
Unit tests for individual functions
Integration tests that verify the functionality of most subcommands
Tests and/or shellcheck run in a continuous integration environment.
Documentation provided in a README or similar file

Unix manual page

### My Implementation
In order to meet the above requirements, this tool has been developed using Lubuntu 18.04 (Desktop-AMD) and git version 2.17.1. The tool requires data exchange over network and hence requires permissions for the same. I have achieved this by creating a new user accout named 'git' in every terminal. This new user account holds all the information about the 'Social Networks' and handles file sharing.

### Development
The theme to solve the problem is to create a user named "git" in every terminal and assign this user all the permissions required for the networked communication so that push, pull, log and show etc can work smoothly. 
``` 
	sudo adduser --disabled-password git
    	sudo su git
```
Above two commands from SN create do this task. 
The "sn" file is the primary pivot in handling and redirecting all the subcommands. This takes and arguement, as one of the listed options, and executes corresponding script to perform command specific operations.

### Tests 
After running "install.sh", all the script executables will be placed in the 
```/home/$uname/bin``` path. These files are give priviledge for being executable so now you can go to your terminal and type 
```sn --help``` and get all the possible options you can opt for.

#### Evaluation
Configure the script on each machine in a LAN environment with atleast three computers. SCRIPT WILL MAKE A NEW USER ACCOUNT FOR GIT BASED OPERATIONS.  

## How to contribute
There are two main ways of contributing to this Suite:

1. **Implementing new subcommands**: 

2. **Implementing new methods**: Ideally, new agent contributions shall perform better than the default ones.


### Help page 
This help document explains the intentions for the commands and their usage. Although due to some other commitments, this project could not be completed upto the mark, Yet I have tried to give an effort.
The details of the options in "sn [options]" as follows - 

create - Lets you create a new network by asking the name for it. Initializes a git repo in the folder of chosen name and creates a database file for the network. Basic idea is to edit this database file for the exchange of messages.

join - Clones a repo from a IP address and a path entered in the prompt.

pull - Pulls the new changes in the git repo from the master server by running git pull.

log - Shows the git log of the selected network.

show - Shows the git show output for the selected network 

push - Pushes the changes made by you in the database file to the master server.

follow - Stores the list of the people you are interested in for the priority.

members - lists all the members in the network.

unfollow - Removes the person from the list of follow.

list - Tells you how many networks you are part of.
	        
--help - Opens this help document.

--sn-path - Shows path to the stored files of the network

leave - Deletes the network directory 

archive - Stores the post separetly from the SHA1's 7 letters.
	      
Although I have tried to incorporate more features, the testing of many features in the real local network could not happen. There is a chance that few commands do not perform properly.

The networks created or joined are stored under the "SN" directory of the home folder of the user. I tried to create another password-disabled user namely "gituser" for this purpose but since most of the files and projects lie in the user's home, it was not a successful attempt. Also due to this pulling from the local network incorporated SSH logins.

All the commands are stored and run from "bin" directory in home folder.

Installsn file contains some changes in the settings which I had to make during this setup.



## References
1. [Ref](url)
