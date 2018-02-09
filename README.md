Assignment 1: Deploying webserver
Current results are in results.md

The purpose of the assignment is to familiarize you with the automatic build, containers, and cloud computing

The due date is Feb 9 after class.
Create repo yougithubid/webserver

Add Dockerfile, for example as the one in this repo

Add index.html with your name in it

Create automatic build

i. on hub.docker.com reate id for yourself (if you have not done so before)
ii. create automated build (pull out from the top menu)
iii. connect to github repo you have just created
make a change on the github repo (to trigger build)

Verify that the build succeeded https://hub.docker.com/r/yourdockerhubid/webserver/builds/

Create a virual machine on GCP

i. go to https://console.cloud.google.com/compute/instances select the class project and click on craete instance
ii. Next to memory click customize and reduce 1G
iii. Mark checkmark "Deploy a container image to this VM" and enter image 'yourgithubid/webserver'
iv. Mark checkmark "Allow HTTP traffic"
v. expand "Management, disks, networking, SSH keys"
vi. in the "startup script" box enter    
#!/bin/bash
docker rm ws
docker run -d --name ws -p80:80 yourghid/webserver
Click "Create" button at the bottom

Check if the webserver works

  i. enter the external ip adress (for the machine you created) in your browser (you should get your name)
  ii. If that does not work connect to the machine
  iii. Open shell
  iv. type gcloud compute ssh "your instance name"
  v. once connected to your instance type 'docker ps': your container should be running
Enter ip adress of the machine at the bottom of your netid.md file in the cocs340/students repo and create a pull request
