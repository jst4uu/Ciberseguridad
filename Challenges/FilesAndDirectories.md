# Q&A

## Questions

1. What is the name of the last modified file in the "/var/backups" directory?
2. What is the inode number of the "shadow.bak" file in the "/var/backups" directory?

## Answers

1. I ubicate the directory with `cd`, then, I use `ls -la` to see all the files in the directory, dates etc, and there is the answer, `Nov 12 2020`.

2. In the same directory, I search "shadow.bak", when I find it, I type `ls -i shadow.bak`, there is the answer.