# cybr-file
You are asked to write a shell script named “rpsm.sh”. The script reports and prints (to stdout) selected storage management information.  Think of it as “RePort Storage Management”.

The easy way to describe what the script needs to do is to look at what it should display in the case where you provide incorrect parameters, or in the case where you provide “-h” for help:

Usage: ./rpsm.sh <options> <directory>
Reports selected information about specified directory tree.
Options:
-h Print this help message, i.e., “Usage: ./rpsm.sh … … (except -h and -v)”
-v Print script version information, i.e., 1.0
-u Find and list all files (just file names) with setuid set, all owners
-g Find and list all files (just file names) with setgid set, all owners
-w Find and list all files (just file names) that are world-writable
-b Find and list all files (just file names) whose size is at least 10M
-d Report directory disk usage
-i Report information about the file system
-a All of the above (except -h and -v)
