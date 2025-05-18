# Navigation

First, we have to find out in which directory we are using `pwd`. The list command is needed to list all the files in the directory, with `-l` the command will display more information.

Here is some information that `-l` displays:

| Column Content     | Description                                               |
|--------------------|-----------------------------------------------------------|
| drwxr-xr-x         | Type and permissions                                      |
| 2                  | Number of hard links to the file/directory                |
| cry0l1t3           | Owner of the file/directory                               |
| htbacademy         | Group owner of the file/directory                         |
| 4096               | Size of the file or number of blocks used for directory   |
| Nov 13 17:37       | Date and time                                             |
| Desktop            | Directory name                                            |

However, we will not see everything that is in this folder. A directory can also have hidden files that start with a dot at the beginning of its name (e.g., .bashrc or .bash_history). Therefore, we need to use the command `ls -la` to list all files of a directory.

To list the contents of a directory, we do not necessarily need to navigate there first. We can also use “ls” to specify the path where we want to know the contents.

`ls -l /var/`

To move trought the directories we can use `cd` and enter the full path to jump there. If we type [TAB] twice to a `cd /dev/s` it will autocomplete the input searching directories with s.

