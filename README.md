# Simple Jenkins Pipeline Setup
This repository provides simple steps to install Jenkins and Blue Ocean

**Ubuntu Install of Jenkins**

> sudo apt update

> sudo apt upgrade

> sudo apt install default-jdk

To take advantage of the latest fixes and features, you can use the project-maintained packages to install Jenkins.

Add repository key to your Ubuntu system

> wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -

After key is added, the system will output 'OK'

Append the debian package repository address to the server's source list:

> sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'

When both are in place do an update:

> sudo apt update

Now Jenkins can be installed

> sudo apt install jenkins

After installation is complete use 'systemctl' command to see if Jenkins is running

> sudo systemctl status jenkins

The output should show:

● jenkins.service - LSB: Start Jenkins at boot time
   Loaded: loaded (/etc/init.d/jenkins; generated)
   Active: active (exited) since Wed 2019-10-09 04:50:15 UTC; 48s ago
     Docs: man:systemd-sysv-generator(8)
    Tasks: 0 (limit: 1152)
   CGroup: /system.slice/jenkins.service

Oct 09 04:50:14 ip-172-31-16-179 systemd[1]: Starting LSB: Start Jenkins at boot time...
Oct 09 04:50:14 ip-172-31-16-179 jenkins[7832]: Correct java version found
Oct 09 04:50:14 ip-172-31-16-179 jenkins[7832]:  * Starting Jenkins Automation Server jenkins
Oct 09 04:50:14 ip-172-31-16-179 su[7879]: Successful su for jenkins by root
Oct 09 04:50:14 ip-172-31-16-179 su[7879]: + ??? root:jenkins
Oct 09 04:50:14 ip-172-31-16-179 su[7879]: pam_unix(su:session): session opened for user jenkins
Oct 09 04:50:14 ip-172-31-16-179 su[7879]: pam_unix(su:session): session closed for user jenkins
Oct 09 04:50:15 ip-172-31-16-179 jenkins[7832]:    ...done.
Oct 09 04:50:15 ip-172-31-16-179 systemd[1]: Started LSB: Start Jenkins at boot time.


**Setup Jenkins**

Go to your Jenkins web interface by using your localhost port 8080 address

> http://localhost:8080

You will see an initial web page

!(/images/screenshot-02.jpg)

Copy the password from the following file and input in the password box

> sudo cat /var/lib/jenkins/secrets/initialAdminPassword

You will be prompted to install plugins, select 'Install Suggested Plugins.

After the plugins installation is complete, create a new admin user and password.  Remember both username and password for access later.

A page will be shown confirming URL, click on Save and Finish


**(Optional) Install Blue Ocean Plugin**

Login as admin.  On the left pane window go to Manage Jenkins --> Manage Plugins.

Go to the Available tab and search for Blue Ocean (Blue Ocean Aggregator) and select Install without Restart

Jenkins will install Blue Ocean

