# Description
This module uses a malformed packet or timing attack to enumerate users on an OpenSSH server. The default action sends a malformed (corrupted) SSH_MSG_USERAUTH_REQUEST packet using public key authentication (must be enabled) to enumerate users. On some versions of OpenSSH under some configurations, OpenSSH will return a "permission denied" error for an invalid user faster than for a valid user, creating an opportunity for a timing attack to enumerate users. Testing note: invalid users were logged, while valid users were not. YMMV.

# Usage
```
$ cd ssh_enumerator 
$ chmod +x time_based_enum.py 
$ ./time_based_enum.py -w [wordlist]
```
