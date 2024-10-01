# How to set up MySQL Community Server and MySQL Workbench
This guide was originally meant to be used for DATA 220P at UC Irvine in Fall 2024. Note that the author has only attempted installation for Windows 11, so any debugging on Mac OS or Linux will have to be done on your own. Feel free to jump around to the sections you need help with.
- [MySQL Community Server](#mysql-community-server)
     - [MySQL Server Setup Wizard](#mysql-server-setup)
     - [MySQL Configurator Wizard](#mysql-configurator-setup)
- [MySQL Workbench](#mysql-workbench)
     - [MySQL Workbench Setup Wizard](mysql-workbench-setup-wizard)

## MySQL Community Server
[jump to top](#how-to-set-up-mysql-community-server-and-mysql-workbench)
The first step is to download the latest version of MySQL Community Server, found at [https://dev.mysql.com/downloads/mysql/](https://dev.mysql.com/downloads/mysql/). The version as of writing this guide is v9.0.1.

![MySQL Community Server 9.0.1 Innovation Installers: Windows MSI Installer is what you want](Images/MySQL_Server_Installers.png)

From this list of installers, click Download next to the Windows MSI Installer. This will bring you to a page that looks like this:

![No thanks, just start my download](Images/No_thanks.png)

If you don't want to log in or sign up for an Oracle Web Account, just click the **No thanks, just start my download.** button below the account buttons. This should download a file called `mysql-9.0.1-winx64.msi` to your computer. This is the installer for MySQL Community Server. Run this file.

### MySQL Server Setup
[jump to top](#how-to-set-up-mysql-community-server-and-mysql-workbench)
You should see an application pop up called MySQL Server 9.0 Setup with a welcome page to the installation wizard. We will now go through the steps for this wizard.
![Installation Welcome](Images/Installation_wizard_welcome.png)
1. Click Next. You should see an End-User License Agreement. Accept the terms and click Next.
![Installation EULA](Images/Installation_EULA.png)
2. You should see **Choose Setup Type** at the top of the wizard. Click *Typical*.
![Installation Type](Images/Installation_Type.png)
3. The wizard should now say **Ready to install MySQL Server 9.0**. Click Install. When Windows asks for permission, accept it.
4. Once installation is complete, you should see a screen that says **Completed the MySQL Server Setup Wizard**. At the bottom of this screen, there is a check box that says **Run MySQL Configurator**. Make sure that this is checked, as this is the next step for the installation. Click Finish.
![Installation Finish](Images/Installation_finish.png)

# MySQL Configurator Setup
[jump to top](#how-to-set-up-mysql-community-server-and-mysql-workbench)
Windows will ask if you want mysql_configurator.exe to have some permissions; allow it. Now you should see an application window titled MySQL Configurator with a welcome page for this configurator. We will now go through the steps for this configurator wizard.
![Configurator welcome](Images/Config_welcome.png)
1. Click Next. You should see a screen titled **Data Directory**. This is where MySQL Server 9.0 and all its related data will be stored. The default is usually good enough, but if you have a specific directory that you want, choose that one instead. Click Next.
![Configurator Directory](Images/Config_directory.png)
2. The screen should be titled **Type and Networking**. Make sure the Config Type is `Development Computer`, connectivity has TCP/IP checked, Port is `3306`, X protocol Port is `33060`, and *Open Windows Firewall ports for network access* is checked. These are usually the default options. It is also a good idea to check **Show Advanced and Logging Options** before you click Next.
![Configuration Type and Networking](Images/Config_type_networking.png)
3. The next screen should be titled **Accounts and Roles**. This is where you will choose a MySQL Root Password, so make sure it is strong. You can also create MySQL User Accounts, but this is not necessary. After entering a root password, click Next.
![Configuration Accounts and Roles](Images/Config_accounts_roles.png)
4. The next screen is titled **Windows Service**. Check **Configure MySQL Server as a Windows Service**. You can also rename the Windows Service Name, but I left it as the default. Now if you don't want MySQL Server to run whenever you reboot your computer, uncheck the  **Start the MySQL Server at System Startup** box. Note that if you uncheck the box, you will have to manually restart the MySQL server whenever you want to run it. Select **Standard System Account** and click Next.
![Configuration Windows Service](Images/Config_Service.png)
5. On the next screen, it should say **Server File Permissions**. Select the one that grants full access to the user running the Windows Service (this will be you) and click Next.
![Configuration Server File Permissions](Images/Config_perms.png)
6. The next page should be called **Logging Options**. Leave everything as default and click Next.
7. The next page should be called **Advance Options**. Leave everything as default and click Next.
8. The next page should be called **Sample Databases**. I did not select any databases to be created (neither Sakila nor World) because you should be able to create them at any point (I could be wrong). Click Next.
9. The next page should be called **Apply Configuration**. It will show the steps that the application will take; they are not check boxes (I thought they were check boxes because I didn't read it). Click Execute at the bottom to make those changes.
![Configuration Apply Configuration](Images/Config_Apply.png)
10. After clicking Execute, it will go through the steps and might take a few seconds to update permissions for the data folder or to start the server. This is normal. Once it's done, you should see "The configuration for MySQL Server 9.0.1 was successful" at the bottom of the screen. Click Next.
![Configuration Apply Configuration Succeeded](Images/Config_Apply_Success.png)
11. The final screen should say **Configuration Complete**. I didn't copy the log to keyboard because I wouldn't know what to do with that, so just click Finish.
![Configuration Complete](Images/Config_finish.png)

Congratulations! You are now done downloading MySQL Server. The next step to actually use it is to download MySQL Workbench.

## MySQL Workbench
[jump to top](#how-to-set-up-mysql-community-server-and-mysql-workbench)
The next step is to download the latest version of MySQL Workbench, found at [https://dev.mysql.com/downloads/workbench/](https://dev.mysql.com/downloads/workbench/). The version as of writing this guide is v8.0.38. Note that this version is **not fully compatible** with MySQL Server 9.0 (or even 8.4 and above) but this is not too important; we'll get into that later.
![MySQL Workbench Website](Images/Workbench_website.png)
There are not many options here; just click Download on the MSI Installer. You will again see the screen that wants you to log in; you can just click **No thanks, just start my download** at the bottom.
![No thanks, just start my download](Images/No_thanks.png)
Run the file. For me, it is called `mysql-workbench-community-8.0.38-winx64.msi`.

### MySQL Workbench Setup Wizard
[jump to top](#how-to-set-up-mysql-community-server-and-mysql-workbench)
You should see an application pop up called MySQL Workbench 8.0 CE - Setup Wizard (or something similar). We will go through the steps for this wizard.
1. Click Next on the application welcome screen.
![Workbench Setup Welcome](Images/Workbench_welcome.png)
2. The next page should say **Destination Folder** at the top. Again, I left it as default, but if you know what you're doing, you can change the folder. Click Next when you're satisfied.
![Workbench Destination Folder](Images/Workbench_folder.png)
3. The next page should say **Setup Type** at the top. Select **Complete** and click Next.
![Workbench Setup Type](Images/Workbench_type.png)
4. The next page should say **Ready to Install the Program**. Click Install.
![Workbench Ready to Install](Images/Workbench_install.png)
5. The next page is an installation progress bar, but at some point, Windows will ask if you want to allow 5d0ca6a2.msi (or something) to make changes to your device. Allow this, and the progress bar will continue until Workbench is installed.
6. Once Workbench has been successfully installed, the page will say **Wizard Completed** at the top. If you wish to test your installations now, check the **Launch MySQL Workbench now** box. Otherwise, you can always run it via the Start menu. Click Finish.
![Workbench Installation Complete](Images/Workbench_complete.png)

Now MySQL Workbench is downloaded on your computer! Congratulations; everything you need has been downloaded. The next steps are to test if everything works together, and to do this, we have some test scripts.

## Testing MySQL Installations
[jump to top](#how-to-set-up-mysql-community-server-and-mysql-workbench)
