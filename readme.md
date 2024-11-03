# InfoBridgePro

InfoBridgePro is a database management system designed to manage information about employees, departments, and projects. This application streamlines data management within an organization.

## Prerequisites

To run this application, ensure you have the following installed:
- **MySQL** (version compatible with the project's database schema)
- **Docker** and **Docker Compose** (for containerized setup)
- **PHP** and **Apache Server** (for PHP web components)
- **Linux Terminal** with sudo privileges (to load files and manage containers)

## Setup Instructions

### Step 1: Build and Start PHP and MySQL Web Application Docker Container

1. Navigate to the directory containing your `docker-compose.yml` file.
2. Run the following command to build and start the container:
   ```bash
   docker-compose up
3. Open localhost in your web browser
   
### Step 2: To access and load files in MySQL
1. Check the containers:
   ```bash
   docker ps -a
2. Check the Images:
   ```bash
   docker images
3. Run the following command in a new terminal of the same directory, To Load the .dat files first change the path to:
   ```bash
   docker cp "/home/Downloads/docker-workspace/src/resources/project.dat" <MySQL containerID> :/var/lib/mysql-files/
4. Run the following command in a new terminal of the same directory to access MySQL Container:
   ```bash
   docker exec -it <mysql_container_Id> bash
5. After opening the bash you have to give access from client side to load files
   ```bash
   mysql --local-infile=1 -u ruthvik -p
   ruthvik
6. Type this in MySQL
   ```bash
   LOAD DATA INFILE '/var/lib/mysql-files/project.dat' INTO TABLE PROJECT;
7. To create Table you can use the book user
   ```bash
   mysql -u book -p
   book

### Step 3: To stop the containers

1. Use this command to stop containers
   ```bash
   docker-compose down
2. To remove the image in docker
   ```bash
   docker rmi <image_name>
