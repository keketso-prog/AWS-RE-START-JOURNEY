Linux Basics

What is Linux?

Linux is an operating system, just like Windows or macOS, but it's free and open-source.
Think of it like this: If Windows is like buying a pre-built house, Linux is like getting the blueprint to build your own house exactly how you want it.
Why it matters for AWS:

Most cloud servers run Linux
It's lightweight and fast
Free to use (no licensing costs)
Very stable and secure

Common Linux distributions:

Ubuntu (most beginner-friendly)
Amazon Linux (AWS's own version, optimized for EC2)
Red Hat / CentOS
Debian


Linux Commands
Linux uses a command line interface (CLI). Here are the essential commands you'll use daily:
Navigation Commands
pwd - Print Working Directory (where am I?)
bashpwd
# Output: /home/user
ls - List files and folders
bashls           # Show files
ls -l        # Show detailed list
ls -a        # Show hidden files too
cd - Change Directory (move around)
bashcd /home           # Go to /home folder
cd ..              # Go up one level
cd ~               # Go to home directory
File Commands
cat - Display file contents
bashcat myfile.txt     # Show what's in the file
cp - Copy files
bashcp file1.txt file2.txt        # Copy file1 to file2
cp file.txt /home/backup/     # Copy to another folder
mv - Move or rename files
bashmv oldname.txt newname.txt    # Rename
mv file.txt /home/docs/       # Move to another folder
rm - Remove (delete) files
bashrm file.txt        # Delete a file
rm -r folder/      # Delete a folder and everything in it
mkdir - Make Directory (create folder)
bashmkdir myfolder     # Create new folder
System Commands
sudo - Super User Do (run command as admin)
bashsudo apt update    # Run update as administrator
chmod - Change file permissions
bashchmod +x script.sh    # Make file executable
chmod 755 file.txt    # Set specific permissions
ps - Show running processes
bashps aux             # Show all processes
top - Live view of system resources
bashtop                # See CPU, memory usage in real-time

Editing Files
There are several text editors in Linux. Here are the most common:
Nano (Easiest for Beginners)
Opening a file:
bashnano myfile.txt
Basic controls:

Type normally to edit
Ctrl + O - Save file
Ctrl + X - Exit
Ctrl + K - Cut line
Ctrl + U - Paste

Vi/Vim (More Powerful)
Opening a file:
bashvi myfile.txt
Basic controls:

Press i - Enter INSERT mode (start typing)
Press Esc - Exit INSERT mode
Type :w - Save
Type :q - Quit
Type :wq - Save and quit
Type :q! - Quit without saving

Tip: Vim has a learning curve, but it's worth learning for speed and power.

Working with Files
Viewing Files
head - Show first 10 lines
bashhead myfile.txt
head -n 5 myfile.txt    # Show first 5 lines
tail - Show last 10 lines
bashtail myfile.txt
tail -f myfile.txt      # Follow file (watch new lines added)
less - View file page by page
bashless myfile.txt
# Use arrow keys to scroll, 'q' to quit
Searching Files
grep - Search for text in files
bashgrep "error" logfile.txt           # Find "error" in file
grep -r "error" /var/logs/         # Search all files in folder
grep -i "error" file.txt           # Case-insensitive search
find - Find files
bashfind . -name "*.txt"               # Find all .txt files
find /home -name "config"          # Find files named "config"
File Permissions
Files have three permission types:

r (read) - Can view the file
w (write) - Can edit the file
x (execute) - Can run the file

Check permissions:
bashls -l myfile.txt
# Output: -rw-r--r-- 1 user group 1234 Nov 10 myfile.txt
Change permissions:
bashchmod 755 script.sh    # Owner: read/write/execute, Others: read/execute
chmod +x script.sh     # Make executable

Bash Shell Scripting
Bash scripts are text files containing commands that run automatically.
Creating a Simple Script
1. Create the file:
bashnano myscript.sh
2. Add commands:
bash#!/bin/bash
# This is a comment

echo "Hello, World!"
echo "Today is:"
date
3. Make it executable:
bashchmod +x myscript.sh
4. Run it:
bash./myscript.sh
Common Scripting Elements
Variables:
bashNAME="John"
echo "Hello, $NAME"
If statements:
bashif [ -f "myfile.txt" ]; then
    echo "File exists"
else
    echo "File not found"
fi
Loops:
bashfor file in *.txt; do
    echo "Processing $file"
done
Real example - Backup script:
bash#!/bin/bash
# Simple backup script

BACKUP_DIR="/home/backups"
DATE=$(date +%Y-%m-%d)

mkdir -p $BACKUP_DIR
cp -r /home/documents $BACKUP_DIR/docs-$DATE
echo "Backup completed: docs-$DATE"

Managing Log Files
Logs are files that record what's happening on your system. They're essential for troubleshooting.
Common Log Locations
System logs:

/var/log/syslog - General system logs
/var/log/auth.log - Authentication logs (who logged in)
/var/log/kern.log - Kernel logs

Application logs:

/var/log/apache2/ - Web server logs
/var/log/mysql/ - Database logs

Viewing Logs
View entire log:
bashcat /var/log/syslog
View last 50 lines:
bashtail -n 50 /var/log/syslog
Watch log in real-time:
bashtail -f /var/log/syslog
Search logs for errors:
bashgrep "error" /var/log/syslog
grep -i "failed" /var/log/auth.log    # Case-insensitive
Log Management Commands
Check log file size:
bashls -lh /var/log/syslog
Compress old logs:
bashgzip /var/log/oldlog.log    # Creates oldlog.log.gz
View compressed logs:
bashzcat oldlog.log.gz
Clear a log file:
bashsudo truncate -s 0 /var/log/syslog    # Empties the file
AWS CloudWatch Logs
In AWS, you'll often use CloudWatch to manage logs instead of manually checking files.
What it does:

Collects logs from EC2 instances automatically
Searchable and filterable
Set up alerts for specific errors
No manual log file management
