index.html is the simple website
commitCheck.py file contains the python code to check for new commits in the git and updates a json file with commit time and a boolean value for new commit . Example {"lastCommitTime": "2023-11-25 07:21:07", "newCommit": true}
The script.sh contains the script that runs the python script to check for new commits and if there is a new commit, copy the repo and restart the nginx server.
We can automate the execution of the above script file using cronjob


Create a EC2 t3 micro instance on aws
do sudo apt-get update
do sudo apt-get install nginx (to start nginx)
sudo systemctl status nginx(check if nginx started or not and check for errors)
and copy the commitCheck.py and script.sh file in writer123456/cicd repo to the instance. And once you copy Keep only the index.html file in this repo  and remove both commitCheck.py and script.sh files (it would make work easy) 
need to clone this github repository writer123456/cicd on to your local system,make some changes to the index.html file, commit and push.
setup the cronjob by editing cronjob file using command
crontab -e and typing following in it
*/5 * * * * ./script.sh  in cronjob file
execute command grep 'script.sh' /var/log/syslog to check if cronjob is automated or not
Copy the public ip addess onto browser and check the website for your latest changes that you pushed recently.
