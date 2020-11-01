---
layout: post
title: "Windows Tips and Tricks"
subtitle: "useful commands and tricks to use in Windows"
categories: coding
tags: windows
comments: true
---

# Windows Commands
Here is a handy [list](https://www.ionos.com/digitalguide/server/know-how/windows-cmd-commands/) of DOS commands.

## Basics

| CMD command | Description | Version |
|-----|------|------|
| call | Calls a batch file within another batch file. The command has no effect if entered directly into CMD instead of in a batch file. | All |
| cd (chdir) | Displays the current directory and lets you switch to other directories. With the parameter /D plus drive and path specification, you can also switch drives. Use cd.. to switch to a higher directory (has the same function as the chdir command).| All |
| cls | Clears the content of the screen. | All |
| date | Displays the current date and allows you to change it. With the parameter /T the date is shown without the option to change. | All |
| dir | Displays all folders and files within the current directory. You can restrict the output by attributes (/A), simplify the list (/B), or display all subdirectories and their files (/S). | All |
| echo | Displays a message and is mainly used within scripts and batch files. | All |
| find | Searches through a file or multiple files for a particular character sequence. If you only want to know how frequently the word or phrase occurs, use the /C parameter. With the extension /I the command ignores upper- and lower-case in the search. | All |
| findstr | Finds character sequences in one or multiple files. It gives you more options when compared to the find command: you can search for files that contain various terms or with /C search for an exact word order. | 10/8/7/Vista/XP |
| md (mkdir) | Creates a new directory on the specified path. If directories don’t already exist on the path, md creates them automatically (you can also use the mkdir command). | All |
| more | Outputs the content of a file (for example, a text file) by the page. You can also use the command to split the output of another command into pages. | All |
| path | Creates and displays the path for searching executable files. | All |
| pause | Pauses execution in batch files and scripts. The user is then prompted in a message to continue by pressing a key. | All |
| popd | Changes to the folder saved by the pushd command. The command is mainly part of batch files and scripts. | All |
| pushd | Saves a specific path into a script or batch file. You can change to this directory with popd. | All |
| rd (rmdir) | Deletes a directory. This must not contain any files, even hidden ones. You can delete an entire directory tree with the /S parameter (you can also use the rmdir command). | All |
| rem | Writes comments in batch and script files that aren’t taken into account when executing. | All |
| runas | Allows a user to run commands with the rights of another user. For example, you can run a command as an administrator from a normal user account as long as you know the password. | All |
| set | Displays environmental variables of CMD.EXE and lets you configure them. | All |
| shift | Moves variables within batch files and scripts. | All |
| shutdown | Shuts down the computer (/s), triggers a restart (/r), or logs the user out (/l). A graphical user interface is displayed if you enter the parameter /I as the first option in the command. | 10/8/7/Vista/XP |
| start | Opens a new command prompt window in which you can run a specific program or command. | All |
| taskkill | Ends one or more running tasks. You either have to specify the process ID (PID) or image name. | 10/8/7/Vista |
| tasklist | Lists all running processes – also on remote computers, if desired. The process ID also has to be specified, which is required for the taskkill command, for example. | 10/8/7/Vista/XP |
| time | Displays the current time and allows it to be changed. If the parameter /T is entered, the command prompt only shows the time and offers no option to directly change it. | All |
| tree | Graphically displays the directory structure of a drive or path. With the /F parameter, all files in the folders are also listed out. /A also ensures that only ASCII characters are used for the graphical representation. The command takes into account all subdirectories starting from the given path. If you don’t enter a path, the current folder is used as the output. | All |
| type | Displays the content of a text file. | All |
| ver | Displays the current version number of Windows or MS-DOS. | All |

## Files
| CMD command | Description | Version |
| ----- | ------ | ------ |
| copy | Copies a file or multiple files to another location. It’s also possible to connect several files to one. You can use the asterisk as a wild card. | All |
| del (erase) | Deletes a file or multiple files. If you also want to delete all files from subfolders, you can do this with the /S parameter. Read-only files can be deleted with /F (you can also use the erase command).| All |
| for | Sets a specific command that should be run for each individual file in a file set. This command is usually used in batch and script files. | All |
| forfiles | Selects one or more files and runs a command that refers to these files. Usually used for batch and script files. | 10/8/7/Vista |
| goto | Skips the execution within a batch program to a specific line (marker). | All |


## Batch Files

### [FOR cmd](https://ss64.com/nt/for_cmd.html)

```markdown
Syntax
      FOR /F ["options"] %%parameter IN ('command_to_process') DO command

Key
   options:
      delims=xxx   The delimiter character(s)
                   (default = a space or TAB)
      skip=n       A number of lines to skip at the beginning. 
                   (default = 0)

      eol=;        Character at the start of each line to indicate a comment
                   The default is a semicolon ;

      tokens=n     The numbered items to  read from each line 
                   (default = 1)

      usebackq     Use the alternate quoting style:                        
                   - Use double quotes for long file names in "filenameset".
                   - Use single quotes for 'Text string to process'
                   - Use back quotes for `command_to_process`

  command_to_process : The output of the 'command_to_process' is 
                        passed into the FOR parameter.

   command    :   The command to carry out, including any parameters.
                  This can be a single command, or if you enclose it
                  in (brackets), several commands, one per line.

  %%parameter :  A replaceable parameter:
                 in a batch file use %%G (on the command line %G)
```

## To parse a csv file
Create sample1.csv file with the following content:
```markdown
0,1,2,4
1,1,2,3
2,2,4,6
3,3,6,9
```
```markdown
for /f "usebackq tokens=1-4 delims=," %%a in ("sample1.csv") do (
      echo %%a %%b %%c %%d )
```


### [FORFILES](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/forfiles)


```markdown
@echo off
IF "%1" == "" goto :HELP

forfiles /P %1 /M "*.*" /c "cmd /C echo video2images: @path & mkdir @fname & ffmpeg -i @path -start_number 0 -b:v 10000k -an -y -q:v 16 -r %2 @fname\%%4d.jpg"

echo DONE
goto :EOF

:HELP
echo video2images.bat [input folder] [fps]
echo 	video2images.bat C:\test 0.01

:EOF
```

# Windows Tools
These builtin windows tools can be run by pressing Windows key and type the name of the program.

## winver
 To check Windows version

## dxdiag
 To see detailed info about DirectX components including the graphics driver.
  
# Additional tools
## SysInternal Tools
[Windows SysInternals](https://docs.microsoft.com/en-us/sysinternals/downloads/sysinternals-suite)
 is a collection of useful utilities for Windows. The most useful is probably ZoomIt which is a very handy tool for presentations.
 * [ZoomIt](https://docs.microsoft.com/en-us/sysinternals/downloads/zoomit)
