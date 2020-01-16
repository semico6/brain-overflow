# When you screw up your /etc/sudoers file:
1. Open two ssh sessions to the target server.
2. In the first session, get the PID of bash by running:
   echo $$
3. In the second session, start the authentication agent with:
   pkttyagent --process (pid from step 2)
4. Back in the first session, run:
   pkexec visudo
5. In the second session, you will get the password prompt. visudo will start in the first session.

Source: https://askubuntu.com/questions/799669/etc-sudoers-file-corrupted-and-i-cant-run-pkexec-visudo-over-ssh?newreg=738961109f804005b8f7188bbcdf98f3
