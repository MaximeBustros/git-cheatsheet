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
``` $ git restore --staged <file>``` Unstages a file but do not remove changes
``` $ git restore <file>``` Unstage a file and discard changes in working directory

## Remove changes
``` $ git checkout -- <file>``` Remove changes to a file

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
* You can negate a pattern by starting it with an exclamation point (!)
* ```match nested directories; a/**/z would match a/z, a/b/z, a/b/c/z, and so on. ```

## Git Diff commands
``` $ git diff``` shows changes that were not yet staged  
``` $ git diff --staged or --cached``` Shows changes between staged and last commit  
``` $ git difftool --tool-help``` Check external tools for diffing  

## Removing files
``` $ git rm <filename>``` Removes file from working directory and stages removal  
``` $ git rm --cached <filename>``` Remove file from staging area but keep it and in the working directory  

## Moving Files
``` $ git mv <source> <destination>``` Moves file and track the move

## Viewing Commit history
``` $ git log``` lists the commits made in that repository in reverse chronological order  
```-p or --patch``` Shows the difference (the patch output)  
```-<number>``` Shows n number of entries  
```--stat``` Shows number of changes on each files  
```--stat``` Show statistics for files modified in each commit.  
```--shortstat``` Display only the changed/insertions/deletions line from the --stat command.  
```--name-only``` Show the list of files modified after the commit information.  
```--name-status``` Show the list of files affected with added/modified/deleted information as well.  
```--abbrev-commit``` Show only the first few characters of the SHA-1 checksum instead of all 40.  
```--relative-date``` Display the date in a relative format (for example, “2 weeks ago”) instead of using the full date format.  
```--graph``` Display an ASCII graph of the branch and merge history beside the log output.  
```--pretty``` Show commits in an alternate format. Option values include oneline, short,  
```full, fuller, and format``` (where you specify your own format).  
```--oneline``` Shorthand for --pretty=oneline --abbrev-commit used together.  
```$ git log -S <Text>``` Checks last time text was changed (Could be useful for checking the last time a reference to a function was changed)  

### Limiting output
```-<n>``` Show only the last n commits  
```--since, --after``` Limit the commits to those made after the specified date.  
```--until, --before``` Limit the commits to those made before the specified date.  
```--author``` Only show commits in which the author entry matches the
specified string.  
```--committer``` Only show commits in which the committer entry matches the
specified string.  
```--grep``` Only show commits with a commit message containing the string  
```-S``` Only show commits adding or removing code matching the string  
```--no-merges``` Removes merge commits

## Working with remotes
```$ git remote -v``` Shows remote    
```$ git remote add <shortname> <url>``` Adding a remote
```$ git remote show <shortname>``` Shows information about remote branch
```$ git remote rename <shortname> <newname>``` Rename
```$ git remote remove|rm <shortname>``` Remove remote

```$ git fetch ``` Gets all the information that you do not have yet on your local machine  
```$ git fetch <shortname>``` Gets all the information that you do not have yet on your local machine  
NOTE: When cloning a repo it automatically adds that remote repository under the name 'origin'
```$ git push origin master``` Push master branch to url pointed by origin

## Tagging
```$ git tag``` Lists tags  
```$ git tag -l <wildcard pattern>``` Tags that match wildcard pattern  
NOTE: Annotated tags are stored in full, lightweights are not.
Annotated tags are considered best practice, whereas lightweights should only be used for temporary purposes.  
```$ git tag -a <tag-name> -m "<message>"``` Create annotated tag  
```-s``` Allows to sign the tag  
```$git show <tag-name>``` Check the tag data along with the commit that was tagged  
```$git tag -a <tag-name> -m "<message>" <commit-hash>``` Add tag to commit-hash  
