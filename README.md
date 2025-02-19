# Three-tier Architecture of Blogging site(WordPress, MySQL, Docker network) using Docker Automation that docker-compose.
Global Blogging Made Easy with Docker and WordPress.

- Set-up:

I use AWS EC2 Instance(AMI- Amazon linux) as Operating System for Docker and then i Install docker-compose on it.

- What is Three-tier Architecture:

1. For Blogging Site I use "WordPress".
2. For DataBase to the Wordpress I use "MySQL".
3. For Network I use own customised "Docker network".

## Step: 1 [Install Docker & start Docker Service]
Docker-comopse work on Docker Engine, So we need to install Docker & Start Docker Services

Install Docker Command:

    yum install docker

Start Docker service Command:

    systemctl start docker

## Step:2- [Install Docker-compose]
### docker-compose:
docker-compose helps to make Automation in Docker Container, docker-compose is use for Automation, we creates Automation file by using yaml language,
docker-compose file must be in YAML language.

"docker-compose.yml" is standard file name for docker-compose file.

- Following steps for installation:

For download docker-compose search on google "docker-compose standalone":

docker-compose Standalone Install Link- [Docker-compose-download-link](https://docs.docker.com/compose/install/standalone/)

![Screenshot 2023-10-12 152512](https://github.com/Pratikshinde55/Docker-Compose/assets/145910708/58760611-2f74-4641-8183-fe522db1f024)

curl downloads the Docker Compose binary for Linux into the /usr/local/bin/ directory:    

    curl -SL https://github.com/docker/compose/releases/download/v2.20.3/docker-compose-linux-x86_64 -o /usr/local/bin/docker-compose

Following command gives the downloaded docker-compose file executable permissions:

    chmod +x /usr/local/bin/docker-compose

chmod: This is the command to change file permissions in Unix-like operating systems.

+x: This option adds execute permissions to the file. It allows the user to run the file as a program.

/usr/local/bin/docker-compose: This is the path to the docker-compose file.

![Screenshot 2023-10-12 150659](https://github.com/Pratikshinde55/Docker-Compose/assets/145910708/e007dc29-98d1-4ae7-9a3b-f5e2dea0fc9f)


 To check Docker-compse install or not use command:

    docker-compse version


## Step:2- [docker-compose.yml automation file]
Create two directories One for mysql data base volume & Second for docker-compose code:-
 
![Screenshot 2023-10-12 153358](https://github.com/Pratikshinde55/Docker-Compose/assets/145910708/391dcbe0-afc5-4863-b35e-0d9102d433d2)

This is code written in yaml language: (docker-compose DSL is Yaml) 

![Screenshot 2023-10-12 171507](https://github.com/Pratikshinde55/Docker-Compose/assets/145910708/7f114fdf-977b-4157-ad34-78e93cb0c17f)

To view docker-compose file:

![Screenshot 2023-10-12 171551](https://github.com/Pratikshinde55/Docker-Compose/assets/145910708/e644a6d9-fed6-4c49-b75e-15d49303a1a7)

To Run Docker-compose file the command is:

     docker-compose up -d
          
 We use (-d) detached because it helps us to run or launch Container in background

- Three-tier Architecture created with the help of Docker-compose  
 
![Screenshot 2023-10-12 172026](https://github.com/Pratikshinde55/Docker-Compose/assets/145910708/946967b4-0412-4254-8dc0-92e30626ae3e)

Command will tell us which file is used to lauch container:
     
     docker-compose ls

Command that give us info about running container from docker-compose file:

     docker-compose ps 

Command used to see logs of container:     
     
     docker-compose logs  
          
![Screenshot 2023-10-12 172518](https://github.com/Pratikshinde55/Docker-Compose/assets/145910708/35b58aac-fb58-4020-9030-6ae31f266511)


## Step:3- [Access Wordpress from Browser]
To access this docker-compose setup -->>instance public IP+Port no.(Change EC2 instance inbound rule)

This interface shows on Google:-

![Screenshot 2023-10-12 172957](https://github.com/Pratikshinde55/Docker-Compose/assets/145910708/b5f72e92-639f-43d8-89e3-c9d6f42d7bed)

