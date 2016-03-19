DOC stuff


/lib/systemd/system/docker.service

/etc/default/docker

systemctl daemon-reload
systemctl restart docker

###

systemctl stop docker
wget -P /etc/default/docker https://raw.githubusercontent.com/remonlam/docker-swarm/master/docker
wget -P /lib/systemd/system/ https://raw.githubusercontent.com/remonlam/docker-swarm/master/docker.service
systemctl daemon-reload
systemctl start docker
docker info

systemctl enable docker


docker -H tcp://127.0.0.1:2375 info

### Create Swarm Manager
docker run --rm swarm create

docker run -t swarm-mgmt -d -p 2376:2375 swarm manage token://231e3e49bb9f292a80af57b4cef582c9

docker run -d swarm join --addr=192.168.0.100:2375 token://231e3e49bb9f292a80af57b4cef582c9
docker run -d swarm join --addr=192.168.0.101:2375 token://231e3e49bb9f292a80af57b4cef582c9
docker run -d swarm join --addr=192.168.0.102:2375 token://231e3e49bb9f292a80af57b4cef582c9

swarm list token:b21cc6c97ee39bcf159da2d4032365d3
