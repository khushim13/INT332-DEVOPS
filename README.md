# INT332-DEVOPS
This repository contains Docker concepts, commands and practical implementations.

1. Introduction to Docker

Docker is a containerization platform that allows developers to package applications with their dependencies and run them consistently across different environments.

3. Images :- Docker Image act as a set of instructions to build a docker container like a template or blueprint.

4. Conatainer :- A container is a lightweight isolated environment that contains:
- Application
- Dependencies
- Libraries

  Example:
Running a Node.js app inside a container.
Command:
docker run nginx

4. Daemon :- A program that executes in the background ready to perform an operation when required. When we use docker commands, we simply sending requests to the docker daemon to start, stop, build, delete a container.

5. Registry :- A place where images are stored is called registry. The default registry is called as docker hub.

6. Docker Hub :- It is just a website which contains bunch of premade images.

7. Docker Architecture
Docker has three main components:        
  -- Docker Client  
  -- Docker Daemon  
  -- Docker Registry (Docker Hub)

 Practical 1: Running Ubuntu Container

 Objective -- To run an Ubuntu container using Docker and execute commands inside it.
  <img width="949" height="306" alt="image" src="https://github.com/user-attachments/assets/e2b36198-9960-43f8-a048-21744fe7a0a8" />
  
  Explanation:
    - `-it` → interactive terminal
    - `ubuntu` → Docker image
    - `bash` → start bash shell inside container
    -'exit' → Exit from Container

  Practical 2: Pulling and Running Container

 Objective
 To download the Basic image from Docker Hub and run it as a container.
 
 1.1. Pull Nginx Image
   
   <img width="1287" height="472" alt="image" src="https://github.com/user-attachments/assets/b856365a-c9fd-4320-9374-b958456796f5" />

 1.2. Stop and Deleting the Container
   
   <img width="1249" height="484" alt="image" src="https://github.com/user-attachments/assets/2a3640b3-11fa-4ead-83b4-b1f953fd68cc" />
 
 2.1 Pull Apache Image
      
   <img width="1206" height="469" alt="image" src="https://github.com/user-attachments/assets/bee1918f-9eaf-40f7-a86d-bcf07fa1be6a" />
 
 2.2 Stop and Deleting the Container 
     
  <img width="1214" height="130" alt="image" src="https://github.com/user-attachments/assets/1d8d30bd-9bb7-421f-9ee1-a538ecf52b12" />

 3.1 Pulling Stop and Deleting ubuntu Image 
  
   <img width="1204" height="267" alt="image" src="https://github.com/user-attachments/assets/bef82fd6-14bf-486b-8d3a-f742c156f615" />
 
 4.1 Running MySQL Container
     Run MySQL container :
     docker run -d --name mysql_container -e MYSQL_ROOT_PASSWORD=root -p 3306:3306 mysql
     
Explanation:
  - `-d` → run container in background
  - `--name mysql_container` → container name
  - `MYSQL_ROOT_PASSWORD=root` → sets MySQL root password
  - `-p 3306:3306` → exposes MySQL port  
     
 4.2  Connect to MySQL : 
      docker exec -it mysql_container mysql -u root -p
      Password: root

Explanation:
      docker exec → logging into that server
      mysql → opening the database software inside that server
      -u root -p → logging into the database with admin credentials
     
   <img width="1227" height="453" alt="image" src="https://github.com/user-attachments/assets/cb671696-247d-4928-937c-5f1d6618eb3e" />
 
 4.3  Stop and Delete the Container
      
   <img width="1202" height="609" alt="image" src="https://github.com/user-attachments/assets/15e82953-bb92-437d-904c-d803a5a2cbb8" />

 5.1 Running Alpine Container in Docker
     
   Objective : To run a lightweight Alpine Linux container and execute basic commands inside it.   
   
   <img width="1053" height="293" alt="image" src="https://github.com/user-attachments/assets/fdabaf9b-c4d4-43d8-a405-940f5d20ba34" />
  
   <img width="1115" height="253" alt="image" src="https://github.com/user-attachments/assets/49fbdb1d-08d4-415f-8daf-61d728ba4735" />

 6. Image Registry and Distribution

     <img width="1265" height="473" alt="image" src="https://github.com/user-attachments/assets/f1df0811-5917-4e46-9568-a89b865dc480" />

     <img width="1280" height="430" alt="image" src="https://github.com/user-attachments/assets/a725ae55-1c35-48ab-89cd-28030931ec6d" />

 8. Executing Commands and Copying Files in a Docker

    Objective : To run a Docker container, execute commands inside it, and transfer files between the host system and the container.

    STEP 1 - Pull an image.

    STEP 2 - Run a Conatiner.

    STEP 3 - Check Running Container.

    STEP 4 - Execute Command Inside Container.

    STEP 5 - Open Container Terminal.

    STEP 6 - Create Folder.

    STEP 7 - Create File.

    <img width="1264" height="391" alt="image" src="https://github.com/user-attachments/assets/e582e795-224a-4aad-b970-c63a600bba9f" />

    <img width="1215" height="296" alt="image" src="https://github.com/user-attachments/assets/b8603fc1-f086-4d12-ae01-49d84eaefb5f" />

    STEP 8 - Exit.

    STEP 9 - Copy File from Container to Host.

    STEP 10 - Copy File from Host to Container.

    STEP 11 - Verify File.

    STEP 12 - Read File.

    <img width="1218" height="291" alt="image" src="https://github.com/user-attachments/assets/392ae8f7-0ebc-4d35-a815-25027df8e9ba" />

    Docker Volume
    
    A Docker Volume is a storage mechanism used to persist and manage data generated by Docker containers. It allows data to be stored outside
    the container on the host system, so the data remains safe even if the container is stopped or deleted.

    Practical: Creating and Managing Docker Volume
    
    STEP 1 - Create a Volume.

    STEP 2 - List Volumes.
    
    <img width="1227" height="500" alt="image" src="https://github.com/user-attachments/assets/db8bf319-e796-44a7-927b-3c039356547e" />
    
    STEP 3 - Inspect Volume.

    <img width="1181" height="297" alt="image" src="https://github.com/user-attachments/assets/f21ae6c9-3596-4c83-beb8-e76b37e7752f" />

    STEP 4 - Run Container with Volume.
    
    STEP 5 - Check Volume Inside Container.
    
    STEP 6 - Inspect Container.

    <img width="1181" height="297" alt="image" src="https://github.com/user-attachments/assets/54f79d6c-d0da-4abe-9217-3efd40e07dd7" />

    STEP 7 - Remove Container.
    
    STEP 8 - Remove Volume.
    
    STEP 9 - Remove Unused Volumes.

    <img width="1216" height="273" alt="image" src="https://github.com/user-attachments/assets/2dde3015-2a87-443c-b404-abb7b6f3c149" />


  

    

    





      





    







  

   

