# REMOTE ACCESS TUTORIAL

*Hi, I'm Jenny Quach. My PID is A16796954. This is my week 2 lab report 1*

This will be the tutorial of how to get access to the server remotely at your local computer. 
This will include many steps such as installing vscode, remote connecting, trying out some commands on the terminal, make changes to the file on your local and copy it to the server, setting ssh key and optimize remote running 

## Step 1: Install Vscode

First, you can go to the [this website](https://code.visualstudio.com) to install vscode. Click on download to download Visual Studio Code. Remember to choose the correct operating system for your computer!

After you have vscoe downloaded, open it and this should be the screen that show up. ![Iamge](/images/step1-1.png)

This mean that you have successfully have vscode downloaded. Now you can start by click on `New File` and choose the option that said `Java class`

 A window will pop up, you can go ahead and write a simple java program there. Anything of your choice. Then save it with `Ctrl/Command S` in your desired local path. Remember to name your file with the `.java` end

You also have the option to run the your new code by typing this command into the terminal:

- `javac YourFileName.java`
- `java YourFileName>`

## Step 2: Remote Connecting 

Now that you have vscode work out. We will now figure out how to connect our local computer to the server computer

You will have to go [this web page](https://sdacs.ucsd.edu/~icc/index.php) to change the password for your ucsd account 

In the website, you will see a window which ask for your username and PID, go ahead and type in your ucsd account username and PID

Then you will see a window with all the information about your account. Click on the box which have this format `cs15lsp22<three_letter_of_your_account>` This will lead you to your remote account.

Now then you will see the sentence "You can change your password for this account" which the phrase `change your password` lead to this link [here](https://sdacs.ucsd.edu/~icc/password.php) (You can access the link through the phrase or through the link provide in this document)

Go there and you will be able to see that they again ask for your username and PID. Repeat the step as above and enter both your ucsd username and PID.

Now you will get to the change password page. Which should look like this ![Image](/images/step2-1.png)

Enter you current password (for your ucsd account) and change it with a new password. Put in mind that this will globally change your ucsd account password so make sure you choose a wise new password and remember (or store) your new password somewhere 

Now it get to the important part. **DO NOT PRESS CHANGE PASSWORD**

Next to the "Change MyTritonLink password", change the option in the box from `Yes` to `No`, then press `Enter/Return` on your computer. If the Enter or Return button doesn't make any change to the site, try to change your browser to Chrome!

- *Note that even though this option is choosen, your password for your mytritonlink account still changed so this will make your ucsd account a bit shacky.*

After that, you should see a page that told that your password have been change and you will have to wait for around 15 mins. 

Waited for 15 mins and go back to vscode terminal. Now you are fully ready to connecting to the remote server from your local terminal!

On your local terminal (or vscode terminal) type this command: (where `zzz` is your specific username)

`ssh cs15lsp22zzz@ieng6.ucsd.edu`

You will probably encounter this message if this is your first time log into the server:
```
The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])?
```

Go ahead to type `Yes` and then press `Enter/Return`
Now it will ask for your password, type the password that you just change above. 

- *If It didn't work out, maybe try to log out using the command `exit` then try log in again with the command `ssh cs15lsp22zzz@ieng6.ucsd.edu` and this time, it should ask for your password immediately. Type your password in again.* 
- *If it still didn't work. Check and make sure you have the correct username, dont try to copy the command from this document but type it out yourself as something the different font may be the cause of the error.*
- *You can also try to repeat the step above and go change the password again if everything is still not work out after all the tries above.* 

After entering the password, this should be the window that show up, and you are finally in the server!
![Image](/images/step2-2.png)

Notice that you are in the server terminal right now, next to the `trash bin icon` you will see a `split screen icon`. Clicking that will create a split terminal of your local computer that you can work on along with the server one.

## Step 3: Trying out some commands on the terminal

Now that you are in the server, there are some command that you can try out to explore the system. 

You can try out a bunch of unix basic command in [this link here](https://www.unixtutorial.org/basic-unix-commands)

I recommend you try out command such as and see what will happen:
- `ls` 
- `ls -lat` 
- `cd`
- `cd ~`
- `cd ..`
- `pwd`

Try those command on both your local and server terminal so that you can notice the difference between the two. 

Below will be the example of some of those commands in the terminal:
![Image](/images/step3-1.png)

Notice that when I try to acces the server account of the other username, it said permission denied. This is because I dont have access to those account. 

## Step 4: Make Changes to the file on your local and copy it to the server

Now that you have an idea of how to monitor the terminal. Now we will get to the step in which we get your local files into the server.

We will bring the file that you created and svaed earlier on vscode into the server. 
We will do this by using the command `scp`, which will copy the file from your local into the server. 

Back to your local terminal, go to the directory that you store the file. Remember that you can use the `cd /directory_name/directory_name` command to go straight to the directory that you want to 

When you are already in the correct directory, type this command into the terminal: (where `zzz` is your specific username)

`scp YourFileName.java cs15lsp22zzz@ieng6.ucsd.edu:~/`

It will ask for your password after you press `Enter/Return`. Go ahead and enter your password for the account.

Give it a few seconds to load, then go check in your server termial, you will now see that the file in your local have been copied to the sever!

This is my example, where I have a WhereAmi.java file that will print out my current system location:
![iamge](/images/step4-1.png)

## Step 5: Setting ssh key 

You will notice that it is quite annoying and time cosuming that we have to type the password every single time we copy or log into the account. 

The idea is that you can call the `ssh-keygen` command which will generate 1 pair of private and public key. You can copy that pair of key in your local computer and then every single time you call the ssh, it will use those files instead of asking for password every single time.

On your local termial, enter this command: `ssh-keygen`

This messgae will show up:
```
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/<user-name>/.ssh/id_rsa):
```

Now then type: `/Users/<user-name>/.ssh/id_rsa` (Remember to replace with your computer local username here)

You will see this message next:
```
Enter passphrase (empty for no passphrase):
```
**Do not type anything in here, just press Enter/Return twice**

After that, this should show up:
```
Your identification has been saved in /Users/<user-name>/.ssh/id_rsa.
Your public key has been saved in /Users/<user-name>/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:jZaZH6fI8E2I1D35hnvGeBePQ4ELOf2Ge+G0XknoXp0 <user-name>@<system>.local
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

Now then go back to your server terminal. Log in using the `ssh cs15lsp22zzz@ieng6.ucsd.edu` command again if you already log out

Type this: `mkdir .ssh` to make a .ssh directory

Now go back to your local and type this:
`scp /Users/<user-name>/.ssh/id_rsa.pub cs15lsp22zz@ieng6.ucsd.edu:~/.ssh/authorized_keys`
(Remeber to replace the username with the correct one)

And now you are good to go! Go ahead and log out of the server account on the terminal (if you have not yet to) and try to log in again! You will now see that it no longer ask for your password.

As you can see in this example here, I was able to login with out password:
![image](/images/step5-1.png)

## Step 6: Optimize remote running

You are almost there!

We have done a lot today, now is the time to learn how to make it more efficient and save your precious time!

There is some command that you can use such as:
- `ssh cs15lsp22zzz@ieng6.ucsd.eud "ls"` this will login your server account and run the command inside `" "`. You can also replace `ls` with command such as `cd`
- `javac OtherMain.java; java WhereAmI` using the `;` will help you run many command line at once
- You can also use the `up arrow` to go back to the previous command, instead of retyping the command 

---
# Thank you!