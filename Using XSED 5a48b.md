# Using XSEDE (Visual Studio Code)

---

## Requirements

---

- XSEDE account
- DUO
- Visual Studio Code
- (Visual Studio Code) Extension: Remote SSH

---

### Step by step (tutorial)

---

1. The first step is the creation of the XSEDE account with your CMU email address.
2. Then you need to enable DUO authentication. **SSH protocol won't work without that.** Go to *XSEDE user portal → My XSEDE → Profile → Duo enrollment.*

[XSEDE User Portal | Multi-Factor Authentication with Duo](https://portal.xsede.org/mfa)

![Screenshot from 2022-03-03 11-48-42.png](Using%20XSED%205a48b/Screenshot_from_2022-03-03_11-48-42.png)

1. Then, you need to install Visual Studio Code according to your Operational System (OS): 

[Download Visual Studio Code - Mac, Linux, Windows](https://code.visualstudio.com/download)

1. Now, you open your VS Code and install go to the *extensions (Ctrrl+Shift+X)*
2. Then, install the *Remote-SSH extension: en*

[Developing on Remote Machines using SSH and Visual Studio Code](https://code.visualstudio.com/docs/remote/ssh)

![Screenshot from 2022-03-03 12-11-45.png](Using%20XSED%205a48b/Screenshot_from_2022-03-03_12-11-45.png)

### Using Remote - SSH

1. Then, you need to click on the symbol below:

![Screenshot from 2022-03-03 12-16-05.png](Using%20XSED%205a48b/Screenshot_from_2022-03-03_12-16-05.png)

1. A new window will open automatically on VS Code. You must select *Connect to Host:* 

![Screenshot from 2022-03-03 12-24-26.png](Using%20XSED%205a48b/Screenshot_from_2022-03-03_12-24-26.png)

1. Then, you must add *XSEDE* as *a new host:*

![Screenshot from 2022-03-03 12-22-28.png](Using%20XSED%205a48b/Screenshot_from_2022-03-03_12-22-28.png)

1. Then use a single sign-in point: [login.xsede.org](http://login.xsede.org/) to connect via SSH. The total process should look like this:

![Screenshot from 2022-03-03 12-23-01.png](Using%20XSED%205a48b/Screenshot_from_2022-03-03_12-23-01.png)

```bash
(base) user@comp ~ % ssh -l XUPusername login.xsede.org
```

XUPusername — is XSEDE login

**Now your new host is added!!!**

Your */home/$USER/.ssh/config* (**generated automatically**) **file should seems like this:

```jsx
Host login.xsede.org
  HostName login.xsede.org
  User XUPusername
```

P.S. : Repeat the steps (**6**), (**7**) and (**8**). But now, you need to click on *login.xsede.org:*

![Screenshot from 2022-03-03 12-44-52.png](Using%20XSED%205a48b/Screenshot_from_2022-03-03_12-44-52.png)

1. A new window will open, asking your password (the password is the same you use to login into the website. If you want to read more, see the link below)

[XSEDE User Portal | XSEDE Single Sign-On Hub](https://portal.xsede.org/web/xup/single-sign-on-hub)

![Screenshot from 2022-03-03 12-47-32.png](Using%20XSED%205a48b/Screenshot_from_2022-03-03_12-47-32.png)

1. Since your username and password are correct, you will be asked for DUO authentication:

![Screenshot from 2022-03-03 12-49-41.png](Using%20XSED%205a48b/Screenshot_from_2022-03-03_12-49-41.png)

P.S. : You may type option **1** or your **passcode (available in your DUO mobile app)**

You can find further information in the video tutorial: [youtu.be/2Y5br8fWwuE](https://t.co/gCQPJdPhrW)

### Bridges2

1. To access bridges2, you need to follow the standard protocol, since you are inside of XSEDE:

```bash
gsissh bridges2
```

1. What you'll see here is single sign-in points for the bridges cluster.

```bash
[your_username@ssohub ~]$ gsissh bridges2
********************************* W A R N I N G ********************************
You have connected to br011.ib.bridges2.psc.edu, a login node of Bridges 2.

This computing resource is the property of the Pittsburgh Supercomputing Center.
It is for authorized use only.  By using this system, all users acknowledge
notice of, and agree to comply with, PSC polices including the Resource Use
Policy, available at http://www.psc.edu/index.php/policies. Unauthorized or
improper use of this system may result in administrative disciplinary action,
civil charges/criminal penalties, and/or other sanctions as set forth in PSC
policies. By continuing to use this system you indicate your awareness of and
consent to these terms and conditions of use.

LOG OFF IMMEDIATELY if you do not agree to the conditions stated in this warning

********************************* W A R N I N G ********************************

For documentation on Bridges 2, please see www.psc.edu/resources/bridges-2/user-guide/
Please contact help@psc.edu with any comments/concerns.

Projects
------------------------------------------------------------
Project: cie160013p PI: Franz Franchetti ***** default charging project *****
  Extreme Memory             8,064 SU remain of 8,064 SU        active: Yes
  GPU                        6,346 SU remain of 12,247 SU       active: Yes
  Regular Memory            36,572 SU remain of 42,303 SU       active: Yes
  Ocean /ocean/projects/cie160013p 1.983T used of 34.18T

[your_username@bridges2-login011 ~]$ projects
Your default charging project charge id  is cie160013p.  If you would like to change the default charging project use the command change_primary_group ~charge_id~. Use the charge id listed below for the project you would like to make the default in place of ~charge_id~

Project: CIE160013P
     PI: Franz Franchetti
  Title: Campus Champion - Carnegie Mellon University

      Resource: Bridges 2 Extreme Memory
    Allocation: 8,064.00
       Balance: 8,064.00
      End Date: 2022-05-17
  Award Active: Yes
   User Active: Yes
     Charge ID: cie160013p
     *** Default charging project ***
   Directories:
       HOME /jet/home/your_username

      Resource: Bridges 2 GPU
    Allocation: 12,247.00
       Balance: 6,346.41
      End Date: 2022-05-17
  Award Active: Yes
   User Active: Yes
     Charge ID: cie160013p
     *** Default charging project ***
   Directories:
       HOME /jet/home/your_username

      Resource: Bridges 2 Ocean Storage
    Allocation: 35,000.00
       Balance: 32,969.10
      End Date: 2022-05-17
  Award Active: Yes
   User Active: Yes
     Charge ID: cie160013p
   Directories:
       HOME /jet/home/your_username
       STORAGE /ocean/projects/cie160013p
       STORAGE /ocean/projects/cie160013p/your_username
       STORAGE /ocean/projects/cie160013p/shared

      Resource: Bridges 2 Regular Memory
    Allocation: 42,303.00
       Balance: 36,572.82
      End Date: 2022-05-17
  Award Active: Yes
   User Active: Yes
     Charge ID: cie160013p
     *** Default charging project ***
   Directories:
       HOME /jet/home/your_username

---------------------------------------------------
```

1. Bridges have two modes of operation (see above): batch mode and interactive mode. To enter the interactive mode use the *interact* command:

```bash
[your_username@bridges2-login011 ~]$ interact

A command prompt will appear when your session begins
"Ctrl+d" or "exit" will end your session

--partition RM-small,RM-shared
salloc -J Interact --partition RM-small,RM-shared
salloc: Pending job allocation 4978230
salloc: job 4978230 queued and waiting for resources
salloc: job 4978230 has been allocated resources
salloc: Granted job allocation 4978230
salloc: Waiting for resource configuration
salloc: Nodes r001 are ready for job
[your_username@r001 ~]$ df -h
Файловая система                         Размер Использовано  Дост Использовано% Cмонтировано в
/dev/nvme0n1p3                             296G          16G  266G            6% /
tmpfs                                      126G            0  126G            0% /sys/fs/cgroup
devtmpfs                                   126G            0  126G            0% /dev
tmpfs                                      126G            0  126G            0% /dev/shm
tmpfs                                      126G         130M  126G            1% /run
/dev/nvme0n1p1                             511M         1,9M  510M            1% /boot/efi
/dev/md0                                   6,1T          43G  6,0T            1% /local
10.8.8.18@o2ib20:10.8.8.19@o2ib20:/ocean    14P         7,7P  5,8P           58% /ocean
10.8.8.36@o2ib20:10.8.8.37@o2ib20:/jet     190T          35T  153T           19% /jet
[your_username@r001 ~]$ free -h
              total        used        free      shared  buff/cache   available
Mem:          251Gi        29Gi       211Gi        29Mi       9,9Gi       219Gi
Swap:         699Gi       234Mi       699Gi
[your_username@r001 ~]$ lscpu | egrep 'Model name|Socket|Thread|NUMA|CPU\(s\)'
CPU(s):              128
On-line CPU(s) list: 0-127
Thread(s) per core:  1
NUMA node(s):        2
NUMA node0 CPU(s):   0-63
NUMA node1 CPU(s):   64-127
```

To leave it, just type:

```bash
[your_username@r001 ~]$ exit
exit
salloc: Relinquishing job allocation 4978230
[your_username@bridges2-login011 ~]$
```

Or Ctrl+D

---

Just adding to what Daniil said. You can use available software, including Gaussian, Anaconda3, and many others. To see what is available, run:

```python
module spider
```

You’ll get a software list. 

To load Gaussian, for example:

```python
module load gaussian
```

and anaconda3 will load anaconda that works with python3:

```python
module load anaconda3
```