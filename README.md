yum-scheduledupdate
===================

Automatic YUM updates, but on a schedule with custom notification list.

Testing
=======
[jason@dethklok yum-scheduledupdate]$ ./bin/yum-scheduledupdate --config-file=/home/jason/sandbox/yum-scheduledupdate/etc/sysconfig/yum-scheduledupdate --debug --check-update --dry-run

Test configuration:
[jason@dethklok yum-scheduledupdate]$ cat etc/sysconfig/yum-scheduledupdate 
[main]
# MAILLIST
#   This is a comma deliminated list
#   Example:  MAILLIST=root,me@mydomain.com,you@yourdomain.org
MAILLIST=root

# MAXWAITTIME
#   yum-autoupdate waits for a random time before starting
#   This setting sets the maximum time in minutes.
#   Set to 0 for no waiting
MAXWAITTIME=0

# CONFIGFILE
#   Change this if you want to use a different yum.conf file.
CONFIGFILE=/etc/yum.conf

# EXCLUDE
#   This is a space deliminated list
#   Example:  EXCLUDE=kernel* openafs* *-kmdl-* kmod-* *firmware*
EXCLUDE=kernel* openafs* *-kmdl-* kmod-* *firmware*

# DEBUG
#     true - turn on debug mode - be more verbose
#     false - Do not run in debug mode (default)
#   + anything other than true defaults to false
DEBUG=false
