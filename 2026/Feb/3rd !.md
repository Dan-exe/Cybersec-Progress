 Day One: Setting up Kali on a VM and getting into tryHackMe
I already have some experience with Kali and did some HackTheBox etc. in my past.
Just need to get back into it and become more fluent in vim and linux terminal.

Linux Basic Commands:

    - find -name ***   
        -name specifies file name
        -to find all files with same extension
         use *.ext
    - grep "***" filename
        -to find things in a file via ***
        -'-r' will search recursively thru every
         file in the directory and all subdirectories

    Operators:
    - '&' allows you to run commands in the background of
     your terminal
    - '&&' allows you to combine multiple commands together
    - '>' redirect so send output to some specified file
    - '>>' does the same as '>' but appends rather than 
      overwrites

GoBuster: 
command line tool to take a list of potential page or directory
names. Exploits unprotected data on a web servers file system. 
Even possible to find hidden vhosts such as development sites or
admin portals.

- Super noisy, and can be easily detected but the amount of threads
  used can be reduced as to make a bit more quiet.

- Useful DIR Commands
- '-h' for general list of modes 
- '-u' the target url string
- '-w' path to the wordlist
- '-t' amount of threads (default 10)
- '--delay' delay between each ROUND of req so if -t 10 --delay 1, then
  10 requests every second.
- '-n' excludes status codes (extra noise not always valuable)
- '-x' file extensions to search for

Example usage:
gobuster -u http://fakebank.thm -w wordlist.txt dir
