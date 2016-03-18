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
docker -H tcp://192.168.0.100:2375 info
systemctl enable docker
