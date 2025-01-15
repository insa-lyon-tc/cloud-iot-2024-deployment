** install docker/docker-compose in Raspberry Pi:
*** docker
curl -fsSL https://get.docker.com | sh
docker --version

*** docker-compose
sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-linux-armv7" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
docker-compose --version

*** Ajouter le fichier au PATH (si nécessaire)
sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose



** to create images and load to docker hub:

`docker login`  
`docker-compose build`
`docker-compose push`

*** manualy: 
`docker build -t ghoti165/mqtt-broker:latest ./broker`  
`docker build -t ghoti165/subscriber:latest ./subscriber`  
`docker build -t ghoti165/publisher:latest ./publisher`  
`docker push ghoti165/mqtt-broker:latest`  
`docker push ghoti165/subscriber:latest`  
`docker push ghoti165/publisher:latest`  



** run docker image: 
copy the file `PullAndRunImage/docker-compose.yml` to Respberry Pi  
run:  
`docker-compose pull`  
`docker-compose up`


** for the code python that need to call the equipement of Respberry Pi

run `docker run -v /var/run/docker.sock:/var/run/docker.sock name-of-image`  

change code in python : add "docker", "exec", "-it", "your-container-name", before the command


