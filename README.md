index.html is the simple website
commitCheck.py file contains the python code to check for new commits in the git
The script.sh contains the script that runs the python script to check for new commits and if there is a new commit, it would copy the repo and restart the nginx server.
We can automate the execution of the above script file using cronjob
