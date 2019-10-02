# easymail
Send email from shell scripts or the command line

# Purpose
To send email from shell scripts or command line without needing to install an MTA such as exim or postfix. All you need to do is adjust the user variables at the top of the script, put the script somewhere in your PATH, and make it executable.

# Usage
Run the script without any arguments for syntax and example usage.

# Dependencies
- GNU/Linux with coreutils: curl
- GNU/Linux with busybox: curl and openssl
- OpenBSD: curl and coreutils

# BusyBox gotcha
BusyBox recently changed the syntax of its *timeout* applet. Run *busybox timeout --help* to check the syntax for your version of BusyBox. If your version does not take the *-t* flag, please delete those two characters from the *get_stdin* function.

# Note about CA ssl certificates
If they are missing on your system (which is not advisable), you can still use this script. Just add *--insecure* to the curl command in the *send_eml_file* function.
