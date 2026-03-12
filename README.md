# INT332-DEVOPS
This repository contains Docker concepts, commands and practical implementations.

1. Introduction to Docker

Docker is a containerization platform that allows developers to package applications with their dependencies and run them consistently across different environments.

2.1 Objects of a docker 
   
  - Images
  
  - Container
 
  - Volume
  
  - Network

2.2 Docker Architecture   
  
  - Docker Client :- The Docker Client is the command-line interface (CLI) that users use to send Docker commands to the Docker daemon.
  
  - Docker Daemon :- The Docker Daemon is the background service that builds images, runs containers, and manages Docker resources.
  
  - Docker Registry :- The Docker Registry is a storage system where Docker images are stored and shared (e.g., Docker Hub).

2.3 Cotainerization :- The process of packaging an application and its dependencies into a container so it can run consistency in any environment.

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

7. Docker log :- It displays the runtime output and error message of a container.

8. Docker CLI :- It is the command line interface used to interact with docker.

9. DockerFile :- It is a text file containing instructions used to build a Docker image.

10. Image layering :- Docker images are built as a stack of read-only layers, where each Dockerfile instruction creates a new layer that can be cached and reused to optimize storage and build performance. 
  
    <img width="654" height="417" alt="image" src="https://github.com/user-attachments/assets/64734ae6-2b44-4a98-b155-ad698b1ac925" />

11. Build Context :- The build context is the set of files and folders that Docker sends to the Docker daemon when running the docker build command.

12. .dockerignore :- Excludes unnecessary files from the build context.

13. cgroups :- Control groups limit and monitor system resources like : CPU, Memory, disk I/O.

14. namespace :- A namespace is a Linux kernel feature that provides isolation by giving each container its own separate view of system resources like processes, network, and filesystem.

    Examples of Docker namespaces
    
     <img width="400" height="298" alt="image" src="https://github.com/user-attachments/assets/2494f022-7ee1-40ca-9492-391992c6c435" />

    1. PID Namespace (Process Isolation) :- PID namespace isolates process IDs, so processes inside one container cannot see or interact with  processes in another container or the host.

    2. NET Namespace (Network Isolation) :- Network namespace provides separate network interfaces, IP addresses, routing tables, and ports for each container.
    
      Each container gets its own:

       - IP address
        
       - Network interface
        
       - Port space

     3. MNT Namespace (Mount / Filesystem Isolation) :- Mount namespace isolates the filesystem view, so each container sees its own filesystem structure.  

15. Diffrences

    15.1  Docker Hub vs Docker Registry

    <img width="579" height="241" alt="image" src="https://github.com/user-attachments/assets/6476eec8-c161-4c56-a99c-f34b6df632f9" />

    15.2  Tagging vs Versioning

     <img width="587" height="212" alt="image" src="https://github.com/user-attachments/assets/35b33919-5a8b-4257-b4cb-d748e8095f4a" />

    15.3 Containerization vs Virtualization

      <img width="528" height="266" alt="image" src="https://github.com/user-attachments/assets/d197d24c-4d21-499a-b50c-2c84a3431b53" />

    15.4 Container vs Volume

     <img width="576" height="211" alt="image" src="https://github.com/user-attachments/assets/625bb9bd-2a8c-410f-b36b-8fd9a213f3c5" />
        

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

    Docker Network

    Docker network is a system that enables communication between containers, the Docker host, and external networks.

    Types of Docker Networks

     1. Bridge Network (Default) :- A bridge network connects containers running on the same Docker host and allows them to communicate using container IP or name.

        Practical Commands 

        STEP 1 - Create Network

        STEP 2 - Run containers

        STEP 3 - Test communication

         <img width="1470" height="956" alt="image" src="https://github.com/user-attachments/assets/401f301e-b3ff-4ee6-995c-1569c90c58bf" />

        STEP 4 - List networks

          <img width="1172" height="269" alt="image" src="https://github.com/user-attachments/assets/951ddd98-2c0f-4411-9ca3-5fef0bc04e6d" />

     2. Host Network :- Host network removes isolation and makes the container use the host machine's network directly.

        <img width="1191" height="104" alt="image" src="https://github.com/user-attachments/assets/913dd093-f5e0-49fd-ad9a-c1cb66ced330" />

        <img width="598" height="39" alt="image" src="https://github.com/user-attachments/assets/ca70ea0b-24c4-4df4-8044-882ccd94171d" />


     4. Overlay Network :- Overlay network connects containers running on different Docker hosts.

         Used in Docker Swarm / Kubernetes clusters.
   
        STEP 1 - Initialize swarm
        
         <img width="884" height="90" alt="image" src="https://github.com/user-attachments/assets/168434f6-904d-4f65-aead-907e1f58ec7e" />

        STEP 2 - Create overlay network

          <img width="769" height="60" alt="image" src="https://github.com/user-attachments/assets/304c874a-ab68-4d25-902b-5c240e800125" />

         <img width="629" height="277" alt="image" src="https://github.com/user-attachments/assets/dc9da4f4-6237-43cb-b79d-f513d27ebda7" />
   
         <img width="1538" height="120" alt="image" src="https://github.com/user-attachments/assets/6c80ba03-e877-4187-8ee8-310d90ce4a2b" />



        Useful Docker Network Commands :-

        STEP 1 - List networks

        STEP 2 - Inspect network

         <img width="1238" height="322" alt="image" src="https://github.com/user-attachments/assets/c2712a31-348c-4a9a-8954-a68c63276d80" />

        STEP 3 - Remove network

        STEP 4 - Connect container to network

        STEP 5 - Disconnect container

          <img width="1220" height="309" alt="image" src="https://github.com/user-attachments/assets/37680a19-88fd-44d9-b4da-4214ef32635f" />

        Comparison Table
        
         <img width="756" height="385" alt="image" src="https://github.com/user-attachments/assets/ee6f6f3f-f1db-4bc4-ace0-e8808688830a" />

    Building and Running an Nginx Container Using Dockerfile

     STEP - 1 Create index.html

     STEP - 2 Create default.conf

     STEP - 3 Create Dockerfile

     STEP - 4 Build Docker image

     STEP - 5 Run container

     STEP - 6 Access website using browser
      
     <img width="1218" height="494" alt="image" src="https://github.com/user-attachments/assets/9b5479fc-b677-47b8-b09b-f7d13f73076a" />
     
     <img width="1200" height="302" alt="image" src="https://github.com/user-attachments/assets/31911379-ef50-4bc2-848f-7932ed805101" />
     
     <img width="1216" height="331" alt="image" src="https://github.com/user-attachments/assets/e67d82c1-520f-4b09-b40b-e17ad09070a9" />
     
     <img width="734" height="318" alt="image" src="https://github.com/user-attachments/assets/3e23c4fb-54d2-4c14-a753-9ef73720f1d6" />


     Practical: Run a Node.js App Using Docker

     STEP 1 - Create Project Folder

     STEP 2 - Create Node Application

     STEP 3 - Create package.json

     STEP 4 - Create Dockerfile

     STEP 5 - Check Project Structure

     STEP 6 - Build Docker Image

     STEP 7 - Run the Container

     STEP 8 - Check Running Container

     STEP 9 - Open in Browser

     <img width="1215" height="423" alt="image" src="https://github.com/user-attachments/assets/3da9ead3-a865-4012-9430-7161dbb7e553" />

     <img width="1253" height="301" alt="image" src="https://github.com/user-attachments/assets/5035eb02-603d-4544-96f2-51c6424bd95f" />

     <img width="1224" height="310" alt="image" src="https://github.com/user-attachments/assets/2f79ece3-3fef-4cd2-9fbe-1f4b0ba2acb1" />

     <img width="523" height="284" alt="image" src="https://github.com/user-attachments/assets/1e5fc930-119f-4b59-bb45-c8cc94b7e25a" />








        

          



       

    

    





      





    







  

   

