---
title: Writing sample for a concept
linktitle: Concepts
type: docs
weight: 200
---

##  Main concepts

### What is DROPS WAP
The DROPS WAP solution is an ARCAD application with a monitoring Web interface.
The DROPS WAP process is fully integrated with the ARCAD deployments: the distribution macro-commands call the DROPS WAP functions. Execute the macro-commands in ARCAD and monitor the results in the DROPS WAP Web Studio.

### How DROPS WAP works

ARCAD application variables are used to control if DROPS WAP is proposed when distributing a release to a target site.​  
The standard ARCAD macro-command (DISTRIB) starts and ends the DROPS WAP replication and synchronization process. The progress of the replication and synchronization is monitored with the DROPS WAP Web Studio.​
Files under DROPS WAP pass through two stages: replication and then synchronization.​  
Data from production files is replicated into the new file formats in DROPS WAP library.​  
New format data is kept in synchronization with production changes via IBM i Journals.​  
The synchronization is maintained until DROPS WAP stops.​  
DROPS WAP can be stopped and re-started, such as to perform a system backup. It maintains its last known replication or synchronization in its memory.​  
DROPS WAP is stopped by a macro-command after ending application activity. The macro-command invokes ARCAD to move the new files and other objects into target libraries.  

### DROPS WAP in action

Setup up the solution
Activate the use of DROPS WAP with the ARCAD distribution process on the development site (Setup on the Development site) and the production (target) site (Setup on the Production site).


Configure the DROPS WAP Web Studio to work with your ARCAD server (Source connectors).


Analyze your files
The first general consideration when using DROPS WAP is to make sure you know what files to include in the process. Analyze your application and decide what files to include.


Launch DROPS WAP with ARCAD macro-commands
Run the DISTRIB macro-command to start the distribution of your application release (Distributing with macros).


Edit and validate the list of files to be managed with DROPS WAP (Edit the list of files (LSTWAP)) when the macro-command displays this list.


Ensure the process of DROPS WAP starts (Montoring DWBASE and DWSTRJRNE​ jobs launched to batch).


Monitor progress with the DROPS WAP Web Studio
Monitor the progress of the replication and the synchronization on the DROPS WAP Web Studio (Monitoring file replication).


Wait until all files are copied and synchronized with journals before stopping the live application environment where the new release will be installed. DROPS WAP keeps the file data synchronized until you stop it.


Transfer to production
The Transfer to production is the end of the process, when your data is ready to be deployed along with the rest of the release. When you want to end the production application and to move the new release into production, run the RCVNTWA2 macro-command ending the DROPS WAP process.

## About this sample  

This topic aims to provide the user with an overview of the software, its functionality, and a tour of the workflow/user tasks involved. It also includes links to relevant parts of the documentation. I wrote the topic based on notes shared with me by the lead engineer. She then reviewed the topic, and we made adjustments accordingly. After that, my technical writer teammate reviewed the writing quality. I created the first version of this documentation using the Madcap Flare XML toolchain.  

## Live documentation
https://help-drops-wap.arcadsoftware.com/Topics/About/MainConcepts.htm
