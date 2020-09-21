# This repository shows my understanding and usage of cloud tools, platform, and services. It fulfills the Work Processes:

  > - Use various cloud tools, services, and platforms
  > - Use logging and monitoring tools
  > - Migrate data from on-premise solution to cloud solution

## About

The app contained in this repository is a fibonacci calculator. You enter an integer and receive the n'th value in the fibonacci sequence. i.e: 11 -> 144. Once a value has been entered, it is saved in a postgres db and a redis cache is used so that computation doesn't have to be done again.

![fibapp](./images/fibonacci-app.jpg)

This repo contains 4 folders which are used to create 4 docker images:

- client - web application
- nginx - traffic manager
- server - server
- worker - connects server to postgres

I have built the four images and have pushed them to my dockerhub repository:

![dockerhub](./images/docker_hub.jpg)

As you can see above, the four images created and pushed to dockerhub are:

- multi-client
- multi-nginx
- multi-server
- multi-worker

After creating these images, I created a couple services using AWS:

- Elastic Beanstalk
![elastic beanstalk](./images/elasticbeanstalk.jpg)

- ElastiCache (Redis)
![elasticache](./images/elasticache-redis.jpg)

- RDS (Managed Relational Database Service)
![rds](./images/rds.jpg)

- VPC Security Group
![security group](./images/security_group.jpg)

After creating the services using AWS, I then created this github repository and hooked it up with Travis-CI for CI/CD. The [*.travis.yml*](./.travis.yml) file contains the instructions for integrating and deploying the application.

I had instructed Travis-CI to integrate and deploy the application when I pushed the code to the master branch of the repo. After pushing, Travis built and deployed to AWS.
![travis](./images/travis.jpg)

You can check out the Travis-CI log [here](./travis-log.txt).

Here is the deployed app:
![deployed](./images/deployed-app.jpg)

You can see the url which is `http://multidocker-env-1.eba-p2zm5mep.us-east-2.elasticbeanstalk.com/`. (This url will not work now because I took down all the services after completing the work processes/competencies since it would cost $$)

### Various cloud tools, services, platforms

You can see me use multiple tools, services, platforms like:

- GitHub
- Travis-CI
- Docker
- DockerHub
- AWS
  - Elastic Beanstalk
  - RDS
  - ElastiCache
  - Security Group

### Logging and Monitoring

[Here](./ec2-log.txt) is the last 100 lines of logging from my EC2 instance that I would use to help solve issues concerning my deployed services.

RDS Logging
![rds-logging](./images/rds-logging.jpg)

Elastic Beanstalk Monitoring
![ec2-monitoring](./images/ec2-monitoring.jpg)

RDS Monitoring
![rds-monitoring](./images/rds-monitoring.jpg)

ElastiCache Metrics
![elasticache metrics](./images/elasticache-metrics.jpg)

### On-premise to Cloud

You can see me moving the application from on-premise (my computer) to the cloud (AWS).
