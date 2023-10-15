# Docker-Compose

Create EC2 instance
Install docker-compose :---
Following steps for installation:
![Screenshot 2023-10-12 152512](https://github.com/Pratikshinde55/Docker-Compose/assets/145910708/58760611-2f74-4641-8183-fe522db1f024)

Docker-comopse work on Docker engine , so we need to install docker & start docker services
    a.#yum install docker
    b. #systemctl start docker
for docker-compose on google search standalone
    docker-compose standalone install 
     (https://docs.docker.com/compose/install/standalone/)
     a. #curl -SL https://github.com/docker/compose/releases/download/v2.20.3/docker-compose-linux-x86_64 -o /usr/local/bin/docker-compose
     b. #chmod +x /usr/local/bin/docker-compose
     
![Screenshot 2023-10-12 150659](https://github.com/Pratikshinde55/Docker-Compose/assets/145910708/e007dc29-98d1-4ae7-9a3b-f5e2dea0fc9f)

 To check Docker-compse install or not-- #docker-compse version
  
     :: create two directory one for mysql data base volume & other is for docker-compose code
![Screenshot 2023-10-12 153358](https://github.com/Pratikshinde55/Docker-Compose/assets/145910708/391dcbe0-afc5-4863-b35e-0d9102d433d2)


This is code written in yaml language:
services:
  db:
    image: mysql
    container_name: mydb1
    networks:
    - psnet
    volumes:
    - /data:/var/lib/mysql
    environment:
    - MYSQL_ROOT_PASSWORD=redhat
    - MYSQL_DATABASE=blogdb
    - MYSQL_USER=pratik
    - MYSQL_PASSWORD=redhat
   wp:
    depends_on :
    - db
    image: wordpress
    container_name: mywp1
    networks:
    - psnet
    ports:
      - 8080:80
    environment:
    - WORDPRESS_DB_HOST=mydb1
    - WORDPRESS_DB_USER=pratik
    - WORDPRESS_DB_PASSWORD=redhat
    - WORDPRESS_DB_NAME=blogdb
networks:
  psnet:
   driver: bridge

   ![Screenshot 2023-10-12 171507](https://github.com/Pratikshinde55/Docker-Compose/assets/145910708/7f114fdf-977b-4157-ad34-78e93cb0c17f)

To view docker-compose file:
![Screenshot 2023-10-12 171551](https://github.com/Pratikshinde55/Docker-Compose/assets/145910708/e644a6d9-fed6-4c49-b75e-15d49303a1a7)


our three-tier architecture created with the help Of Docker-compose 
>>To Run Docker-compose file .. we used
   #docker-compose up -d
  we use detached because it helps us to run or launch container in background
![Screenshot 2023-10-12 172026](https://github.com/Pratikshinde55/Docker-Compose/assets/145910708/946967b4-0412-4254-8dc0-92e30626ae3e)

>> '#docker-compose ls' is command will tell us which file is used to lauch container
>> '#docker-compose ps ' is command that give us info about running container from docker-compose file
>> '#docker-compose logs' is command used to see logs of container.
![Screenshot 2023-10-12 172518](https://github.com/Pratikshinde55/Docker-Compose/assets/145910708/35b58aac-fb58-4020-9030-6ae31f266511)

To access this docker-compose setup -->>instance public IP+Port no.(Change EC2 instance inbound rule)
This interface shows on google
![Screenshot 2023-10-12 172957](https://github.com/Pratikshinde55/Docker-Compose/assets/145910708/b5f72e92-639f-43d8-89e3-c9d6f42d7bed)
