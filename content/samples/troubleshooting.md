---
title: Writing sample for a troubleshooting article
linktitle: Troubleshooting
type: docs
weight: 400
---


## An error is thrown when launching a command through the CLI to anonymize a project \[Linux\]

When executing a command to anonymize a project on a Linux operating system (Ubuntu or CentOS) via the command line interface (CLI), the following error may occur:

*Error: Could not find main class cache2k-core-1.6.0.Final.jar*

This error occurs even if the necessary library exists in the /libs folder.

To resolve this issue, certain Linux distributions such as CentOS, Ubuntu, and Debian, require the classpath to be enclosed in double quotes. Here is the corrected command format for CentOS:

```
// CentOS Command
java -cp "../libs/*" com.redacted.tools.anonymizer.cli.CLI List
```