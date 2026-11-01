## 1.1 Find things

```bash
sudo find /var/log -type f  \( -size +1M -o -mtime -1 \)
```

- `sudo`: its a command with you can access to root privileges, its needed because for example the /var/log directory is not accesable with regular users
- `find`: with find  you can find files in a specific directory and it's subdictionaries
- `-type`: with type you can specify that you looking for a file or a directory, -type f is regular file, -type d is directory
- `-mtime`: with mtime you can specify the time of the modification of the file which you are looking for, for example -1 means less tha  24 hours ago, -mtime 1 means between 24 and 48 hours ago. -mtime +1 more than  48 hours ago and so on
- `-size`: with size you can specify what file size are you looking for, for example wit -1M you search for file below 1MB size, with +1M you search for files with above 1MB file size, sizes are rounded up to whole with MB, you can also specify the sizes in KB like -1024k becasue -1M only matches empty files only because its rounds up the size 
- `-o`: -o is an OR operator with you can connect file searchs with sepcific statment in to one command logically, you can use paranthesis to include statements together like this:
sudo find /var/log -type f \( -size +1M -o -mtime -1 \), the backslahes are needed to unlock the paranthesis, because without backslash the bash shell will belive that the paranthesis are bash commands and will drop an error
- `-newermt`: with newermt you can specify the modification time with text rather than numbers with -mtime wich uses numbers witch are 24 hours blocks for example -1 is less 24 hours ago, -mtime 1 is between 24 and 48 hours ago, +1 is more than 48 hours ago, with newermt you can specify the modification time like this: "24 hours ago", "yesterday", "2026-11-01 14:30"
̣̣̣




