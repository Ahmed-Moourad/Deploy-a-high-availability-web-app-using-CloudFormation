# Deploy a high-availability web app using CloudFormation

> _This my solution to the second project in Udacity Advanced Cloud DevOps nanodegree_

> **Disclaimer**: Don't just copy and paste from here to pass your project, this will fail successfully due to plagiarism :) 
>  **✨INSTEAD** you can use it to compare your work and find the error that can't make your application available.

## Project description:
In this project, I have deployed web servers for a highly available web app using CloudFormation. I wrote the code that creates and deploys the infrastructure and application for a simple app from the ground up. I began with deploying the networking components, followed by servers, security roles and software.

## Project diagram:
![This digram shows the project Architecture](https://user-images.githubusercontent.com/112473376/210959777-a60fed33-431d-4ca4-bb57-1e4d9203b87e.png)


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

![The output section in CloudFormation Consolet](https://user-images.githubusercontent.com/112473376/210959928-f86cf640-2f66-43d1-b714-33c4a9275f93.JPG)

After you click the link you should see a simple website like this:

<img width="578" alt="simple html website" src="https://user-images.githubusercontent.com/112473376/210960183-6e1ef2f3-7777-403b-86d3-5b61a5240d08.png">

## End

That's it from me, I hope this was helpful, and I wish you the best of luck during your learning journey.


**~~NOT~~ Free to edit, Hell Yeah!**
