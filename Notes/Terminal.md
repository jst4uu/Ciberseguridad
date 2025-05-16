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

Customizing the prompt can be useful to make better your experience!!

## Getting help

Sometimes, we will find some parameters we dont know from memory or we never seen before

But we can ask for help with the next command:

`{name}htb[/htb]$ ls`

It's a list of files and directories

`{name}htb[/htb]$ man <tool>`

Gives detailed information about tools

Or we can use

`{name}htb[/htb]$ <tool> --help`

`{name}htb[/htb]$ ls --help`

some tools or commands like __curl__ gives short version of help using **-h**

`{name}htb[/htb]$ <tool> -h`

**Apropos** This tool searches descriptions for instances of a keyword

`jst4uu@htb[/htb]$ apropos sudo`

# System Information

Useful commands about system:

| Command   | Description                                                                                  |
|-----------|----------------------------------------------------------------------------------------------|
| `whoami`  | Displays current username.                                                                   |
| `id`      | Returns user's identity.                                                                     |
| `hostname`| Sets or prints the name of the current host system.                                          |
| `uname`   | Prints basic information about the operating system name and system hardware.                |
| `pwd`     | Returns working directory name.                                                              |
| `ifconfig`| Used to assign or view an address to a network interface and/or configure interface parameters. |
| `ip`      | Utility to show or manipulate routing, network devices, interfaces and tunnels.              |
| `netstat` | Shows network status.                                                                         |
| `ss`      | Another utility to investigate sockets.                                                       |
| `ps`      | Shows process status.                                                                         |
| `who`     | Displays who is logged in.                                                                    |
| `env`     | Prints environment or sets and executes command.                                              |
| `lsblk`   | Lists block devices.                                                                          |
| `lsusb`   | Lists USB devices.                                                                            |
| `lsof`    | Lists opened files.                                                                           |
| `lspci`   | Lists PCI devices.                                                                            |

# SSH

It's an protocol that allows remote access to linux hosts and servers, it doesn't requires a GUI

To connect to our target we use:

`{name}htb[/htb]$ ssh htb-student@[IP-address]`

## Hostname

Shows the name of the computer we are logged in

## Whoami

This quick and easy command can be used on both Windows and Linux systems to get our current username. During a security assessment, we obtain reverse shell access on a host, and one of the first bits of situational awareness we should do is figuring out what user we are running as. From there, we can figure out if the user has any special privileges/access. **id** expands the whoami command.

## uname

If we type **man uname** it will bring us the page with the possible options we can run the command.

But if we type `uname -a` will print information in a specific order like, hostname, linux kernel, version etc, the flag **-a** will omit **-p** (processor type) and **-i** (hardware platform) if they are unknow.

With **-r** we will see kernel release, with this info we can search exploits about the kernel
