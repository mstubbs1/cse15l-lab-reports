<!--
![Image](https://github.com/mstubbs1/cse15l-lab-reports/blob/main/Screenshot%202022-04-08%20at%2015.02.44.png) 
-->
# Hello Future CSE15L Students 
Today I will be guiding you on how to use your course specific account on the `ieng6` server.

**Disclaimer** : This guide will be centered around **MacOS**, so this tutorial is assuming that you will be using **MacOS** as there are a few key differences on how to do this if you're using a windows pc.

## Firstly... 
You need to have Visual Studio Code installed. To do this, go to the [Visual Studio Code Website](https://code.visualstudio.com/download) and downlad the version for your corresponding operating system. *Again, this guide will be focusing on doing all of this on MacOS*. 

![Image](https://github.com/mstubbs1/cse15l-lab-reports/blob/main/vstudio.png?raw=true)

Once you have successfully installed visual studio code onto your Mac, you can create a new instance of the terminal by clicking `Terminal `> ` New Terminal` at the top of your display.

![Image](https://github.com/mstubbs1/cse15l-lab-reports/blob/main/terminal.png?raw=true)

## Now That You Have a Terminal

You can connect to your `ieng6` account. Do this by typing in the terminal `ssh cs15lsp22zz@ieng6.ucsd.edu` With the "zz" replaced by your 2-3 unique  characters that can be found in your course directory. The link for that can be found [here](https://sdacs.ucsd.edu/~icc/index.php). Once you type the command into the terminal, make sure to type "yes" when it asks you permission to continue connecting to the host. This allows you to fully connect to the computer in the cse basement.

![Image](https://github.com/mstubbs1/cse15l-lab-reports/blob/main/sign.jpg?raw=true)

*While this screenshot was taken in windows powershell, it's the exact same on a mac terminal.*

## Testing Some Commands 

An important command to note is `ls`. This command stands for "list files" and list all the files in the directory you are currently in.

![Image](https://github.com/mstubbs1/cse15l-lab-reports/blob/main/ls.png?raw=true)

A variation of this command can be used, this is `ls -a`. This command lists all the files in the directory along with its **hidden files**.

![Image](https://github.com/mstubbs1/cse15l-lab-reports/blob/main/ls-a.png?raw=true)

## Moving Files With `scp` 

Moving files between your local computer to the computer in the cse basement can be done with the command `scp`. It stands for "secure copy". For this demonstration I will be moving a file called "test.txt" that is located in my downloads directory. Firstly, you want to start off in a terminal that is not signed into the ieng6 server. Once you are in a terminal of your local account, go to the directory that your file is in using the `cd` command, then you can type in the command `scp test.txt cs15lsp22zz@ieng6.ucsd.edu:~/`

It's important to note that text.txt can be replace with the file you are going to move and the "zz" should be replaced with your unique 2-3 charecters of your cs15l account. 

![Image](https://github.com/mstubbs1/cse15l-lab-reports/blob/main/scp.png?raw=true)

**Note** : You will be asked to type in your password here

## Setting an ssh Key 

Setting an ssh key is importnat to make things easier by not having to type in your passoword every single time you want to log in to your account, or move files between computers. This is possible by using an "ssh key". To do this, we use a program within the terminal called "ssh-keygen".

The first step should be to open a terminal (without connecting to ieng6 server) and type in the command `ssh-keygen`

The terminal will then tell you to "enter a file in which to save the key". For this just type the directory it gives you and replace the backslashes with forward slashes if there are any. 

![Image](https://github.com/mstubbs1/cse15l-lab-reports/blob/main/keygen.png?raw=true)

(for this demonstration I changed the file name to "id_rsa2" to not break any keygens already within my computer.)

Once you type in the directory, it asks you to create a passphrase, but just leave this blank and hit enter twice. The key-gen should generate some randomart which looks like this: 

![Image](https://github.com/mstubbs1/cse15l-lab-reports/blob/main/keygen2.png?raw=true)

Then copy the public key to your ieng6 account in the server. `ssh` into you account like earlier in this tutorial, once in type the command `mkdir .ssh`

 This comand creates a directory called ".ssh" in your account. Once this has been run you can `exit` out and back on your cliet you can use `scp` to move the public key into your new .ssh directory in your ieng6 account. The command to move the public key is:  
 
 `scp /Users/username/.ssh/id_rsa2.pub cs15lsp22zz@ieng6.ucsd.edu:~/.ssh/authorized_keys`

 **Note** : The path, public key file name and the "zz"within the cs15l account should all be changed to accomadate your unique file and user names. 

## Optimizing Remote Running

Putting a command in quotes after the `ssh` command allows you to run a command within the remote server and exit after running it. An example of this being used is: 

![Image](https://github.com/mstubbs1/cse15l-lab-reports/blob/main/sshquote.jpg?raw=true)

Another important thing to note is you can run several commands withing the same line by seperating them with semicolons. An example of this looks like: 

`ls ; ls -a `











