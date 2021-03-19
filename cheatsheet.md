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

## Add command
``` $ git add . ``` Add all files to tracked files  
``` $ git add <filename>``` Add a single file to tracked files  
``` $ git add <directory>``` Add all files in a directory recursively to tracked files  

## Commit command
``` $ git commit -m <message>``` Commit staged files  
``` $ git commit --amend``` Replace previous commit with most recent staged files. Ammend is useful when forgetting to stage a file or making a mistake in the commit message

## Uncommiting files
``` $ git reset HEAD <file>``` Removes a file from staged files
``` $ git checkout <file>``` Remove
## Status command
``` $ git status``` Checking status of the working directory  
``` $ git status -s``` Checking the short status of the working directory  

## Ignoring files
To ignore files add a .gitignore in the root directory
* Blank lines or lines starting with # are ignored.
* Standard glob patterns work, and will be applied recursively throughout the entire working tree
* You can start patterns with a forward slash (/) to avoid recursivity.
* You can end patterns with a forward slash (/) to specify a directory.
* You can negate a pattern by starting it with an exclamation point (!).

### Glob patterns
* (\*) matches 0 or more characters
* \[abc\] matches any character inside the brackets
* ? matches a single character
* [0-9] matches any character between them (in this case 0 through 9)
* ```match nested directories; a/**/z would match a/z, a/b/z, a/b/c/z, and so on. ```

