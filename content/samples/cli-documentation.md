---
title: Writing sample for a product without a graphical interface (CLI)
linktitle: CLI documentation
type: docs
weight: 500
---


## The Command Line Interface (CLI)

The Anonymizer Command Line Interface executes predefined anonymization processes from the command line. Use the CLI to:

- list the rules, engines or anonymization projects defined on your Anonymizer Server,
- executes anonymization projects on either a Design Server or a Production Server,
- display the status of project executions.


The Anonymizer CLI is distributed as a zip file. Extract the content into the folder of your choice. Go to the */bin* folder to launch the CLI.

>Note  
The CLI needs to have access to a Java 8 Runtime Environment installed and accessible from anywhere in a command line terminal (run `java -version` to find the current accessible Java version).

>Important!  
The CLI launches processes from the Anonymizer Server using the login of a defined user. That user must have all the rights required to run the processes called by the CLI.


To call any action using the CLI, the following syntax is used: `anonymizer` *\<command\> \<parameters\>*.

Support of the commands from the previous versions of Anonymizer CLI is maintained. Refer to the command **alias** to know the previous name of a command.
If you were using the previous version of the Anonymizer CLI, the commands 

### Common parameters

The following parameters are common to all CLI commands.

`-H`, `--help`  
: Display the help message for the command.

`-S`, `--server`  
: *\[Required\]* The URL of the Anonymizer Server to which to connect.

`-U`, `--user`  
: *\[Required\]* The user used to connect to the Anonymizer Server.

`-P`, `--password`  
: *\[Required\]* The password used to connect to the Anonymizer Server.

`-C`, `--crypted`  
: Required if the password is Base64 encrypted.

`-L`, `--log-file`  
: The path to the file where the logs will be written.

`-V`, `--verbose`  
: Enable debug and trace log levels.

### project

Alias: `anyListProject`

This command sends a request to list all the existing anonymization projects or get information about a specific project on an Anonymizer Server.

Usage: `anonymizer project [-CHV] -P[=<password>] [-P[=<password>]]... [-L=<logFile>] [-n=<name>] -S=<serverURL> -U=<user>`.

`-n`, `--name`  
: The name of the project.

### rule

Alias: `anyRuleList`

This command sends a request to list all the existing project rules or get information about a specific rule on an Anonymizer Server.

Usage: `anonymizer rule [-CHV] -P[=<password>] [-P[=<password>]]...[-L=<logFile>] [-n=<name>] -S=<serverURL> -U=<user>`

`-n`, `--name`  
: The name of the rule.

### engine

Alias: `anyEngineList`

This command sends a request to list all the existing project engines or get information about a specific engine on an Anonymizer Server.

Usage: `anonymizer engine [-CHV] -P[=<password>] [-P[=<password>]]...[-L=<logFile>] [-n=<name>] -S=<serverURL> -U=<user>`

`-n`, `--name`  
: The name of the engine.

### status

This command sends a request to list the statuses of all the existing project executions or get details of about the status of a specific project.

Usage: `anonymizer status [-CHV] -P[=<password>] [-P[=<password>]]...[-L=<logFile>] [-n=<name>] -S=<serverURL> -U=<user>`

`-n`, `--name`  
: The execution session name to get the status.

### executeProject

Alias: `anyAnonymizeProject`

This command sends a request to execute a predefined anonymization project.

Usage: `anonymizer executeProject [-CHV] [-e[=<execute>]] [-w[=<wait>]] -P[=<password>] [-P[=<password>]]...[-L=<logFile>] [--parameters=<parameters>][-pc=<projectCode>] -S=<serverURL> [-sn=<sessionName>] -U=<user> [-sp=<sessionProperties>[,<sessionProperties>...]]...`

`-pc`, `--projectCode`  
: The code of the project to execute.  
Alias: `-any.projectcode`

`-sn`, `--sessionName`  
: The name/ID of the execution instance to run.  
Alias: `-any.execname`

`-sp`, `--sessionProperties`  
: This parameter is used to declare the parameters of the execution session.

`-w`, `--wait`  
: When this option is defined, the command waits for the end of the anonymization project and for the project to return to a simple status (for example: `Anonymization Project Status : OK` or `Anonymization Project Status : ERROR`).  
By default, this option is activated and set to `true`.  
Alias: `-any.wait`

`-e`, `--execute`  
: Create and run an execution instance. By default, this option is activated and set to true.

`--parameters`  
: The project's execution parameters. Add the project parameter values in JSON format.  
`{"$param_schema":"schema",`  
`"$server":"server"}`  
In parameters, avoid characters that can be interpreted as a JSON separator. For example, for the colon character in a connection URL *server:port*, it is recommended to use two parameters for the server name and the port instead.  
Alias: `-any.parameters`

### executeProductionProject

Alias: `anyProdAnonymizeProject`

This command sends a request to execute a predefined anonymization project, from the production server. Additional parameters also allow the modification of data sources.

Usage: `anonymizer executeProductionProject [-CHV] [-e[=<execute>]] [-w[=<wait>]] -P[=<password>] [-P[=<password>]]... [-dsp=<datasourcePass>][-dsu=<datasourceUser>] [-dsurl=<datasourceUrl>] [-L=<logFile>][--parameters=<parameters>] -pc=<projectCode> -pv=<projectVersion>-S=<serverURL> [-sn=<sessionName>] -U=<user> [-sp=<sessionProperties>[,<sessionProperties>...]]...`

`-dsp`, `--datasourcePassword`  
: Makes it possible to override the data source password.  
Alias: -any.datasource.pass

`-dsu`, `--datasourceUser`  
: Makes it possible to override the data source user.  
Alias: `-any.datasource.user`

`-dsurl`, `--datasourceUrl`  
: Makes it possible to override the data source URL.  
Alias: `-any.datasource.url`

`-pc`, `--projectCode`  
: The code of the project.  
Alias: `-any.projectcode`

`-pv`, `--version`  
: The version of the project to execute.  
Alias: `-any.projectversion`

`-sn`, `--sessionName`  
: The name of the execution.  
Alias: `-any.execname`

`-sp`, `--sessionProperties`  
: Makes it possible to declare the parameters of the execution session.

`-umv`, `--useMainVersion`  
: This parameter is used to execute the main version of the project package, if it is defined.

`-w`, `--wait`  
: Makes it possible to wait for the end of the anonymization process. By default, this option is activated and set to true.

`-e`, `--execute`  
: Create and execute an execution session. By default, this option is activated and set to true.

`--parameters`  
: The project's execution parameters. Add the project parameter values in JSON format.  
`{"$param_schema":"schema",`  
`"$server":"server"}`  
In parameters, avoid characters that can be interpreted as a JSON separator. For example, for the colon character in a connection URL *server:port*, it is recommended to use two parameters for the server name and the port instead. 
Alias: `-any.parameters`

### productionProjectPackage

This command sends a request to list all the Project Packages on a Production Server.

Usage: `anonymizer productionProjectPackage [-CHV] -P[=<password>] [-P[=<password>]]... [-L=<logFile>] -S=<serverURL> -U=<user>`

### productionStatus

This command sends a request to list the statuses of all the existing project executions or get details of about the status of a specific project on a Production Server.

Usage: `anonymizer productionStatus [-CHV] -P[=<password>] [-P[=<password>]]...[-L=<logFile>] [-n=<name>] -S=<serverURL>-U=<user>`

`-n`, `--name`  
: The name of the execution session to get the status.

[...]

## live documentation

Click the link to see the [live documentation](https://help-dot-anonymizer.arcadsoftware.com/en-us/Topics/Tools/Anonymizer-CLI.htm).