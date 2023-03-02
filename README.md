# cybr-file
input1=$1
version=1.0
argCount=$#
dirName=$2

if [ $argCount -gt 2 ] then
    echo " Invalid Arguments .."
    echo " example: ./rpsm.sh (options) (directory)"
else
    if [ $input1 == "-v" ] then
        echo "Version = $version"
    elif [ $input1 == "-h" ] then
        echo "-h Print this message"
        echo "-v Print script version information"
        echo "-u Find and list all files with setuid set, all owners"
        echo "-g Find and list all files with setgid set, all owners"
        echo "-w Find and list all files that are world-writable"
        echo "-b Find and list all files whose size is at least 10M"
        echo "-d Report directory disk usage"
        echo "-i Report information about filesystem"
        echo "-a All of the above (except -h and -v)"
    elif [ $input1 == "-u" ] then
        ls -ld $dirName
    elif [ $input1 == "-d" ] then
        du -d 1 $dirName

    elif [ $input1 == "-b" ] then
        find $dirName -size +10M -exec ls -lh {} \;
    elif [ $input1 == "-w" ] then
        find $dirName -type f -maxdepth 1 -writable
    elif [ $input1 == "-i" ] then
        df $dirName
    elif [ $input == "-id" ] then
        df $dirName

        du -d 1 $dirName

    elif [ $input1 == "-u" ] then
        ls -lu

    elif [ $input1 == "-g" ] then
        ls -g

    elif [ $input1 == "-a" ] then
        ls -ld $dirName
        du -d 1 $dirName

        df $dirName
        find $dirName -size +10M -exec ls -lh {} \;
        find $dirName -type f -maxdepth 1 -writable

    fi
fi
