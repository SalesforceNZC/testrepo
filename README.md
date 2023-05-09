# testrepo
Steps to contribute to and work with NZC internal repo

# Github setup:
1.	Set up a github account using your salesforce.com email: https://github.com/ 
2.	Log a ticket for TMP Network Access Request (this is approved by your manager; once manager approves they will ): https://concierge.it.salesforce.com/articles/en_US/Supportforce_Article/How-to-Gain-Access-to-the-SFM-Aloha-tile
3.	The Access request fullfillment will enable you to sync your account with the enterprise account (soma.salesforce.com); this closes down anything in your repo to internal salesforce only (anything "public" is available to salesforce enterprise accounts only)

# To pull from an environment and push to github using Workbench:
1.	Create an outgoing change set in source org with metadata
2.	Log into Workbench (using source org credentials): https://workbench.developerforce.com/login.php 

    a.	If you are not sure what org Workbench logged into, hover over your name in the upper right area of Workbench to see the username
3.	In workbench go to --> migration --> Retrieve --> enter the change set name in “Package Names:”
4.  Click to "Download ZIP File" and open on your local 
5.  Open the ZIP folder - contents that will be used to push to repo are: package.xml + all of the subfolders of metadata (example "classes", etc.)
6.  Go to github --> repositories --> click new --> name repo, fill in Description, select public (allows SF employees to access), select to Add a README file
7.  Click add file --> upload files --> upload each of the files (the package.xml and all metadata files)
8.  Scroll to bottom and click to Commit Changes
9.  Fill in the README.md file with any instructions or info for re-use


# To pull from github and push to an environment using Workbench:
1.  Go to selected repo --> click Code (green button) --> Download Zip
2.  Open the zip
3.  Rezip without the README.md (so just the package.xml + all the metadata folders)
4.  Log into Workbench using your destination org credentials
5.  In workbench go to --> migration --> Deploy --> choose the zipped file you created 
6.  # (TBD on what checkboxes if any, and any test level to select)

# To use ANT migration to pull from environment: 
1. Install ANT migration tool; you will use 2 files: build.properties + build.xml (these are commands that talk to the terminal) 
2. open build.properties and edit the following to authenticate into the source org and pull the outbound change set:  
   a. sf.username (your username)  
   b. sf.password (your password)
   
   c. sf.packagename
4. open terminal and type the following and then press enter: ant retreiveChangeset
5. allow it to complete and confirm it was BUILD SUCCESSFUL

# To use ANT migration to deploy to environment: 
1. 
