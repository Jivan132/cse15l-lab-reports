# Tutorial
### In this tutorial, you will learn how to log in into a course-specific account on “ieng6”.
## Step 1: Installing VScode
The first step will be to install VScode. You can do this by going to “https://code.visualstudio.com/” and there you can download the latest version. Once it is installed, you will see something similar to this when you open it.
![step 1](https://github.com/Jivan132/cse15l-lab-reports/blob/main/photos/Step%201.jpg?raw=true)

## Step 2: Remotely Connecting
The next step will be to connect remotely to the “ieng6” server. You can do this by first opening the terminal here.
![step 2](https://github.com/Jivan132/cse15l-lab-reports/blob/main/photos/Step%202.jpg?raw=true)
Then, click on new terminal and it will pop-up at the bottom. In there you will type “ssh [course specific account]” (you can find your account name and reset your password [here](https://sdacs.ucsd.edu/~icc/index.php)). After this, you will be prompted to type your password, be careful typing it because you will not be able to see what you are typing or how many characters you are typing. Once you enter your password, you will probably be presented with this massage:
> The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])?

 Type “yes” since we will be connecting to this server often. You will know that you have followed everything correctly if you see something similar to this:
 
 ![step 2.2](https://github.com/Jivan132/cse15l-lab-reports/blob/main/photos/Step%202.2.jpg?raw=true)

## Step 3: Trying Some Commands
Once you are connected to the “ieng6” server you can try some commands on the server and then try them again on your computer to see the differences. Some commands you can try are:
 - cd
- cd~
- ls -lat
- la -a
- ls
- exit (which exits the server session)
- Among others

You can see that in the example below “ls” is run first in the server and then in the client side. The output of both images corresponds to the names of the files of each directory (one for the server and the other for the client).
![step 3.1](https://github.com/Jivan132/cse15l-lab-reports/blob/main/photos/Step%203.jpg?raw=true)
_Server Output_


![step 3.2](https://github.com/Jivan132/cse15l-lab-reports/blob/main/photos/Step%203.2.jpg?raw=true)
_CLient Output_

## Step 4: Moving Files with scp
Now we will see how we can move files from our computer to the server “ieng6”. We can accomplish this with the command “scp”. Either create a new file or open it using VScode. After saving it, open the terminal and type the following command “scp &lt;name of the file including the extension> &lt;course specific account>:~/”. For example, in my case it would be “scp WhereAmI.java cs15lwi22alh@ieng6.ucsd.edu:~/”. After doing this, you will be prompted for your password and you will see something similar to this:
![step 4](https://github.com/Jivan132/cse15l-lab-reports/blob/main/photos/Step%204.jpg?raw=true)

## Step 5: Setting an SSH Key
You might to start to notice that each time that we want to connect to the server we are prompted to enter our password. We can get around this issue by creating a “SSH Key” so our computer gets “remembered” by the server. In order to create it we need to type the following in our terminal while being in the client side:
```
ssh-keygen
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/Ivan/.ssh/id_rsa): /Users/Ivan/.ssh/id_rsa
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /Users/joe/.ssh/id_rsa.
Your public key has been saved in /Users/joe/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:jZaZH6fI8E2I1D35hnvGeBePQ4ELOf2Ge+G0XknoXp0 joe@Joes-Mac-mini.local
The key's randomart image is:
+---[RSA 3072]----+
|                 |
|       . . + .   |
|      . . B o .  |
|     . . B * +.. |
|      o S = *.B. |
|       = = O.*.*+|
|        + * *.BE+|
|           +.+.o |
|             ..  |
+----[SHA256]-----+
```
If you are a Windows user you will need to also follow this extra step of “ssh -add” to get it to run (tip: open PowerShell with admin privileges).

Once you have completed these steps, you need to connect to the server via “ssh” to set up the “SSH Key” on the server side. There, you will need to type the following on the terminal (replace the account with your own):
```
mkdir .ssh
exit
scp /Users/Ivan/.ssh/id_rsa.pub cs15lwialh@ieng6.ucsd.edu:~/.ssh/authorized_keys
```

Finally, try to enter again to the server using "ssh". If everything went correctly it should not ask you for your password.
![step 5](https://github.com/Jivan132/cse15l-lab-reports/blob/main/photos/Step%205.jpg?raw=true)

## Step 6: Optimizing Remote Running
You can optimize some of the remote running by adding more commands in your line. For example, if you would like to run more than one command, you can do this by adding a semicolon after each command. Like this:
```
cp WhereAmI.java OtherMain.java; javac OtherMain.java; java WhereAmI
```
You can also run commands in the server and then automatically exit by adding the command in quotes after the “ssh &lt;course specific account>”. This is an example of how it would look:

![step 5](https://github.com/Jivan132/cse15l-lab-reports/blob/main/photos/Step%206.jpg?raw=true)

*Pro tip: you can go to previous commands by using the arrow keys*

