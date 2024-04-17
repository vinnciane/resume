---
title: Writing sample for a concept
linktitle: Concept
type: docs
weight: 200
---

##  Main concepts

### What is \[PRODUCT\]
The \[PRODUCT\] solution is an \[REDACTED\] application with a monitoring Web interface.
The \[PRODUCT\] process is fully integrated with the \[REDACTED\] deployments: the distribution macro-commands call the \[PRODUCT\] functions. Execute the macro-commands in \[REDACTED\] and monitor the results in the \[PRODUCT\] Web App.

### How \[PRODUCT\] works

\[REDACTED\] application variables are used to control if \[PRODUCT\] is proposed when distributing a release to a target site.​  

The standard \[REDACTED\] macro-command (DISTRIB) starts and ends the \[PRODUCT\] replication and synchronization process. The progress of the replication and synchronization is monitored with the \[PRODUCT\] Web Studio.​

Files under \[PRODUCT\] pass through two stages: replication and then synchronization.​  

* Data from production files is replicated into the new file formats in \[PRODUCT\] library.​  
* New format data is kept in synchronization with production changes via IBM i Journals.​  
* The synchronization is maintained until \[PRODUCT\] stops.​  

\[PRODUCT\] can be stopped and re-started, such as to perform a system backup. It maintains its last known replication or synchronization in its memory.​  

\[PRODUCT\] is stopped by a macro-command after ending application activity. The macro-command invokes \[REDACTED\] to move the new files and other objects into target libraries.  

### \[PRODUCT\] in action

***Setup up the solution***  

* Activate the use of \[PRODUCT\] with the \[REDACTED\] distribution process on the development site (*\[link\]* Setup on the Development site) and the production (target) site (*\[link\]* Setup on the Production site).

* Configure the \[PRODUCT\] Web Studio to work with your \[REDACTED\] server (*\[link\]* Source connectors).


***Analyze your files***

* The first general consideration when using \[PRODUCT\] is to make sure you know what files to include in the process. Analyze your application and decide what files to include (*\[link\]* Analyze your application).


***Launch \[PRODUCT\] with \[REDACTED\] macro-commands***  

* Run the DISTRIB macro-command to start the distribution of your application release (*\[link\]* Distributing with macros).

* Edit and validate the list of files to be managed with \[PRODUCT\] (*\[link\]* Edit the list of files (LSTWAP)) when the macro-command displays this list.

* Ensure the process of \[PRODUCT\] starts (*\[link\]* Montoring DWBASE and DWSTRJRNE​ jobs launched to batch).


***Monitor progress with the \[PRODUCT\] Web Studio***  

* Monitor the progress of the replication and the synchronization on the \[PRODUCT\] Web Studio (*\[link\]* Monitoring file replication).

* Wait until all files are copied and synchronized with journals before stopping the live application environment where the new release will be installed. \[PRODUCT\] keeps the file data synchronized until you stop it.


***Transfer to production***  

* The Transfer to production is the end of the process, when your data is ready to be deployed along with the rest of the release. When you want to end the production application and to move the new release into production, run the RCVNTWA2 macro-command ending the \[PRODUCT\] process.



## About this sample  

This topic aims to provide the user with an overview of the software, its features, and a tour of the workflow/user tasks involved. It also includes links to relevant parts of the documentation. I wrote the topic based on notes shared with me by the lead engineer. She then reviewed the topic, and we made adjustments accordingly. After that, my technical writer teammate reviewed the writing quality. I created the first version of this documentation using the Madcap Flare XML toolchain.  

## Live documentation

Click the link to see the [live documentation](https://help-drops-wap.arcadsoftware.com/Topics/About/MainConcepts.htm).
