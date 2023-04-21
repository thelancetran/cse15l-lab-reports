# **Lab Report 1**
This is a step-by-step guide on how to access your course-specific account on ieng6 using the terminal in VS Code

## **STEP 1: Installing VS Code**
*If you have done so already, you can skip this step*
1. Go to the [Visual Studio Code Website](https://code.visualstudio.com/)
![Image](downloadVSCode.png)
2. Click on the download link shown above in red
3. Install the file matching on your operating system (Windows, Linux, Mac)
4. After installing, open VS Code and it should look something like this:
![Image](VSCodeHome.png)
---

### **(WINDOWS ONLY!!!) STEP 1.5: Git Bash and VS Code**
*If you have already set the default terminal in VS Code to use Git Bash, then you can skip this step*
1. Go to the [Git for Windows Website](https://gitforwindows.org/)  
![Image](GitDownload.png)
2. Click on the download link shown above in red
3. Follow this [Stack Overflow post](https://stackoverflow.com/questions/42606837/how-do-i-use-bash-on-windows-from-the-visual-studio-code-integrated-terminal/50527994#50527994) that will explain how to set your default terminal in VS Code to use Git Bash
---

## **STEP 2: Remotely Connecting**
1. In VS Code, open the terminal by going to `terminal` -> `new terminal` or with the shortcut `Ctrl` + ``` ` ```. You should see something like this:  
![Image](TerminalVSCode.png)
2. Type `ssh <course-specific account>@ieng6.ucsd.edu` where `<course-specific account>` is your course-specific account and press `Enter`
3. Enter your password and you should get something like this:
* **NOTE:** When typing in your password, you will NOT be able to see any characters being typed, but keep in mind that this is normal and whatever you type is being inputted!
![Image](LogIn.png)
---

## **STEP 3: Trying Some Commands**
Now that we have access to our account on ieng6, we should try running some commands!  
Here is a list of commands and their function:  
```
pwd: "Print Working Directory" - shows the current directory that you are in
ls: "List" - lists the files in the current directory you are in
cd: "Change Directory" - you can change your directory by entering 
cp: "Copy" - you can copy file(s) from the directory you are in, into another directory
mkdir: "Make Directory" - you can create your own directories in the directory you are in
cat: "Concatenate" - prints out the "String" contents (basically outputs words, like code in a .java file)
```
Here are some examples of these commands in use:  
`ls -lat`  - by including `-lat`, we can display full contents (`l`), which include hidden files and directories (`a`), in our current directory in a long listing format, which begins with the most recently edited file (`t`). Hence, `-lat`!
![Image](ls-lat.png)

`cd ~, cd .., cd, cat, cp`  - by including `~`, we can access the home directory (So `cd ~` will change directories to the home directory). And `..` refers to the previous directory (So `cd ..` will change directories to the previous directory!)
![Image](someCommands.png)

* **NOTE:** When finished, you can log out of the remote server by typing and entering `Exit`
