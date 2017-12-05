# Unix-Hints

## find - _my friend which I never can remember_

````find <folder> [options] <test> <action>````

e.g.: ````find / -name "*.xml"```` find all xmls beginning from root folder and list only.

## See version of OS

````$> lsb_release -a````

## Install Oracle Java8

1. Follow:  
  https://wiki.ubuntuusers.de/Java/Installation/Oracle_Java/Java_8/
2. Since the `sudo update-alternatives ...` seem not work straight out of the box check this:  
  https://stackoverflow.com/a/9082947/845117
  `apt-get install libc6-i386`

HowTo: https://gist.github.com/greyshine/bae891fb14a4ee45767f2af8e75422de


## Streams

````
0 stdin

1 stdout

2 stderr

/dev/null 
````

_further readings: [https://unix.stackexchange.com/a/70971/191027](https://unix.stackexchange.com/a/70971/191027)_

###stream stderr to stdout

````2>&1````
### stream to DEV0

````$> echo nada > /dev/null````


## Uptime and Serverload

````
$> uptime
+13:28  up  1:10, 2 users, load averages: 1,57 1,65 1,79
````

The *uptime* utility displays the current time, the length of time the system has been up, the number of users, and the load average of the system over the last 1, 5, and 15 minutes.


## basedir of executing script

Echos the current directory.

````shell
BASEDIR=$(dirname "$0")
echo $BASEDIR
````



## Timestamp

````timestamp=$(date +"%Y%m%d%H%M%S")````

````timestamp=$(date +"%Y-%m-%d_%H:%M:%S")````

_Date parsing and formatting: [http://www.computerhope.com/](http://www.computerhope.com/unix/udate.htm)[unix](http://www.computerhope.com/unix/udate.htm)[/udate.htm](http://www.computerhope.com/unix/udate.htm)_



## Execute command and continue even if it failed

````shell
cd /notexisting ||:
echo still running
````

the ````||:```` successfully executes the left part or the right part. since _something OR true_ result in _true_ it will always continue.

WATCH: only writing ````|:```` pipes the previous command into the ````: ```` command.

## String handling

### Substring begin to; e.g. extract text until first space

````shell
sed 's/\s.*$//'
grep -o '^\S*'
awk '{print $1}'
````

_https://unix.stackexchange.com/a/98985/191027_



## The $-argument group

$# - Anzahl der Argumente

````shell
#!/bin/sh
echo This is all of the arguments with any number: $*
echo This is the amount of passed arguments: $#
echo This is the first argument: $1
echo This is the file name of this executing script: $0
echo This is the directory name of the file name of this executing script: $(dirname $0)
echo This shows the last exit status: $?
echo some background executed echoing to nirvana > /dev/null &
echo This shows the process id of the last background started process: $!
````



### Check if a specific argument is given

example taken from: https://stackoverflow.com/a/28263100/845117

````shell
for i in "$@" ; do
    if [[ $i == "value1" ]] ; then
        echo "value 1 is set!"
        # break
    fi
done
````



### Check if e.g. $1 argument exist

https://askubuntu.com/a/444089/608206

````shell
if [ ! -z "$1" ] ; then
	echo \$1 is given
fi

if [ -z "$1" ] ; then
	echo \$1 is missing
fi

````





## ln -s // Symlinking

````shell
ln -s {/path/to/file-name} {link-name}
````



## directory of current executing script

````shell
THIS_DIR=$(dirname $0)
````



## Regenerating a public key from id_rsa

https://stackoverflow.com/a/38924652/845117
````shell
ssh-keygen -y -f ~/.ssh/id_rsa > ~/.ssh/id_rsa.pub
````
O-Ton: The -y option is the command teling ssh-keygen to output your public key.

## from my Evernote cheatsheet

_everything from here on until the end of the document is intended to be refactored into nice sections above this one…_

\> uptime



find

```shell
find Startverzeichnis [Optionen] Test Aktion
```

find / -name "*.xml"

Siehe https://de.wikipedia.org/wiki/Find

​     

IF

OR

if [[ ${trackErrors} -gt 0  || ${count} -eq 0 ]]

then...

oder

if [ ${trackErrors} -gt 0 -o ${count} -eq 0 ]

AND

if [ "$data2" != "world" ] && [ "$data1" != "hello" ]

then

negate IF

if [ ! -e $somefile ]

then

​     # if somefile does not exist then...

Symlinks

Symbolic link:

ln -s {/path/to/file-name} {link-name}

hard links can only reference files, no directories.

hard links cannot cross reference over mounted drives

Write call result into variable

var=$(echo hallo)

echo $var

echoes hallo

read file into variable

var=$(cat <file>)

crontab

<http://www.adminschoice.com/crontab-quick-reference>

Add .htaccess user

Substring / cut

$> echo hallo | cut -c 2-4

\> all

For each file in dir do...:

[http://www.cyberciti.biz/faq/](http://www.cyberciti.biz/faq/unix-loop-through-files-in-a-directory/)[unix](http://www.cyberciti.biz/faq/unix-loop-through-files-in-a-directory/)[-loop-through-files-in-a-directory/](http://www.cyberciti.biz/faq/unix-loop-through-files-in-a-directory/)

File test operators

are you a folder, are you a file?

<http://tldp.org/LDP/abs/html/fto.html>





