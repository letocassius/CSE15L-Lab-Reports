# CSE 15L Week 2 Lab Report

this is a tutorial for incoming 15L students about how to log into a course-specific account on ieng6. 

## Part 1 -  - Installing VScode

Go to the Visual Studio Code website https://code.visualstudio.com/, and follow the instructions to download and install it on your computer. Choose your version base on your device type.

When it is installed, you should be able to open a window. It should look similar to this:
<img width="1351" alt="Screen Shot 2022-04-10 at 3 44 00 PM" src="https://user-images.githubusercontent.com/64039891/162643108-88e13fdc-6f90-41db-9563-8582b4ab866b.png">
The color and the menu bar might be different based on your setting. 

## Part 2 - Remotely Connecting
You will be remote connecting to a UCSD computer from your device using VScode. 

if you’re on Windows you will need to install a program called OpenSSH Using the procedure on this link:https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse.

When you finish Look up your course-specific account for CSE15L [here](https://sdacs.ucsd.edu/~icc/index.php.).

Then, in VSCode, open a new terminal and type in your command to connect to the remote computer. which will look like this, except the letters "aoo" will be repalced with your own course-specific account.  

<img width="607" alt="Screen Shot 2022-04-10 at 3 56 42 PM" src="https://user-images.githubusercontent.com/64039891/162643468-d97c5e8a-6057-4042-a970-5bf86b4ebfff.png">

After that, type in your password and your can access a computer on UCSD campus remotely. You are accessing the server as a client. 
<img width="848" alt="Screen Shot 2022-04-10 at 4 01 02 PM" src="https://user-images.githubusercontent.com/64039891/162643633-32171bd2-5142-4123-94ae-3f78752edc36.png">

## Part 3 - Trying Some Commands
Now you can try to run some commands on the server using your device! Here are some interesting commands to get you started:
- `cd ~`
- `cd`
- `ls -lat`
- `ls -a`
- `ls <directory>` where `<directory>` is `/home/linux/ieng6/cs15lwi22/cs15lwi22apl`
(where again `wi22` is replaced by the time you're taking this class, and `apl` is replaced by
the letters in your course-specific account.)
- `cp /home/linux/ieng6/cs15lwi22/public/hello.txt ~/`
- `cat /home/linux/ieng6/cs15lwi22/public/hello.txt`

For example, your will be able to to see all your files withn your do `ls -a`. You will see something like this:
<img width="972" alt="Screen Shot 2022-04-10 at 4 07 40 PM" src="https://user-images.githubusercontent.com/64039891/162643872-050d0b70-470a-4717-8464-465d3d333db7.png">


## Part 4 - Moving Files with scp

## Setting an SSH Key

## Optimizing Remote Running


