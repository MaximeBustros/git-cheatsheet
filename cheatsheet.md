# Git Cheatsheet

## Settings
```$ git config --list``` View all settings  
```$ git config --list --show-origin``` View all settings and where they are coming from  
```$ git config <key>``` View value of a specific key  
```$ git config --show-origin <key>``` Check origin of value of said key

Note: Keys can appear more than once because git reads the configuration from different files
```$ git config --global user.name "John Doe"``` Configure user.name  
```$ git config --global user.email johndoe@example.com``` Configure user.email  
```$ git config --global core.editor emacs``` Configure editor on linux/mac  
```$ git config --global core.editor "'C:/Program Files/Notepad++/notepad++.exe' -multiInst -notabbar -nosession -noPlugin"``` Configure editor on Windows  
```$ git config --global init.defaultBranch main``` Change default main branch  

## Getting help
``` $ git help <verb>```  
``` $ git <verb> --help```  
``` $ man git-<verb>``` Only for unix  
``` $ git <verb> -h``` Show parameters of said command  

## Getting a Git repository
``` $ git init``` Initializing a repository in an existing directory  
``` $ git clone <url>``` Cloning existing Repository from url  
``` $ git clone <url> <target>``` Clones an exisisting repository from a url and puts it in a directory called "target"  

## Basic commands
``` $ git status``` Checking status of the working directory  
``` $ git add . ``` Add all files to tracked files  
``` $ git add <filename>``` Add a single file to tracked files  
``` $ git add <directory>``` Add all files in a directory recursively to tracked files  
