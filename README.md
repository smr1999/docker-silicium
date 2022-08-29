# docker-silicium 

---

**sudo systemctl start docker**

**sudo systemctl enable docker**

**docker run hello-world**

**docker ps**

**docker ps -a (all containers also stop containers)**

**docker images**

**docker login -> then username and password**

**docker login -u username -p password**

*Image dosen't runable but container does !*

**docker pull nginx**

**docker run nginx**

**docker run -d nginx (deattach)**

**docker stop container_id or container_name**

**docker start container_id or container_name (can use for stop continaers)**

**docker rm container_id or container_name**

**docker run -p 8080:80 -d image (port map 8080 our system to 80 image)**

**docker exec -it container_id or container_name /bin/bash**

```
Example

docker exec -it nginx_id bash

cd etc/nginx/conf.d/

cat default.conf

cd /usr/share/nginx/html

rm index.html

touch index.html

echo "<h1>Hello world</h1>" > index.html

```

---

### Use volume

**docker run -d -p 8080:80 -v /home/smr/Desktop/temp/bootstrap-silicium-final-project:/usr/share/nginx/html nginx**

**docker run -d -p 8080:80 -v /home/smr/Desktop/temp/bootstrap-silicium-final-project:/usr/share/nginx/html:ro nginx (readonly mode)**

---
### More about docker commands

**docker stop $[docker ps -q] (stop all containers)**

**docker start $[docker ps -aq] (start all containers)**

**docker rm $(docker ps -aq) (remove all containers)**

**docker rmi image_name**

---
### Save and load docker

**docker save -o path image_name**

**docker load -i path**

---

**docker run -d --name your-name image(set name for container)**

**docker pull nginx:alpine (use alpine version of nginx)**

---

### Dockerfile

**docker build -t website:latest -t website:0.1 .**

**docker run -d -p 80:80 --name website webiste:latest**

---

### docker compose

**docker compose up**

**docker compose up -d(deattach)**

**docker compose down**

