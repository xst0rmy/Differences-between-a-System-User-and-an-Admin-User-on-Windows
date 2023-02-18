# P-set: Differences-between-a-System-User-and-an-Admin-User-on-Windows

It may be a surprise to you to find out that there is a windows user with a higher priveledge than an Administrator user. Some people think the Admin account on windows is the most powerful user which isn't true because it is limited in functions it can perform and it is also limited in information it can access on the windows operating system. 

The user with a higher priveledge on windows OS is called The System User. The system user is not easily accessible for use like an admin user but below, i'll show you detailed process on how I accessed the system user with ease.

But, TAKE NOTE: Accessing the operating system comes with a higher level of risks as clicking a wrong button can permanently damage your operating system and you may have to uninstall the operating system. Therefore, make sure you carry out adequate research and be very knowledgeable of what you want to do on your system as a system user.

The system user was created as a means to protect the security of important operating system configurations and other basic functions that allow the smooth running of the operations system. Without this security in place, a normal user or an admin user could delete sensitive or important files by mistake which could lead to the malfuntioning of the operating system and may ultimately lead to having the operating system getting uninstalled.

To read more on the system user and its origin, click the link below

```
https://4sysops.com/archives/how-to-access-the-sam-and-security-hives-in-the-registry-using-the-system-account/

```

Below is the process I used in becoming a system admin and was able to access the contents of the SAM (Security Account Manager) hive in the registry editor which is found on various windows OS versions. It stores the users' passwords in a database file.  


First if all, lets try to access the contents of the SAM hive as an admin user. Below is an image showing i started the registry key app as an admin user

![](https://github.com/xst0rmy/Differences-between-a-System-User-and-an-Admin-User-on-Windows/blob/main/Images/sid%201.png)

The arrow in the image below shows the the various hives (Folders) and keys (sub-folders) I clicked on to get to the Sam Hive. You'll notice there is no information to access on the SAM hive result

![](https://github.com/xst0rmy/Differences-between-a-System-User-and-an-Admin-User-on-Windows/blob/main/Images/sid%202.png)

Next, search for Command Prompt app and run ad administrator

![](https://github.com/xst0rmy/Differences-between-a-System-User-and-an-Admin-User-on-Windows/blob/main/Images/sid%203.png)

Below I made a mistake by inputed the correct code to become a system user but was surprised it was rejected. I had to ask what user I was out of desperation by typing the command "whoami"

![](https://github.com/xst0rmy/Differences-between-a-System-User-and-an-Admin-User-on-Windows/blob/main/Images/sid%204.png)

After carrying out additional research on what was wrong, I got to find out I needed to install an app (PsTools) that'll enable me to use the "psexec" command in the command line interface.

Below is the link to download PsTools from Microsoft, it is 3.5mb at the time of this write-up.

```


https://learn.microsoft.com/en-us/sysinternals/downloads/psexec


```

After downloading the zip file, decompress it. you should have similar files as shown in the image below

![](https://github.com/xst0rmy/Differences-between-a-System-User-and-an-Admin-User-on-Windows/blob/main/Images/sid%205.png)

The image below shows the various command I used to before I could install the Sysinternals software which is the software thatll give me access to become a system user. PS. I hope you read the insightful writeups in the website you downloaded the PsTools from?  

![](https://github.com/xst0rmy/Differences-between-a-System-User-and-an-Admin-User-on-Windows/blob/main/Images/sid%206.png)

Did you notice how I had to navigate to the Download folder where the PsTools was located in using the cd command or Change Directory command.

Next, I used this command below to agree to the terms of EULA in order to use the software.

```


psexec.exe -sid


```

This brought up the page where you have to agree to the license terms before you can continue. Click the "Print" option at the lower left side of the form if you intend to have moire information on the agreement.

Click the "Agree" button to proceed.

Next, type the command below to open up a system user command prompt access

```

psexec -sid cmd.exe


```

![](https://github.com/xst0rmy/Differences-between-a-System-User-and-an-Admin-User-on-Windows/blob/main/Images/sid%207.png)

The image below shows another command prompt tab opened after running the command above. 

![](https://github.com/xst0rmy/Differences-between-a-System-User-and-an-Admin-User-on-Windows/blob/main/Images/sid%208.png)

I typed regedit.exe to open up the registry editor application.

![](https://github.com/xst0rmy/Differences-between-a-System-User-and-an-Admin-User-on-Windows/blob/main/Images/sid%209.png)

The above command opened up the Registry Editor app and the arrow indicator in the image below shows the path I used to access the SAM hive

![](https://github.com/xst0rmy/Differences-between-a-System-User-and-an-Admin-User-on-Windows/blob/main/Images/sid%2010.png)

Notice any difference in the SAM drive as compared to when I opened it as an admin user?

Yes, there are more information on here and that is because the admin user doesn't have the right to access these extra information or make changes to them.

Now lets open up the file in the SAM folder to access the database file that saves up the passwords on the operating system which is the file with the "C" which I highlighted.

![](https://github.com/xst0rmy/Differences-between-a-System-User-and-an-Admin-User-on-Windows/blob/main/Images/sid%2011.png)

Yes! it is a binary file, the creators also had to put a level of security and not display it in a compiled language so that if a malicious user were to access it, they woulkdnt be able to instantly view the saved passwords.

I hope you learnt something by reading the write-up above. There are other ways to access the system user, If you wish to read up on that, click the link below:

```

https://techdirectarchive.com/2022/07/25/how-to-run-a-program-in-windows-as-the-system-localsystem-account/


```






