 AWS Docker Nginx Website Deployment .

Project Overview

This project demonstrates how to deploy a static website on AWS EC2 using Docker and Nginx.
The website is publicly accessible through the EC2 public IP address.


Technologies Used

- AWS EC2 (Amazon Linux)
- Docker
- Nginx Web Server
- Linux Commands
- Git & GitHub
- HTML & CSS


Architecture

Local Machine → GitHub → AWS EC2 → Docker Container → Nginx → Website


Steps Performed

1. Launch EC2 Instance

- Created an EC2 Linux instance in AWS
- Downloaded and used ".pem" key pair
- Connected using SSH

2. Install Docker

sudo yum update -y
sudo yum install docker -y
sudo systemctl start docker
sudo systemctl enable docker

3. Pull Nginx Image

docker pull nginx

4. Run Nginx Container

docker run -d -p 80:80 nginx

5. Copy Website Files

docker cp index.html <container-id>:/usr/share/nginx/html/
docker cp style.css <container-id>:/usr/share/nginx/html/

6. Configure Security Group

Allowed inbound rule:

- HTTP (Port 80) → Anywhere (0.0.0.0/0)

7. Access Website

Open in browser:

http://<EC2-Public-IP>


Project Features

- Public website hosting
- Docker containerized web server
- Remote server management using SSH
- Version controlled with GitHub


Learning Outcome

- Learned AWS EC2 setup and connection
- Understood Docker container deployment
- Hosted a real website using Nginx
- Managed files inside running containers

Future Improvements

- Add CI/CD pipeline (GitHub Actions)
- Add domain name using Route 53
- Enable HTTPS using SSL certificate

 Conclusion

 By doing this project we understand how to deploy a static website on AWS EC2 using Docker and Nginx
