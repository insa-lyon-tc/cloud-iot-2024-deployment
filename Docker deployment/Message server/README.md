## to create images and load to docker hub:  
`docker-compose build`  
`docker-compose push`  

### manualy:  
`docker build -t ghoti165/mqtt-broker:latest ./broker`  
`docker build -t ghoti165/subscriber:latest ./subscriber`  
`docker build -t ghoti165/publisher:latest ./publisher`  
`docker push ghoti165/mqtt-broker:latest`  
`docker push ghoti165/subscriber:latest`  
`docker push ghoti165/publisher:latest`  



## install docker/docker-compose in Raspberry Pi:  
### docker  
curl -fsSL https://get.docker.com | sh  
docker --version  

### docker-compose
sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-linux-armv7" -o /usr/local/bin/docker-compose  
sudo chmod +x /usr/local/bin/docker-compose  
docker-compose --version  

### Ajouter le fichier au PATH (si nécessaire)
sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose  

## run docker image: 
copy the file `PullAndRunImage/docker-compose.yml` to Respberry Pi  
run:  
`sudo -s`  
`docker-compose pull`  
`docker-compose up`  


