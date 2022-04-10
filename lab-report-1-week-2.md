![Image](https://github.com/mstubbs1/cse15l-lab-reports/blob/main/Screenshot%202022-04-08%20at%2015.02.44.png)

# Hello Future CSE15L Students 
Today I will be guiding you on how to use your course specific account on the `ieng6` server.

**Disclaimer** : This guide will be centered around **MacOS**, so this tutorial is assuming that you will be using **MacOS** as there is a pretty large difference on how to do this if you're using a windows pc or a mac.

## Firstly... 
You need to have Visual Studio Code installed. To do this, go to the [Visual Studio Code Website](https://code.visualstudio.com/download) and downlad the version for your corresponding operating system. *Again, this guide will be focusing on doing all of this on MacOS*. 

![Image](https://github.com/mstubbs1/cse15l-lab-reports/blob/main/vstudio.png)

Once you have successfully installed visual studio code onto your Mac, you can create a new instance of the terminal by clicking `Terminal `> ` New Terminal` at the top of your display.

![Image](https://github.com/mstubbs1/cse15l-lab-reports/blob/main/terminal.png)

## Now That You Have a Terminal

You can connect to your `ieng6` account. Do this by typing in the terminal `ssh cs15lsp22zz@ieng6.ucsd.edu` With the "zz" replaced by your 2-3 unique  characters that can be found in your course directory. The link for that can be found [here](https://sdacs.ucsd.edu/~icc/index.php). Once you type the command into the terminal, make sure to type "yes" when it asks you permission to continue connecting to the host. This allows you to fully connect to the computer in the cse basement.

![Image](https://github.com/mstubbs1/cse15l-lab-reports/blob/main/sign.jpg)

*While this screenshot was taken in windows powershell, it's the exact same on a mac terminal.*

## Testing Some Commands 

An important command to note is `ls`. This command stands for "list files" and list all the files in the directory you are currently in.

![Image](https://github.com/mstubbs1/cse15l-lab-reports/blob/main/ls.png)

A variation of this command can be used, this is `ls -a`. This command lists all the files in the directory along with its **hidden files**.

![Image](https://github.com/mstubbs1/cse15l-lab-reports/blob/main/ls-a.png)

## Moving Files With `scp` 

Moving files between your local computer to the computer in the cse basement can be done with the command `scp`. It stands for "secure copy". For this demonstration I will be moving a file called "test.txt" that is located in my downloads directory. Firstly, you want to start off in a terminal that is not signed into the ieng6 server. Once you are in a terminal of your local account, go to the directory that your file is in using the `cd` command, then you can type in the command `scp test.txt cs15lsp22zz@ieng6.ucsd.edu:~/`

It's important to note that text.txt can be replace with the file you are going to move and the "zz" should be replaced with your unique 2-3 charecters of your cs15l account. 

