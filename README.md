# Layer-4-Load-Balancer
**Layer-4 Load Balancer with Nginx**

**Step [1] Clone GitHub**

**Goto webapp Directory**
    
    cd webapp
    
**Build Docker file**

    docker build -t webapp .

**Check Docker Images**
    
    docker images
    
**Run Docker Image First Container**

    docker run -it -d --name web01 -p 9000:80 webapp
    
**Run Docker Image 2nd Container**

    docker run -it -d --name web02 -p 9001:80 webapp
    
**Check All Container**

    docker ps -a
    
**Check Running Container**

    docker ps

**Execute 2nd Webapp container**

    docker exec -it <Container ID> bash

**Change 2nd Container index.html file Header / Body**

    vi /usr/share/nginx/html/index.html
    
**Reload Nginx 2nd webapp-server** 
 
    docker exec <Container ID> nginx -s reload
    
**Check Web browser 1st webapp**

    localhost:9000

**Check Web browser 2nd webapp**

    localhost:9001
    
**Back to Current Directory**    

    cd ..
    
**Go to proxy Directory**

    cd proxy
    
**Build Docker file**

    docker build -t lb/proxy .

**Run Docker Image Container**

    docker run -it -d -p 80:80 --name lb-server lb/proxy
    
**Check Web Browser (Double reload, reload, reload)**

    localhost:80
