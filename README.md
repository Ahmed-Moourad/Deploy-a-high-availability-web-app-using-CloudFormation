# Deploy a high-availability web app using CloudFormation

> _This my solution to the second project in Udacity Advanced Cloud DevOps nanodegree_

> **Disclaimer**: Don't just copy and paste from here to pass your project, this will fail successfully due to plagiarism :) 
>  **✨INSTEAD** you can use it to compare your work and find the error that can't make your application available.

## Project description:
In this project, I have deployed web servers for a highly available web app using CloudFormation. I wrote the code that creates and deploys the infrastructure and application for a simple app from the ground up. I began with deploying the networking components, followed by servers, security roles and software.

## Project diagram:
![this digram shows the project Architecture]
(https://drive.google.com/file/d/1Lk0ki6sjARQ7hqbMtPhDdWSHK9WN6ODo/view?usp=sharing)



## Project files:

 1. project-infra.yml :
> This file creates the network infrastructure of your app next:
			- One VPC
			- Two Public Subnet
			- Two Private Subnet with All suitable RouteTables for each
			- One Internetgatway
			- Two NAT for High Availability

2. project-infra-parm.json :
> This file contains the needed prarmeters to run the first file, make sure you put your parameters.

3. project-servers.yml :
>This file Deploy the servers for our Application as Next:
			- One Application LoadBalancer.
			- Four Webservers, two Webserver/Private Subnet using Launch Configuration.
			- One Bastion host to SSH to our servers and troubleshoot any problems.
			- The Security groups for the LoadBalancer and Webserver.
			- IAM Role that allows your Webservers to deal with S3 buckets to get the code which uploaded by the developers.

4. project-servers-parm.json :
> This file contains the needed prarmeters to run the third file, make sure you put your parameters.

5. create .sh:
>This script contains the create-stack command and can help you to run CloudFormation faster:
```sh
aws cloudformation create-stack --stack-name $1 --template-body file://$2 --parameters file://$3 --capabilities "CAPABILITY_IAM"  "CAPABILITY_NAMED_IAM" --region=us-east-1
```

6. update .sh:
> This script contains the update-stack command and can help you to run CloudFormation faster:
```sh
aws cloudformation update-stack --stack-name $1 --template-body file://$2 --parameters file://$3 --capabilities "CAPABILITY_IAM"  "CAPABILITY_NAMED_IAM" --region=us-east-1
```

## After you run the templates:

You will get the URL of your application in the Output section in CloudFormation console.

EX:
![The output section in CloudFormation Console](https://drive.google.com/file/d/1EG9XOWG2wWAqAOUePXywksvH16eSeA9S/view?usp=sharing)

After you click the link you should see a simple website like this:
![simple html website](https://drive.google.com/file/d/1q1VGEhR-sKkPknKqHKFGCJEy0JKfhjL0/view?usp=sharing)

## End

That's all from me, I hope this was helpful, and I wish you the best of luck during your learning journey.


**~~NOT~~ Free to edit, Hell Yeah!**
