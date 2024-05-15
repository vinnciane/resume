---
title: Writing sample for a procedure
linktitle: Procedure
type: docs
weight: 300
---


## Declaring an application

**Step 1**   Right-click on **Applications** in the navigator and select **Declare an application**.

**Step 2**   Define the required parameters:

Application ID  
: Set a unique application ID. This ID can be ten characters long but cannot exceed five characters if you wish to use the default prefix (*DFT) for your ARCAD libraries.  

Text  
: Enter a short description to identify the application.

Application managers  
: An application manager has to make sure that the application runs properly for all the users.  
    Select the profile of the application manager from the drop-down list, that corresponds to ARCAD declared developers.

ARCAD lists library  
: Set the library containing the ARCAD lists needed to manage the application.

ARCAD library prefix  
: Define the prefix for all the libraries when the length of the application ID is more than four characters.  
    Set the prefix of the name given to the libraries linked to the application. The library is needed for the execution and compilation of all components of the application. The available options are the following:  
        ***DFT**: the library prefix name contains the application code, the environment code and the formatted version.  
        **Name**: a custom library prefix name.

Initial Version #  
: Set the initial version number that you want to assign to the application. By default, the initial version number is *01.00.00*.  

ASP group  
: Define the ASP group associated with the application.  
The available options are the following:  
 - \*SYSBAS: the application does not have an associated ASP group.  
 - Name: a custom ASP group name.  
By default, the ASP group parameter is set to *SYSBAS.  

Click **Next >** to continue.  

**Step 3**   Define the IFS Directories to link to the new application. Click Add to select the directory.  

Click **Next >** to continue.  

**Step 4**   Select which task you wish to execute after declaring the application.

Create a Development Environment
: Tick this checkbox to automatically create a development environment (*DEV) at the end of the application declaration.

Load Repository  
: Tick this checkbox to automatically load the ARCAD Repository. This option executes the third phase in the process of the declaration of an application, corresponding to the DECLARE3 macro-command.  

Click **Next >** to continue.  

**Step 5**   The wizard displays a summary of the command that the declared application action is going to execute. You can check the parameters entered and make any changes necessary.
Click **Prompt command** to test the parameters set and check that they are correct.  

Click **Finish**.  

**Result**   The command is executed and the application is successfully declared.

## About this sample

This procedure is a setup task for an Eclipse-based software product. It is common for these types of products to have fairly complex wizards to perform a task. To focus on the user experience when working in such wizards, I used steps to stick to the pages of the wizard and keep the user 'in situ' with the user interface. Within these steps, I used definition lists to break down the different concepts and actions on each page.  
I prepared the procedure as part of a Getting Started guide, and it was reviewed by a senior consultant for the content and by my technical writer teammate for the writing quality.  

## Live documentation

Click the link to see the [live documentation](https://help-arcad-repository.arcadsoftware.com/Topics/Setup/Declaring-Applications.htm).
