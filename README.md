# springboot
#1.Steps to follow on ec2 ubuntu instance

sudo chown ubuntu:ubuntu -R /opt
cd /opt
docker images
wget wget https://github.com/Kriengg/springboot/archive/main.zip
unzip main.zip
cd springboot-main/demo
docker build -t springboot-app .
docker run -d -p 80:8080 springboot-app

#2.Application logs on container
docker logs d645fbcf2d67

# if u have log file on container..do bash
a)docker ps -a [get the containername ex  heuristic_einstein]

now run this command to interact with container
b)docker exec -it heuristic_einstein /bin/sh

c)In our applition.property we gave log file as  mylog.log

You can run below command to view it 

/app # ls
app.war    mylog.log
/app # vi mylog.log 

or use tail
/app # tail -n 20 mylog.log

#applcaiton url

http://ec2IP:80/hello
http://ec2IP/hello


