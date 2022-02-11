# Lab Report 3
### For this lab report, I am going to show the steps I took to complete the choice 1 “Streamlining ``` ssh ``` Configuration”. This is done with the intention of connecting to the ``` ieng6 ``` in a faster manner.
<br/><br/>
## Create and edit ``` .ssh/config``` file:
![step 1](https://github.com/Jivan132/cse15l-lab-reports/blob/main/Lab-Report-3/Photos/Step%201.jpg?raw=true)
> VScode window showing the edited file that was created to save the configurations of ```ssh```.

In this file, we have created a series of command in order to access the ```ieng6``` server faster. The first line indicates the alias that we want to use in order to run the following commands. The next line establishes the server to which we should connect. The next line is the username that you are using to connect to the server. Finally, the last line is just to refer to your ```id_rsa``` file

<br/><br/>

## Connect to the server with the alias created:
![step 2](https://github.com/Jivan132/cse15l-lab-reports/blob/main/Lab-Report-3/Photos/Step%202.jpg?raw=true)
> Windows PowerShell window showing that I was able to connect to the server by just typing ```ssh server```

As we can see in the picture, we are using the command ```ssh server``` to connect to the ```ieng6``` server instead of writing my whole username ```cs15lwi22alh@ieng6.ucsd.edu```. This works because in the previous step I was able to configure a “shortcut” by providing an alias, which in this case is the word ```server```.

<br/><br/>

## Copying a file to the server using the alias:
![step 3](https://github.com/Jivan132/cse15l-lab-reports/blob/main/Lab-Report-3/Photos/Step%203.jpg?raw=true)
> 