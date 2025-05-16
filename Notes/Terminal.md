# Terminal Basics

## Bash Prompt

The prompt is a message that tells you:

- Who you are (username).
- Your computer's name.
- The directory/file you are currently working.

This appears in a new line and the cursor is on the right side waiting for you to write a new command. It can be customized to show more useful information to the user. It can look like this:

`<username>@<hostname><current working directory>$`

The home directory for users is marked by a tilde <~> and is the default folder when we log in.

`<username>@<hostname>[~]$`

The dollar signs stands for a user, but when we change to root , it turns to a #

`root@htb[/htb]#`

When we run a shell in the target system, we may not see the directory, hostname, and its because the variable ps1 is not being set correctly, we should see something like:

`$` (unprivileged user root)
`#` (privileged user root)

The ps1 variable in Linux controls how your command prompt looks in the terminal and defines if your system is ready to be used, and you can customize it, adding more  useful information like your IP, date, time, and the sucess or failure of the last command, changing, or even adding colors or special characters.

This can helps with penetration tests, tracking our your actions more effectively, you can set the prompt to show the full path of the current working directory instead of just its name, and even include the target's IP address if needed. Using tools like script or reviewing the .bash_history file (located in the user's home directory), you can record all the commands you've used and organize them by date and time, which aids in documentation and analysis.

The prompt can be customized using special characters and variables in the shell’s configuration file (.bashrc for the Bash shell). For example, we can use: the \u character to represent the current username, \h for the hostname, and \w for the current working directory.

|Special character|Description                        |
|-----------------|-----------------------------------|
|\d               |Date (May 15)                      |
|\D {%Y %m %d}    |(YYYY - MM - DD)                   |
|\H               |Full Hostname                      |
|\j               |Number of jobs charged in the shell|
|\n               |New line                           |
|\r	              |Carriage return                    |
|\s               |Name of the shell                  |
|\t               |	Current time 24-hour (HH:MM:SS)   |
|\T	              |Current time 12-hour (HH:MM:SS)    |
|\@	              |Current time                       | 
|\u	              |Current username                   |
|\w               |Full path of the current working directory|
