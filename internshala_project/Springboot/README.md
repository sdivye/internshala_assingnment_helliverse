# Installation of Dependencies

This guide covers the installation of necessary dependencies including OpenJDK and Maven.

<p>Install the OpenJDK 11 Java Runtime Environment (JRE).</p>

```
sudo apt update && sudo apt install -y openjdk-11-jre
```

<p>Install Maven, which is a build automation tool used primarily for Java projects.</p>

```
sudo apt install -y maven
```

# Setup and Build the Java Spring Boot Project

This guide covers cloning the repository, navigating to the project directory, and building the project.

## Cloning the Repository

Clone the desired git repository.
```
git clone https://github.com/sdivye2/Jenkins-Zero-To-Hero.git
```
<p>Navigate to the Project Directory</p>

Change directories to the Spring Boot project directory.
```
cd Jenkins-Zero-To-Hero/springboot/
```
Building the Project

Use Maven to clean and package the project.
```
./mvnw clean package
```
Source the ~/.bash_profile file to ensure that any necessary environment variables are loaded.
```
source ~/.bash_profile
```
<p>Configure Nginx and Run the Application</p>

This guide covers configuring Nginx, running the Java Spring Boot application, and restarting the Nginx service.
```
sudo apt install nginx -y
```
## Navigate to the Target Directory
Running the Application
```
cd target/
```
Run the packaged jar file.
```
java -jar spring-boot-web.jar &
```
## Configure Nginx

Navigate to the Nginx configuration directory and edit the default configuration file. Do this manually.
```
cd /etc/nginx/sites-available/
sudo nano default
```
## Edit the default 
```bash 
server {
    listen 80;
    server_name springboot.xtended.live;
    index index.html index.htm;
    access_log /var/log/nginx/spring.xtended.live .log;
    error_log  /var/log/nginx/spring.xtended.live -error.log error;

    location / {
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header Host $http_host;
        proxy_pass http://127.0.0.1:8081/;
        proxy_redirect off;
    }
  }
```
Copy the Jar File to the Web Server Root Directory
```
sudo cp ~/Jenkins-Zero-To-Hero/springboot/target/spring-boot-web.jar /var/www/html/
```
Create a Symlink for the Nginx Configuration
```
sudo ln -s /etc/nginx/sites-available/default /etc/nginx/sites-enabled/
```
To run Springboot in background service 
```bash
nohup java -jar bmi-1.0.jar &
```
Restart Nginx Service
```
sudo systemctl service nginx restart
```
