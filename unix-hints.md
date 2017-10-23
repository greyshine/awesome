# Unix-Hints

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

##stream stderr to stdout

````
2>&1
````



### stream to DEV0

````
$> echo nada > /dev/null
````





# Uptime and Serverload

````
$> uptime
+13:28  up  1:10, 2 users, load averages: 1,57 1,65 1,79
````

The *uptime* utility displays the current time, the length of time the system has been up, the number of users, and the load average of the system over the last 1, 5, and 15 minutes.



## basedir of executing script

Echos the current directory.

````
BASEDIR=$(dirname "$0")
echo $BASEDIR
````



## Timestamp

timestamp=$(date +"%Y%m%d%H%M%S")

timestamp=$(date +"%Y-%m-%d_%H:%M:%S")

_Date parsing and formatting: [http://www.computerhope.com/](http://www.computerhope.com/unix/udate.htm)[unix](http://www.computerhope.com/unix/udate.htm)[/udate.htm](http://www.computerhope.com/unix/udate.htm)_



## String handling

### Substring begin to; e.g. extract text until first space

````
sed 's/\s.*$//'
grep -o '^\S*'
awk '{print $1}'
````

_https://unix.stackexchange.com/a/98985/191027_





## from my Evernote cheatsheet

_everything from here on until the end of the document is intended to be refactored into nice sections above this one…_



pass on all arguments in script

for example: java -cp thejar.jar some.Main $*

$# - Anzahl der Argumente

Load average:

\> uptime



find

```
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

Redirect Error Stream

- stderr2stdout
   someCommand 2>&1
- stderr2dev0
   someCommand 2> /dev/null
- stdout2dev0
   someCommand 1> /dev/null
- stdout,stderr2dev0
   someCommand 1> /dev/null 2> /dev/null

basically redirecting:

- err to dev0
   2>/dev/null
- 2>&1

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

