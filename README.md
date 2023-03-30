# node-todo-cicd

In this Repo, I will try to dockerize a sample Node JS-todo Application using Dockerfile, create a docker image and run a container based on that docker image and also will push that docker Image to Amazon Elastic Conatiner Registry(E.C.R) for scanning the vulnerabilities.

Prerequisites:

-> An AWS account with EC2 and ECR access.

Step 1:

1. First Find a sample NodeJS app source code available on opensource or you can fork this repo and use this.

2. After Writing/Finding a Sample Node JS application, Try to run it locally on your laptop by installing Node and npm by using following commands.

`sudo apt install nodejs`

`sudo apt install npm`

`npm install`

`node app.js`

3. You can also skip the second step if you want to use docker.

Step 2:

1. Create an EC2 Virtual machine of any type like Ubuntu, CentOS.. and Install docker on it using suitable commands.

