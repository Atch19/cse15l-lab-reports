# **First Report Week 2**
## 1. Installing VScode
* To install VScode go to [Visual Studio Code Webpage](https://code.visualstudio.com/).
* Follow the instructions when prompted.

This is what it should show when you complete the set up

[2]: vscode.PNG  
![vscode launch][2]


***
## 2. Remotely Connecting
* Go to [Username tool](https://sdacs.ucsd.edu/~icc/index.php) to find your username for this CSE 15L class, then reset your password for that account. 
* Launch VScode, open the terminal from Terminal > New Terminal.
* Type `ssh (Username)@ieng6.ucsd.edu`, replace (Username) with your username. 
* If this is your first time, click yes when prompted. After which type in your password. 


You should see a simular output. <br>



```
Last login: Fri Apr  1 12:33:23 2022 from 100.82.177.183
quota: No filesystem specified.
Hello cs15lsp22alk, you are currently logged into ieng6-203.ucsd.edu

You are using 0% CPU on this system

Cluster Status 
Hostname     Time    #Users  Load  Averages  
ieng6-201   18:10:01   7   0.22,  0.25,  0.22
ieng6-202   18:10:01   12  4.08,  4.15,  4.21
ieng6-203   18:10:01   12  1.09,  1.14,  1.16

 
Fri Apr 01, 2022  6:13pm - Prepping cs15lsp22
[cs15lsp22alk@ieng6-203]:~:74$ 
```

## 3. Trying some commands
* You should try to run a few commands. You can find most on the web but, here are a few examples: cd {dir}, ls, pwd, mkdir {name}, and cp.
* You can try to log out and run a few of those commands again, on your local pc, just to get to know your environment.   

Here is a sample of the mkdir and ls command. 

[1]: example.PNG  
![Example code][1]

## 4. Moving Files with `scp`
* Scp is used to safely transfer files between different computers. 
* To start off lets create a java file with some code.

For Example we can have:

```
class WhereAmI{
    public static void main(String[] args) {
    System.out.println("I am using a " + System.getProperty("os.name") + " Operating system. ");
    }
}
```
* Save the file, then run `scp WhereAmI.java (Username)@ieng6.ucsd.edu:~/`
* This command will transfer your file to the remote ieng6 computer after you type in the password when promoted. 

This should be what you see:


[3]: scp1.PNG  
![SCP1][3]

* After you log in, try running `ls` to see if your file was actually transfered.

You should get a simular output:

[4]: scp2.PNG  
![SCP1][4]



## 5. Setting a SSH Key
* SSH keys are useful to assist with logging in and out of servers without using your password which can be tiresome. 
* This process will create a pair of private and public keys which will help you log in faster. 
* Type in `ssh-keygen`.
* When prompted to enter a file in which to save your key type

`/Users/(local username)/.ssh/id_rsa`

* Leave the passphrase blank once prompted.

* You will now pass the key on to the server. ssh to the server once again. 
* Once on the server you will type `mkdir .ssh`
* Log out 
* Type in `scp /Users/(local username)/.ssh/id_rsa.pub (username)@ieng6.ucsd.edu:~/.ssh/authorized_keys`


If everything went smoothly, this is what you should see. 

[5]: nopassword.PNG  
![SCP1][5]


Notice how I am not prompted to enter my password. 
## 6. Optimizing Remote Running
* You can now run commands from  your local computer to the remote computer. Try `ssh (username)@ieng6.ucsd.edu "ls"`
* It will quickly log into the server and run the command and then log out, printing the output in the terminal. 
* To run several commands at once, add a `;` between commands. 

This is an example of running several commands, it `scp` the command into the remote server, complies it using javac, then runs it using java. 


[6]: part7.PNG  
![SCP1][6]