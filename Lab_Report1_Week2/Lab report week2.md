
# CSE 15L Week 2 Lab Report

this is a tutorial for incoming 15L students about how to log into a course-specific account on ieng6. 

## Part 1 -  - Installing VScode

Go to the [Visual Studio Code website](https://code.visualstudio.com) and follow the instructions to download and install it on your computer. Choose your version base on your device type.

When it is installed, you should be able to open a window. It should look similar to this:
<img width="1351" alt="Screen Shot 2022-04-10 at 3 44 00 PM" src="https://user-images.githubusercontent.com/64039891/162643108-88e13fdc-6f90-41db-9563-8582b4ab866b.png">
The color and the menu bar might be different based on your setting. 

## Part 2 - Remotely Connecting
You will be remote connecting to a UCSD computer from your device using VScode. 

if you’re on Windows you will need to install a program called OpenSSH Using the procedure on this [link](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse).

When you finish Look up your course-specific account for CSE15L [here](https://sdacs.ucsd.edu/~icc/index.php).

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
Now we are able to do some work on local and remote computers. A key step in working remotely is the ability to copy files between the your comuter (client) and the UCSD computer (server). To do this, we could use the `scp` command. We will be ablt to run this command from the *client*, without logging into `ieng6`.

1. First make a file called `WhereAmI.java`, and compile using `javac` run it with`java`.
<img width="815" alt="Screen Shot 2022-04-10 at 5 19 23 PM" src="https://user-images.githubusercontent.com/64039891/162646351-6117e5a1-b631-4705-80d4-f8a8ccd0bc26.png">
2. Then, in the terminal from where you made this file, run the following command using your username:
`scp WhereAmI.java cs15lsp22aoo@ieng6.ucsd.edu:~/`
It should look like this:
<img width="1129" alt="Screen Shot 2022-04-10 at 5 21 54 PM" src="https://user-images.githubusercontent.com/64039891/162646490-73c2ef23-608f-464c-bb16-6a0e804f36fd.png">
3. Log into the server again through `ssh`, and do the `ls` command in the terminal. Now you could see that the file is that you just created in been copies to the server.
 <img width="800" alt="Screen Shot 2022-04-10 at 5 25 14 PM" src="https://user-images.githubusercontent.com/64039891/162646642-8a25404a-8a93-4fc2-8704-08c1026a47a2.png">
4.Now run it again using `javac` and `java` on the ieng6 computer using   and java.
<img width="500" alt="Screen Shot 2022-04-10 at 5 26 32 PM" src="https://user-images.githubusercontent.com/64039891/162646697-4c16b003-a3a3-43e2-993d-9d8488dd544f.png">

## Part 5 - Setting an SSH Key
Notice how when you log into the server, it is always required type in your password. This process can be anoying. To avoid this, there is a great solution – `ssh` keys. We are going to use a program called `ssh-keygen`.

We could set it up like this. 
<img width="631" alt="Screen Shot 2022-04-10 at 5 33 28 PM" src="https://user-images.githubusercontent.com/64039891/162647187-08def8eb-e1e1-43f5-92d0-6e392d56db50.png">

This created two new files on your system; the private key `id_rsa` and the public key `id_rsa.pub`, stored in the .ssh directory on your computer.

Now you're going to copy the **public** key to the `.ssh` directory from your computer to the server.

1. `ssh cs15lsp22aoo@ieng6.ucsd.edu`

enter the password and log on to server.

2. `mkdir .ssh`
<img width="376" alt="Screen Shot 2022-04-10 at 5 44 00 PM" src="https://user-images.githubusercontent.com/64039891/162647742-5a419132-ec76-44f3-92ee-c6d0b7552233.png">


3. Log off of the server using `exit`
Now back on the client!

4. you now can use`$ scp <path for id_rsa.pub> cs15lsp22aoo@ieng6.ucsd.edu:~/.ssh/authorized_keys`
# You use your username and the path you saw in the command above'


## Part 5 - Optimizing Remote Running
sometimes we want to make a local edit to a fileWe can use the following command to save time: We can use the following command to save time:

<img width="818" alt="Screen Shot 2022-04-10 at 6 54 40 PM" src="https://user-images.githubusercontent.com/64039891/162652276-be29945f-2a66-40b2-9f2e-927a28e6ea15.png">
