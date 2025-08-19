# chef-node-check
This script does the following:
Key Features:

Runs knife status to get node information
Parses the output to identify nodes that haven't checked in for more than 3 hours
SSHs to those nodes as vagrant@<server> with interactive password support
Runs chef-client on each overdue node
Creates timestamped logs in /var/log/chef-updates/

Usage:

Make the script executable: chmod +x chef-update-script.sh
Run it: ./chef-update-script.sh

Notes:

The script assumes knife status output includes server information that can be parsed
SSH connection uses standard timeout and host checking options
All output is logged with timestamps
The script handles different time formats from knife status (hours, minutes, seconds)
Interactive password prompts will work when you run the script

Customization:

Change THRESHOLD_HOURS=3 to adjust the time threshold
Modify LOG_DIR to change where logs are stored
Adjust SSH options in the ssh command if needed

The script will prompt for passwords when connecting to each server, and all chef-client output will be captured in the log file.