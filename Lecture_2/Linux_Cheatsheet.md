# Essential Linux Commands for DevOps Professionals

This guide provides a cheat sheet of 50+ essential Linux commands with explanations and examples, aiming to help DevOps professionals improve their Linux skills for server management, automation, and troubleshooting.

| **Command** | **Description** | **Example** |
|-------------|-----------------|-------------|
| id          | Find out user and group names and numeric ID’s (UID or group ID) of the current user or any other user in the server. | `id -u root` |
| cd          | Change Directory: Navigate to a different directory. | `cd /home/user/documents` |
| pwd         | Print Working Directory: Display the current directory's full path. | `pwd` |
| mkdir       | Make Directory: Create a new directory. | `mkdir new_folder` |
| rm          | Remove: Delete files or directories. | `rm file.txt` |
| cp          | Copy: Copy files or directories. | `cp file.txt /backup` |
| mv          | Move: Move files or directories. | `mv file.txt /new_location` |
| touch       | Create Empty File: Create a new empty file. | `touch new_file.txt` |
| cat         | Concatenate and Display: View the content of a file. | `cat file.txt` |
| nano        | Text Editor: Open a text file for editing. | `nano file.txt` |
| grep        | Search Text: Search for text patterns in files. | `grep "pattern" file.txt` |
| find        | Search Files and Directories: Search for files and directories. | `find /path/to/search -name "file_name"` |
| chmod       | Change File Permissions: Modify file permissions. | `chmod 755 file.sh` |
| chown       | Change Ownership: Change the owner and group of a file or directory. | `chown user:group file.txt` |
| ps          | Process Status: Display running processes. | `ps aux` |
| top         | Monitor System Activity: Monitor system processes in real-time. | `top` |
| kill        | Terminate Processes: Terminate a process using its ID. | `kill PID` |
| wget        | Download Files: Download files from the internet. | `wget https://example.com/file.zip` |
| curl        | Transfer Data with URLs: Transfer data to or from a server. | `curl -O https://example.com/file.txt` |
| tar         | Archive and Extract: Create or extract compressed archive files. | `tar -czvf archive.tar.gz folder` |
| ssh         | Secure Shell: Connect to a remote server securely. | `ssh user@remote_host` |
| scp         | Securely Copy Files: Copy files between local and remote systems using SSH. | `scp file.txt user@remote_host:/path` |
| rsync       | Remote Sync: Synchronize files and directories between systems. | `rsync -avz local_folder/ user@remote_host:remote_folder/` |
| df          | Disk Free Space: Display disk space usage. | `df -h` |
| du          | Disk Usage: Show the size of files and directories. | `du -sh /path/to/directory` |
| ifconfig    | Network Configuration: Display or configure network interfaces (deprecated, use ip). | `ifconfig` |
| ip          | IP Configuration: Manage IP addresses and network settings. | `ip addr show` |
| netstat     | Network Statistics: Display network connections and statistics (deprecated, use ss). | `netstat -tuln` |
| systemctl   | System Control: Manage system services using systemd. | `systemctl start service_name` |
| journalctl  | Systemd Journal: View system logs using systemd's journal. | `journalctl -u service_name` |
| free        | Displays the total amount of free space available. | `free -m` |
| at          | Execute Commands Later: Run commands at a specified time. | `echo "command" | at 15:30` |
| ping        | Network Connectivity: Check network connectivity to a host. | `ping google.com` |
| traceroute  | Trace Route: Trace the route packets take to reach a host. | `traceroute google.com` |
| curl        | Check Website Connectivity: Check if a website is up. | `curl -Is https://example.com | head -n 1` |
| dig         | Domain Information Groper: Retrieve DNS information for a domain. | `dig example.com` |
| hostname    | Display or Set Hostname: Display or change the system's hostname. | `hostname` |
| who         | Display Users: Display currently logged-in users. | `who` |
| useradd     | Add User: Create a new user account. | `useradd newuser` |
| usermod     | Modify User: Modify user account properties. | `usermod -aG groupname username` |
| passwd      | Change Password: Change user password. | `passwd username` |
| sudo        | Superuser Do: Execute commands as the superuser. | `sudo command` |
| lsof        | List Open Files: List open files and processes using them. | `lsof -i :port` |
| nc          | Netcat: Networking utility to read and write data across network connections. | `echo "Hello" | nc host port` |
| scp         | Secure Copy Between Hosts: Copy files securely between hosts. | `scp file.txt user@remote_host:/path` |
| sed         | Stream Editor: Text manipulation using regex. | `sed 's/old/new/g' file.txt` |
| awk         | Text Processing: Pattern scanning and text processing. | `awk '{print $2}' file.txt` |
| cut         | Text Column Extraction: Extract specific columns from text. | `cut -d"," -f2 file.csv` |
| sort        | Sort Lines: Sort lines of text files. | `sort file.txt` |
| diff        | File Comparison: Compare two files and show differences. | `diff file1.txt file2.txt` |
| ls          | List Files and Directories: List the contents of a directory. | `ls -la` |
| history     | View the previously executed command. | `history 10` |
| cron        | Schedule Tasks: Manage scheduled tasks. | `crontab -e` |
| ssh-keygen  | Generate a public/private authentication key pair for SSH. | `ssh-keygen` |
| nslookup    | Name server Lookup: Check DNS hostname to IP or IP to hostname. | `nslookup google.com` |
| tr          | Translate or delete characters. | `cat crazy.txt | tr "[a-z]" "[A-Z]"` |
| tnc         | Test Network Connection: Displays diagnostic information for a connection. | `tnc google.com --port 443` |
| w           | Displays current user. | `w` |
| su          | Switch User. | `su - root` |
| ac          | Total connect time for all users or specified users. | `ac john` |


