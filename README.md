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

Step 2: Setting Up the EC2 Instance

1. Create an EC2 Virtual machine of any type like Ubuntu, CentOS.. and Install Git and Docker on it using suitable commands like yum or apt-get based on your type of EC2 instance.

2. After installation, Clone this repo using the following command. 

`git clone https://github.com/AnilKumar-Noolu/NodeJS-todo-app.git`

3. After the repo is cloned, type `ls` command to view the Repo that is downloaded locally on your EC2 machine.

Step 3: Dockerizing the NodeJS Application

1. Create your Dockerfile for the above NodeJS Appliocation. In Dockerfile, we are exposing this NodeJS todo application on Port: 8000.

![Screenshot-16](https://user-images.githubusercontent.com/98457309/228907635-11697f26-9d44-405d-a764-ae04e5b5737a.png) 

2. Now build this Dockerfile using the build command.

`docker build -t nodejs-todo .`

3. On Successfully building this Dockerfile, you can view the images created successfully using the command.
`docker images`

![Screenshot-17](https://user-images.githubusercontent.com/98457309/228908081-751b0bea-6a75-4950-99e0-577a37cc87e0.png)

4. Once, you verified that the image is successfully created, Now create a Container to run the application using the following command.

`docker run -d -p 8000:8000 nodejs-todo:latest`

5. Here, we are exposing our NodeJS Application to the Outside World using 8000 Port. Enter the docker ps to know the status of the running Container.

![Screenshot-18](https://user-images.githubusercontent.com/98457309/228909896-9155d9eb-2e8e-46dc-92e2-aa3d1df106ea.png)

6. Now Check the browser by pasting the <Public_IP_address:8080> You can see that the application is running on your Browser.

![Screenshot-19](https://user-images.githubusercontent.com/98457309/228914759-344b80ba-c5a3-412b-b01c-3f58dec7f8cb.png)

Step 4: Pushing the Image to DockerHub

1. Now Since the Container is running fine, we can store the Docker Image to Repository and can use it when we really need it. For that we can use DockerHub, Amazon ECR, Jfrog Artifactory etc..

2. Now, we will see how we will push that image to DockerHub.

3. Firstly create an account in DockerHub using email and Password.

4. Login to the DockerHub inside your instance using username and password with following command.

`docker login`

![Screenshot-20](https://user-images.githubusercontent.com/98457309/228916533-3842a2c0-2921-48cc-bf08-227512fe838a.png)

5. Then you need to Tag that image first before pushing it to the DockerHub. Tag that Image using the following command.

`docker tag nodejs-todo:latest <your_dockerhub_username>/nodejs-todo:latest`

![Screenshot-21](https://user-images.githubusercontent.com/98457309/228917190-6cccee76-cfec-402d-bafd-f8582443ccd9.png)

6. Once the tagging is done, Then Push it to the DockerHub Using the following command:

`docker push <your_dockerhub_username>/nodejs-todo:latest`

![Screenshot-22](https://user-images.githubusercontent.com/98457309/228917324-3d9f7d3d-bdf9-4eaf-a57f-56131d192452.png

7. After few seconds, you can see that the Image you tagged is successfully pushed to your DockerHub Account.

![Screenshot-23](https://user-images.githubusercontent.com/98457309/228917571-906f01c5-95e0-4913-a298-725e76d7f9c2.png)





 

