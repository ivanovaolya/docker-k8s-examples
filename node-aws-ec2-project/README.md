# Node AWS EC2 deployment project 
Contains samples of https://www.udemy.com/course/docker-kubernetes-the-practical-guide.   
Section 9: Deploying Docker Containers
### Setup
1. Create and launch EC2 instance on aws.amazon.com
2. Connect to your instance using its Public DNS
```
> ssh -i "some-name-key-pair.pem" ec2-user@ec2-3-126-84-10.eu-central-1.compute.amazonaws.com
```
3. Verify that all pachages on remote machine are using the latest versions
```
> sudo yum update -y
```
4. Install Docker
```
> sudo amazon-linux-extras install docker
```
4. Start Docker
```
> sudo service docker start
```
5. Build an image locally and push it to DockerHub
```
> docker build -t docker-practical-guide:v2 .
> docker tag docker-practical-guide:v2 olyaaivanova/docker-practical-guide:v2
> docker push olyaaivanova/docker-practical-guide:v2
```
6. In AWS Console verify that security group(s) for instance can accept inbound traffic (http, port 80)
7. Run built image in EC2 instance
```
> docker run -d --rm -p 80:80 olyaaivanova/docker-practical-guide:v2
```
8. Using Public IPv4 address, launch deployed app 