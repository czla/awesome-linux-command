# Linux command line
For Chinese version, click [中文版](README.md)  

## Content 
* [1.Shell](#1shell)
* [2.File system](#2file-system)
* [3.Help command](#3help-command)
* [4.I/O redirection](#4io-redirection)
* [5.Shortcuts](#5shortcuts)
* [6.Process](#6process)
* [7.Vim](#7vim)
* [8.Packaging system](#8packaging-system)
* [9.Find files](#9find-files)
* [10.Compress files](#10compress-files)
* [11.Regular Expression](#11regular-expression)
* [12.Manipulating text](#12manipulating-text)
* [13.conda](#13conda)

### 1.Shell  
Command | Description  
:-: | :-  
`Up` `Down`| view command history   
date | display the current time and date  
cal | display a calendar of the current month  
df | see the current amount of free space on your disk drives  
free | display the amount of free memory  
exit | end a terminal session   
`Ctrl-Alt-[F1-F6]` | open virtual terminals  
`Alt-F7` | return to the graphical desktop
printenv | Print part or all of the environment
set | Set shell options
export | Export environment to subsequently executed programs

[Back to Content](#content)

### 2.File system
Command | Description  
:-: | :-  
pwd | Print name of current working directory  
ls | List directory contents  
cd | Change directory(-Last directory ~Home directory)  
file | determine a file’s type  
less | view text files  
cp | Copy files and directories  
mv | Move/rename files and directories  
mkdir | Create directories  
rm | Remove files and directories  
ln | Create hard and symbolic links  
du -h --max-depth=1 | Show directory size under current directory

* Common ls Options  

Option | Long Option | Description  
:-: | :-: | :-  
-a | --all | List all files, including hidden files  
-d | --directory | list the contents of the directory, not the directory itself  
-F | --classify | append an indicator character to the end of each listed name. For example, a '/' if the name is a directory.  
-h | --human-readable | display file sizes in human readable format rather than in bytes  
-l |  | Display results in long format  
-r | --reverse | Display the results in reverse order. Normally, ls display its results in ascending alphabetical order  
-S |  | Sort results by file size  
-t |  | Sort by modification time  

* Wildcards  

Wildcard | Meaning  
:-: | :-  
\* | Matches any characters  
? | Matches any single character  
\[characters\] | Matches any character that is a member of the set characters
\[!characters\] | Matches any character that is not a member of the set characters
\[\[:class:\]\] | Matches any character that is a member of the specified class

* Commonly Used Character Classes

Character Class | Meaning  
:-: | :-:  
\[:alnum:\] | Matches any alphanumeric character
\[:alpha:\] | Matches any alphabetic character
\[:digit:\] | Matches any numeral
\[:lower:\] | Matches any lowercase letter
\[:upper:\] | Matches any uppercase letter

* cp Options

Option | Meaning  
:-: | :-  
-a, --archive | Copy the files and directories and all of their attributes, including ownerships and permissions
-i, --interactive | Before overwriting an existing file, prompt the user for confirmation
-r, --recursive | Recursively copy directories and their contents
-u, --update | only copy files that either don't exist, or are newer than the existing corresponding files, in the destination directory
-v, --verbose | Display informative messages as the copy is performed

* mv Option includes \[-i，-u，-v\];rm Option includes \[-i，-r，-v，-f\];its meaning is similar to that in cp

[Back to Content](#content)

### 3.Help command

Command | Description
:-: | :-
type | Indicate how a command name is interpreted
which | Display which executable program will be executed
man | Display a command’s manual page
apropos | Display a list of appropriate commands
info | Display a command’s info entry
whatis | Display a very brief description of a command
alias | Create an alias for a command

[Back to Content](#content)

### 4.I/O redirection

Command | Description
:-: | :-
\> | redirect standard output to another file (cover)
\>\> | redirect standard output to another file(append)
2\> | redirect standard errors to another file，standard input/output/errors are representated by file descriptor number 0/1/2 respectively
2\>&1 or &\> | redirect standard output and errors to another file
tee | print to standard output(terminal) and file simultaneously
cat | copies file to standard output
sort | Sort lines of text
unique | Report or omit repeated lines
wc | Print newline, word, and byte counts for each file
grep | Print lines matching a pattern，option -i ignore lowercase/capitalization
head | Output the first part of a file，option -n to appoint line numbers
tail | Output the last part of a file，option -n to appoint line numbers

[Back to Content](#content)

### 5.Shortcuts

* Cursor Movement

Key | Action
:-: | :-
`Ctrl`-`a` | Move cursor to the beginning of the line
`Ctrl`-`e` | Move cursor to the end of the line
`Ctrl`-`f`  | Move cursor forward one character;same as the right arrow key
`Ctrl`-`b` | Move cursor backward one character;same as the left arrow key
`Alt`-`f`  | Move cursor forward one word
`Alt`-`b`  | Move cursor backward one word
`Ctrl`-`l` | Clear the screen and move the cursor to the top left corner. The clear command does the same thing

* Text Editing

Key | Action
:-: | :-
`Ctrl`-`d` | Delete the character at the cursor location
`Ctrl`-`t` | Transpose(exchange)the character at the cursor location with the one preceding it
`Alt`-`t`  | Transpose the word at the cursor location with the one preceding it
`Alt`-`l`  | Convert the characters from the cursor location to the end of the word to lowercase
`Alt`-`u`  | Convert the characters from the cursor location to the end of the word to uppercase

* Cut And Paste

Key | Action
:-: | :-
`Ctrl`-`k` | Kill text from the cursor location to the end of line
`Ctrl`-`u` | Kill text from the cursor location to the beginning of the line
`Alt`-`d`  | Kill text from the cursor location to the end of the current word
`Alt`-`Backspace`  | Kill text from the cursor location to the beginning of the word. If the cursor is at the beginning of a word, kill the previous word
`Ctrl`-`y` | Yank text from the kill-ring and insert it at the cursor location

* Auto-completion

Key | Action
:-: | :-
`Alt`-`?`  | Display list of possible completions，equals pressing the tab key a second time
`Alt`-`*`  | Insert all possible completions

* History

Key | Action
:-: | :-
`Ctrl`-`p` | Move to the previous history entry. Same action as the up arrow
`Ctrl`-`n` | Move to the next history entry. Same action as the down arrow
`Alt`-`<`  | Move to the beginning (top) of the history list
`Alt`-`>`  | Move to the end (bottom) of the history list, i.e., the current command line
`Ctrl`-`r` | Reverse incremental search. Searches incrementally from the current command line up the history list
`Alt`-`p`  | Reverse search, non-incremental. With this key, type in the search string and press enter before the search is performed
`Alt`-`n`  | Forward search, non-incremental
`Ctrl`-`o` | Execute the current item in the history list and advance to the next one

[Back to Content](#content)


### 6.Process

Command | Description
:-: | :-
ps | Report a snapshot of current processes
top | Display tasks
jobs | List active jobs
bg | Place a job in the background
fg | Place a job in the foreground
kill | Send a signal to a process
killall | Kill processes by name
shutdown | Shutdown or reboot the system

[Back to Content](#content)
### 7.Vim

For more detail information, please click [Vim Totorial](Vim_en.md)

[Back to Content](#content)
### 8.Packaging system

* Major Packaging System Families

Packaging System | Distributions (Partial Listing)
:-: | :-
Debian Style (.deb) | Debian, Ubuntu, Xandros, Linspire
Red Hat Style (.rpm) | Fedora, CentOS, Red Hat Enterprise Linux, OpenSUSE, Mandriva, PCLinuxOS

* Packaging System Tools

Distributions | Low-Level Tools | High-Level Tools
:-: | :-: | :-
Debian-Style | dpkg | apt-get, aptitude
Fedora, Red Hat Enterprise Linux, CentOS | rpm | yum

* Package Search Commands

Style | Command(s)
:-: | :-
Debian | apt-get update; apt-cache search search_string
Red Hat | yum search search_string

* Package Installation Commands

Style | Command(s)
:-: | :-
Debian | apt-get update; apt-get install package_name
Red Hat | yum install package_name

* Low-Level Package Installation Commands

Style | Command(s)
:-: | :-
Debian | dpkg --install package_file
Red Hat | rpm -i package_file

* Package Removal Commands

Style | Command(s)
:-: | :-
Debian | apt-get remove package_name
Red Hat | yum erase package_name

* Package Update Commands

Style | Command(s)
:-: | :-
Debian | apt-get update; apt-get upgrade
Red Hat | yum update

* Low-Level Package Upgrade Commands

Style | Command(s)
:-: | :-
Debian | dpkg --install package_file
Red Hat | rpm -U package_file

* Package Listing Commands

Style | Command(s)
:-: | :-
Debian | dpkg --list
Red Hat | rpm -qa

* Package Status Commands

Style | Command(s)
:-: | :-
Debian | dpkg --status package_name
Red Hat | rpm -q package_name

* Package Information Commands

Style | Command(s)
:-: | :-
Debian | apt-cache show package_name
Red Hat | yum info package_name

* Package File Identification Commands

Style | Command(s)
:-: | :-
Debian | dpkg --search file_name
Red Hat | rpm -qf file_name

[Back to Content](#content)

### 9.Find files

Command | Description
:-: | :-
locate | Find files by name
updatedb | update database

* find file types

File Type | Description
:-: | :-
b | Block special device file
c | Character special device file
d | Directory
f | Regular file
l | Symbolic link

* find size units

Character | Unit
:-: | :-
b | 512 byte blocks. This is the default if no unit is specified
c | Bytes
w | Two byte words
k | Kilobytes (Units of 1024 bytes)
M | Megabytes (Units of 1048576 bytes)
G | Gigabytes (Units of 1073741824 bytes)

* find tests

Test | Description
:-: | :-
-cnewer file | Match files or directories whose contents or attributes were last modified more recently than those of file
-ctime n | Match files or directories whose contents or attributes were last modified n*24 hours ago
-empty | Match empty files and directories
-iname pattern | Like the -name test but case insensitive
-mmin n | Match files or directories whose contents were modified n minutes ago
-mtime n | Match files or directories whose contents were modified n*24 hours ago
-name pattern | Match files and directories with the specified wild card pattern
-newer file | Match files and directories whose contents were modified more recently than the specified file
-size (+/-) n | Match files (larger/smaller) than size n
-type c | Match files of type c

* find logical operators

Operator | Description
:-: | :-
-and | Match if the tests on both sides of the operator are true. May be shortened to -a. Note that when no operator is present, -and is implied by default
-or | Match if a test on either side of the operator is true. May be shortened to -o
-not | Match if the test following the operator is false. May be abbreviated with an exclamation point (!)
() | Groups tests and operators together to form larger expressions. This is used to control the precedence of the logical evaluations。 

* Predefined find Actions

Action | Description
:-: | :-
-delete | Delete the currently matching file
-ls | Perform the equivalent of ls -dils on the matching file. Output is sent to standard output
-print | Output the full pathname of the matching file to standard output. Default action
-quit | Quit once a match has been made

* for example

Command | Description
:-: | :-
`find ~ -type d \| wc -l` | search directories in `Home` and count lines
`find ~ -type f -name "*.JPG" -size +1M \| wc -l` | look for all the regular files that match the wild card pattern “*.JPG” and are larger than one megabyte
`find ~ -type f -name '*.BAK' -delete` | delete files that have the file extension “.BAK”

[Back to Content](#content)

### 10.Compress files
* gzip: compress/uncompress one or more files. It will replace the original file
    * gzip Options

    Option | Description
    :--: | :--:
    -c  | Write output to standard output and keep original files. May also be specified with --stdout and --to-stdout
    -d  | Decompress. This causes gzip to act like gunzip. May also be specified with --decompress or --uncompress
    -f  | Force compression even if compressed version of the original file already exists. May also be specified with --force
    -h  | Display usage information. May also be specified with --help
    -l  | List compression statistics for each file compressed. May also be specified with --list
    -r  | If one or more arguments on the command line are directories, recursively compress files contained within them. May also be specified with --recursive
    -t  | Test the integrity of a compressed file. May also be specified with --test
    -v  | Display verbose messages while compressing. May also be specified with --verbose
    -number | Set amount of compression. number is an integer in the range of 1 (fastest, least compression) to 9 (slowest, most compression). The values 1 and 9 may also be expressed as --fast and --best, respectively. The default value is 6

* bzip2: similar to gzip, achieves higher levels of compression at the cost of compression speed，extension .bz2
* zip: common compression tool for windows，extension .zip
    * zip examples

    Command  | Description
    :--:  | :--:
    `zip -r myfile.zip ./*`  | Compress all the files and directories under the current directory to `myfile.zip`
    `zip -d myfile.zip smart.txt`  | Delete `smart.txt` from `myfile.zip`
    `zip -m myfile.zip ./rpm_info.txt`  | Add `rpm_info.txt` to `myfile.zip`
    `unzip -o -d /home/sunny myfile.zip` | Uncompress `myfile.zip` to `/home/sunny/`,-o means override file without warning, -d specifies uncompress path

* tar: Archiving，short for tape archive，gathering up many files and bundling them together into a single large file, with extension .tar
    * tar Modes

    Mode  | Description
    :--:  | :--:
    -c     |  Create a new archive
    -x     |  Extract an archive
    -r     |  Append specified pathnames to the end of an archive
    -t     |  List the contents of an archive，can choose 1 from these 4 mode
    -v     |  Report file informations during processing
    -f     |  Specify archive name，must be set as the last option
    
    * Examples

    Command  | Description
    :--:  | :--:
    `tar -cf all.tar *.jpg`  | Compress *.jpg to an archive named `all.tar`
    `tar -rf all.tar *.gif`  | Add *.gif to `all.tar`
    `tar -tf all.tar`        | List all files in `all.tar`
    `tar -xf all.tar`        | Uncompress all files in `all.tar`

* Conclusion

    Command  | Description
    :--:  | :--:
    `tar –xvf file.tar`  | Uncompress `file.tar`
    `tar -xzvf file.tar.gz` | Uncompress `tar.gz`
    `tar -xjvf file.tar.bz2` | Uncompress `tar.bz2`
    `tar –xZvf file.tar.Z`  | Uncompress `tar.Z`
    `unrar e file.rar`      | Uncompress `file.rar`
    `unzip file.zip`        | Uncompress `file.zip`
    `tar –cvf jpg.tar *.jpg` | Archive *.jpg to `jpg.tar`
    `tar –czf jpg.tar.gz *.jpg` | Archive *.jpg to `jpg.tar`，then compress it to `jpg.tar.gz` using gzip
    `tar –cjf jpg.tar.bz2 *.jpg` | Archive *.jpg to `jpg.tar`，then compress it to `jpg.tar.bz2` using bzip2
    `tar –cZf jpg.tar.Z *.jpg`  | Archive *.jpg to `jpg.tar`，then compress it to `jpg.tar.Z` using compress
    `rar a jpg.rar *.jpg`   | Compress *.jpg to `jpg.rar`
    `zip jpg.zip *.jpg`     | Compress *.jpg to `jpg.zip`

[Back to Content](#content)

### 11.Regular Expression
* grep: **g**lobal **r**egular **e**xpression **p**rint
    
    Option | Description
    :--: | :--:
    -i  | Ignore case, may also be specified by `--ignore-case`
    -v  | Invert match, may also be specified by `--invert-match`
    -c  | Print the number of matches (or non-matches if the -v option is also specified), may also be specified by `--count`
    -l  | Print the name of each file that contains a match instead of the lines themselves, may also be specified by `--files-with-matches`
    -L  | Like the -l option, but print only the names of files that do not contain matches, may also be specified by `--files-without-matches`
    -n  | Prefix each matching line with the number of the line within the file,  may also be specified by `--line-number`
    -h  | For multi-file searches, suppress the output of filenames, may also be specified by `--no-filename`

* Metacharacter

    Character | Description
    :--: | :--:
    `.` | Match any character in that character position
    `^` | Matching at the beginning of the line
    `$` | Matching at the end of the line
    `[]`| Match a single character from a specified set of characters


    * metacharacters lose their special meaning when placed within brackets except the following two:

        Character | Description
        :--: | :--:
        `-` | Indicate a character range
        `^` | Indicate negation if it is the first character within a bracket expression
        
* **E**xtended **R**egular **E**xpressions (ERE): `egrep` or `grep -E`add following metacharacters:

    Character | Description
    :--: | :--:
    `\|` | Alternation, allows a match to occur from among a set of expressions
    `()` | Separate the alternation
    `?` | Limitation, indicate that they are to be matched zero or one time
    `*` | Limitation, indicate that they are to be matched zero or any times
    `+` | Limitation, indicate that they are to be matched one or more times
    `{}`| Limitation, express minimum and maximum numbers of required matches

    * Specifying The Number Of Matches

    Specifier  | Meaning
    :--:    | :--:
    `{n}`   | Match the preceding element if it occurs exactly n times
    `{n,m}` | Match the preceding element if it occurs at least n times, but no more than m times
    `{n,}`  | Match the preceding element if it occurs n or more times
    `{,m}`  | Match the preceding element if it occurs no more than m times


* Examples
    
    Command  | Description
    :--:  | :--:
    `grep bzip dirlist*.txt`  | Searche all of the listed files for the string `bzip`
    `grep -h '.zip' dirlist*.txt` | Searche for any line in our files that matches the regular expression `.zip`
    `grep -h '^$' dirlist*.txt` | Match empty line
    `grep -i '^..j.r$' /usr/share/dict/words` | Search a five letter word whose third letter is `‘j’` and last letter is `‘r’`
    `grep -h '[bg]zip' dirlist*.txt` | Match any line contains `'bzip'` or `'gzip'`
    `grep -h '[^bg]zip' dirlist*.txt` | Match any line contains `'bzip'` or `'gzip'`, and the preceding letter of `'zip'` is neither `'b'` nor `'g'`
    `grep -h '^[A-Za-z0-9]' dirlist*.txt` |  Matches all filenames starting with letters and numbers
    `grep -h '[-AZ]' dirlist*.txt` | Match every filename containing a `dash`, or a upper case `'A'` or an uppercase `'Z'`
    `grep -Eh '^(bz\|gz\|zip)' dirlist*.txt` | Match the filenames in our lists that start with either `'bz'`, `'gz'`, or `'zip'`
    `grep -Eh '^bz\|gz\|zip' dirlist*.txt` | Match any filename that begins with `'bz'` or contains `'gz'` or contains `'zip'`
    `^\(?[0-9]\)?  [0-9]-[0-9]$` | Match `n n-n` or `(n) n-n`, `n` is a number

[Back to Content](#content)

### 12.Manipulating text
* **sort**: Sort lines of text files
    * Common sort Options

    Option | Long Option | Description
    :--:  | :--: | :--:
    `-b` | `--ignore-leading-blanks` | Ignore leading spaces in lines and calculates sorting based on the first non-whitespace character on the line
    `-f` | `--ignore-case`  | Makes sorting case insensitive
    `-n` | `--numeric-sort` | Performs sorting based on the numeric evaluation of a string
    `-r` | `--reverse`      | Sort in reverse order
    `-k` | `--key=field1[,field2]` | Sort based on a key field located from `field1` to `field2` rather than the entire line
    `-m` | `--merge`        | Merge multiple files into a single sorted result without performing any additional sorting
    `-o` | `--output=file`  | Send sorted output to file rather than standard output
    `-t` | `--field-separator=char` | Define the field separator character. By default fields are separated by spaces or tabs

* **uniq**: Removes duplicate lines which are adjacent to each other
    * Common uniq Options

        Option  |  Description
        :--:  |  :--:
        `-c` | Output a list of duplicate lines preceded by the number of times the line occurs
        `-d` | Only output repeated lines, rather than unique lines
        `-f n` | Ignore `n` leading fields in each line, and fields are separated by whitespace
        `-i` | Ignore case during the line comparisons
        `-s n` | Ignore the leading `n` characters of each line
        `-u` |  Only output unique lines. This is the default

* **tr**: Transliterate characters
    * `echo "lowercase letters" | tr a-z A-Z` outputs `LOWERCASE LETTERS`
    * `echo "lowercase letters" | tr [:lower:] A` outputs `AAAAAAAAA AAAAAAA`
    * `tr -d '\r' < dos_file > unix_file` converts `MS-DOS` text files to `Unix` style text

* **sed**: **s**tream **ed**itor
    * sed Address Notation

    Address | Description
    :--: | :--:
    `n` | A line number where `n` is a positive integer
    `$` | The last line
    `/regexp/` | Lines matching a POSIX basic regular expression
    `addr1,addr2` | A range of lines from `addr1` to `addr2`, inclusive. Addresses may be any of the single address forms above
    `first~step` | Match the line represented by the number `first`, then each subsequent line at `step` intervals
    `addr1,+n` | Match `addr1` and the following `n` lines
    `addr!` | Match all lines except `addr`, which may be any of the forms above

    * sed Basic Editing Commands
        
        Command | Description
        :--: | :--:
        `=` | Output current line number
        `a` | Append text after the current line
        `d` | Delete the current line
        `i` | Insert text in front of the current line
        `p` | Print the current line
        `q` | Exit `sed` without processing any more lines. If the `-n` option is not specified, output the current line.
        `Q` | Exit `sed` without processing any more lines
        `s/regexp/replacement/` | Substitute the contents of `replacement` wherever `regexp` is found, after the trailing slash following replacement, an optional flag may be specified to modify the s command’s behavior
    * Examples

    Command | Description
    :--: | :--:
    `echo "front" \| sed 's/front/back/'` | Replace `front` with `back`
    `echo "front" \| sed '2s/front/back/'` | Replace `front` with `back` in the second line, so output is still `front`
    `sed -n '1,5p' distros.txt` | **Print** a range of lines, starting with line one and continuing to line five
    `/etc/passwd \| sed '/root/p'` | Search lines contain `root` in `/etc/passwd`
    `/etc/passwd \| sed  '/root/d'` | Delete lines contain `root` in `/etc/passwd` and print other lines
    `sed -i 's/\.$/\!/g' regular_express.txt` | Replace the last `.` of a line with `!` in `regular_express.txt`
    `sed -i '$a # This is a test' regular_express.txt` | Add `# This is a test` to the last line of `regular_express.txt`

[Back to Content](#content)

### 13.conda

For more detail information, please click [conda Totorial](conda-cheatsheet.pdf)

[Back to Content](#content)