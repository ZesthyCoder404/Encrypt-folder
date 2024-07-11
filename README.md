## Encrypt folder

This is a .bat file that can make you encrypt any folder you want without using complicated commands in the cmd. Very usefull if you want to make a private folder.


## How it works?

So basically this .bat lock your folder and you can only access the folder by clicking on the file and writing your custom password. But you need to follow some steps to make it work. Everything is explained here below.
## Choosing a password

Fisrt of all let's take a look of the .bat file (to modify the .bat file open it with Notepad)

```bash
@ECHO OFF
if EXIST "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}" goto UNLOCK
if NOT EXIST Private goto MDPrivate
:CONFIRM
echo Are you sure to lock this folder? (Y/N)
set/p "cho=>"
if %cho%==Y goto LOCK
if %cho%==y goto LOCK
if %cho%==n goto END
if %cho%==N goto END
echo Invalid choice.
goto CONFIRM
:LOCK
ren Private "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}"
attrib +h +s "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}"
echo Folder locked
goto End
:UNLOCK
echo Enter password to Unlock Your Secure Folder
set/p "pass=>"
if NOT %pass%== YOUR PASSWORD goto FAIL
attrib -h -s "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}"
ren "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}" Private
echo Folder Unlocked successfully
goto End
:FAIL
echo Invalid password
goto end
:MDPrivate
md Private
echo Private created successfully
goto End
:End
```
Now, what we are looking for is THIS :
```bash
if NOT %pass%== YOUR PASSWORD goto FAIL
```
You can see the : YOUR PASSWORD, well this is where you need to write the password that you want. *NOTE : Do not delete any other part of the code, only the YOUR PASSWORD (and make sure there is a space between ```
%pass%==``` and your password.*
## Saving

Now that you chose your password, it's very important to save the file as a .bat and not as text file. So click on the ```Save as``` of Notepad, choose a name (whatever you want is ok). But save it as a  ```.bat ```, if you did it correctly you will see a different icon compared to the text file format.
## Encrypt your folder
So now to encrypt your folder, you just need to save your .bat file there and open it. If everything is ok, a new folder called ``` Private``` has appeared . There is where you will put the files you want to hide in the secret folder. Click again on the .bat file and you  should get this messages on your cmd : ```Are you sure to lock this folder? (Y/N) ```. If you want to lock your folder type : ``` Y``` or ```y```, if you don't type ``` N``` or ```n```. If you locked you folder, the folder ``` Private``` normally has disappeared. 

*NOTE: You might get this weird folder called : ```Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}```. It's normal, just exit your file explorer, open it again and the folder will disappear.*

After locking your folder, to access to your files again, click on the ```.bat``` file. You will get this message from the command prompt ```Enter password to Unlock Your Secure Folder ```. Just enter the password you wrote in the bat file and the ```Private``` folder should appear. So this is how you lock and unlock your private folder.
## More information
Even if the .bat file lock your folder, it's not 100% safe and  i do not recomend to use it for important files (like bank info or stuff like that). 

If you want to change your password just open the file with Notepad and change your password, also make sure to save it (as .bat of course).

Finally, im not the creator of the code, but i haven't found who wrote it. I just wanted to share it on GitHub. I hope it worked for you!


## Issues

If you have any issues, please let me know and contact me on Discord (my username is in my GitHub Readme file)


## Author

- [ZesthyCoder404](https://github.com/ZesthyCoder404)

