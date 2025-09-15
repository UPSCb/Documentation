# Microscopy storage access

For microscope users, things are set-up slightly differently. Access is provided on the PI group level and the directories are named with the first letter of PI's first name followed by their last name e.g. if PI is Nicolas Delhomme, directory will be ndelhomme. Each group has a password that you can access in messages pinned on Slack channels named after PIs.

## Connecting from your computer

You will need to be within UPSC or connected to the UmU network with VPN. A **web interface** can be accessed [here](https://hopper.srv.its.umu.se:5001/#/signin). 

You can also mount the network directory (which will make it visible and accessible) on your work computer by following the steps below.

### Windows 

If you are already connected to the microscopy drive from your computer, then disconnect it first as follows:

1. In the File Explorer, go to "This PC" 

2. click on the three dots ... and select Disconnect Network Drive 

3. select the microscopy folder and press OK

Otherwise (or then):

1. In the File Explorer, go to "This PC"

2. Click on the three dots ... and select Add network location 

3. Click Choose a custom network location Then enter: \\hopper.srv.its.umu.se\XXXXX (replace XXXXX with the name of the folder) 

5. Then at the Enter network credentials step, use the credentials shared with you on Slack, check in the box "Remember my credentials" 

6. Press OK

### MacOS

1. In the Finder, click Go and connect to server...

2. Use the URL smb://hopper.srv.its.umu.se/XXXXX (replace XXXXX with the name of the folder)

3. Accept when the message pops up saying "you are trying to connect to hopper...

4. Change the credentials to those shared with you on Slack

5. You may check the box to save the password in your keychain

>!!! Note 
For some users, it only worked after capitalising the first letter of the username, e.g. using Ndelhomme instead of ndelhomme

### Linux

If you are using e.g. Ubuntu, you can similarly access the folder. We have not had any such use-case so far, so contact the facility if you are interested.

### On common lab computers

These are e.g. computers associated with lab instruments from the microscopy facility or others (RNA/DNA lab).

## Microscopy platform

As part of the storage centralisation process, the data from the microscopy platform is being migrated. For that, we have generated a list of all known users and a detailed migration process.

### Users list

The list of all know users is available [there](https://docs.google.com/spreadsheets/d/1jotxTXwJb3Dt136HSsVsOaMJvj9D9dbpPWAVCWmMUsA/edit?gid=0#gid=0) (note that anyone with the link can modify the information, so be warry when accessing and modifying it). As a user, take a look and confirm your affiliation and whether the data there should be considered Hot or Cold [described here](9.%20storage.md). As a group leader, take a look and ensure that all alumni from your group have been assigned correctly and similarly, decide whether the data should be considered Hot or Cold.


### Migration process

The migration process for a given research group consists of the following steps:

1. Identifying the users members of that group. 

2. Deciding on the type of storage, Cold, Hot or both. 

3. Setting up the new storage. 

4. Creating a new user for the research group 

5. The active members of the research group are invited to the Slack channel of the UPSC Bioinformatics Facility. This is to ensure that credentials are shared in a secure way, as well as to provide a means of communication between the group and the facility about the storage (maintenance and downtime information, need for an increased quota, addition / removal of users, etc.). 

6. The data is moved, individual user access is disabled and the user common to the group is activated. 

7. Users can access their data as described in the section above (How to access).
