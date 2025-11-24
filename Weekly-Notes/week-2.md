# Week 2: Linux Basics

## What is Linux?

Linux is an operating system, just like Windows or macOS, but it's **free and open-source**. Think of it like this: If Windows is like buying a pre-built house, Linux is like getting the blueprint to build your own house exactly how you want it.

### Why it matters for AWS:
- Most cloud servers run Linux
- It's lightweight and fast  
- Free to use (no licensing costs)
- Very stable and secure

### Common Distributions:
- **Ubuntu** - Most beginner-friendly
- **Amazon Linux** - AWS's own version (optimized for EC2)
- **Red Hat/CentOS** - Enterprise focused  
- **Debian** - Very stable

## Command Line Basics

**Terminal/Shell:** The black screen where you type commands

### Essential Commands:
bash
pwd          # Print Working Directory (where am I?)
ls           # List files and folders
cd           # Change directory  
clear        # Clean your screen
exit         # Close terminal
### Shortcuts:
- **↑** → Previous command
- **Tab** → Auto-complete  
- **Ctrl+C** → Stop running command
- **Ctrl+L** → Clear screen

## Working with Files & Folders

### File Operations:
bash
touch filename.txt           # Create file
cp source.txt dest.txt      # Copy file  
mv old.txt new.txt          # Move/Rename
rm filename.txt             # Delete file 
cat filename.txt            # View file content

### Folder Operations:

bash
mkdir foldername            # Create folder
rmdir foldername           # Delete empty folder
rm -r foldername           # Delete folder & contents  
ls -la                     # List all files with details

 **Be careful with rm:** There's no undo in Linux! Always double-check before deleting.

## Editing Files

### Text Editors:
| Editor | Difficulty | Notes |
|--------|------------|-------|
| **nano** | Easy | Ctrl+X to exit |
| **vim** | Hard | Press i to insert, :wq to save & quit |
| **gedit** | Easy | GUI editor (if you have desktop) |

**Example:** `nano myfile.txt`

## File Permissions

### Permission Types:
- **r** → Read (can view)
- **w** → Write (can edit)
- **x** → Execute (can run as program)

### Who Gets Permissions:
- **Owner** → The person who created it
- **Group** → Team members  
- **Others** → Everyone else

### Common Commands:

bash
ls -l                       # View permissions (shows like: -rwxr-xr--)
chmod 755 filename          # Change permissions
chown username filename     # Change owner


## Managing Processes

**Process:** A running program

### View Processes:
bash
ps                         # Show current processes
top                        # Live view of processes  
jobs                       # Show background jobs

### Control Processes:

bash
kill PID                   # Stop process
kill -9 PID                # Force kill 
command &                  # Run in background
## Managing Services

**Service:** Programs that run in background (like web server, database)

### systemctl Commands:

bash
systemctl start service     # Start service
systemctl stop service     # Stop service
systemctl restart service  # Restart service
systemctl status service   # Check if running
systemctl enable service   # Auto-start on boot
systemctl disable service  # Don't auto-start

## Software Management

**Package:** Software you install

### Ubuntu/Debian (apt):

bash
sudo apt install package            # Install software
sudo apt update && sudo apt upgrade # Update system
sudo apt remove package             # Remove software
### RedHat/CentOS (yum):
bash
sudo yum install package    # Install software
sudo yum update            # Update system  
sudo yum remove package    # Remove software

## Bash Scripting Basics

**Script:** A file with multiple commands

### Creating a Script:
bash
1. nano script.sh           # Create file
2. #!/bin/bash             # First line (shebang)
3. echo "Hello World"      # Add commands
4. chmod +x script.sh      # Make executable
5. ./script.sh             # Run script

### Variables & Special Characters:
bash
# Variables
NAME="John"
echo $NAME

# Special Characters
|    # Pipe (send output to next command)
>    # Redirect output to file  
*    # Wildcard (all files)

## Week 2 Key Takeaways 

- Linux is free, secure, and runs most cloud servers  
- Command line is powerful once you learn the basics  
- File permissions control who can access what  
- Processes are running programs you can manage  
- Services run in background (web servers, databases)  
- Package managers install software easily  
- Bash scripts automate repetitive tasks  
- Amazon Linux is optimized for AWS EC2  

### Personal Note:
The command line felt intimidating at first, but once I learned the basic commands, it became incredibly powerful. Being able to manage files, processes, and services from just text commands is amazing - no wonder most servers don't even have a GUI!
