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

WEEK 2

📝 Week 2 - Linux Notes 🐧 Introduction to Linux

💻 Linux Command Lines

Terminal/Shell → The black screen where you type commands Basic commands:

pwd → Print Working Directory (where am I?) ls → List files and folders cd → Change directory (move to different folder) clear → Clean your screen exit → Close terminal

✏️ Editing Files

Text editors:

nano → Easy for beginners (Ctrl+X to exit) vim → Powerful but harder (press i to insert, :wq to save & quit) gedit → GUI editor (if you have desktop)

Example: nano myfile.txt opens the file to edit

📁 Working with Files

Create file: touch filename.txt 

Copy file: cp source.txt destination.txt 

Move/Rename: mv oldname.txt newname.txt 

Delete file: rm filename.txt ⚠️ (careful! no undo) 

View file: cat filename.txt (shows content) 

Create folder: mkdir foldername 

Delete folder: rmdir foldername (only empty folders) or rm -r foldername (deletes everything inside)

🔐 Managing File Permissions

Permission types:

r → Read (can view) w → Write (can edit) x → Execute (can run as program)

Who gets permissions:

Owner → The person who created it Group → Team members Others → Everyone else

View permissions: ls -l (shows like: -rwxr-xr--) Change permissions: chmod 755 filename or chmod +x script.sh Change owner: chown username filename

⚙️ Working with Commands

Get help: man command (manual) or command --help Command structure: command -options arguments Examples:

ls -la → List all files with details rm -rf folder → Force delete folder

History: history shows all previous commands Shortcuts:

↑ → Previous command Tab → Auto-complete Ctrl+C → Stop running command

🔄 Managing Processes

Process → A running program View processes: ps or top (live view) Kill process: kill PID (PID = process ID number) Force kill: kill -9 PID 💀 Background jobs: Add & at end → command & Foreground job: fg Check running: jobs

🎯 Managing Services

Service → Programs that run in background (like web server, database) Commands (systemd):

systemctl start servicename → Start service systemctl stop servicename → Stop service systemctl restart servicename → Restart service systemctl status servicename → Check if running systemctl enable servicename → Auto-start on boot systemctl disable servicename → Don't auto-start

🐚 Bash Shell

Bash → The default Linux command language Variables:

Create: NAME="John" Use: echo $NAME

Environment variables: echo $PATH, echo $HOME Special characters:

| → Pipe (send output to next command)

→ Redirect output to file

→ Append to file

→ Wildcard (all files)
📜 Bash Shell Scripting

Script → A file with multiple commands Create script:

nano script.sh First line: #!/bin/bash Add commands Save and exit

Make executable: chmod +x script.sh Run script: ./script.sh Basic scripting:

bash #!/bin/bash echo "Hello World" NAME="Linux" echo "Learning $NAME"

📦 Software Management

Package → Software you install Package managers:

Ubuntu/Debian: apt

Install: sudo apt install package Update: sudo apt update && sudo apt upgrade Remove: sudo apt remove package

RedHat/CentOS: yum or dnf

Install: sudo yum install package Update: sudo yum update

📋 Managing Log Files

Logs → Records of what happened in the system Location: /var/log/ Important logs:

/var/log/syslog → System messages /var/log/auth.log → Login attempts /var/log/dmesg → Boot messages

View logs:

cat /var/log/syslog → See all tail -f /var/log/syslog → Watch live updates head /var/log/syslog → See first lines

journalctl → Modern log viewer (systemd)

🚀 Advanced Bash Shell Scripting

Conditionals (if statements):

bash if [ $AGE -gt 18 ]; then echo "Adult"

AWS Linux AMIs Overview: https://docs.aws.amazon.com/linux/ EC2 User Guide for Linux: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/


