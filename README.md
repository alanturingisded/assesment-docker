here is the docker-compose file to establish the wp platform.

we are using wordpress and mysql for the database.

run the docker-compose.yaml file by using this command
*docker compose up -d*

next if the platform of WP already establish, login to the wp and you will be prompted with registration

if you want to create or mount any of the theme or website, log onto the container
*docker exec -it wordpress_assesment bash*

copy the theme
*docker cp theme1 /var/www/html/wp-content/theme/*
copy the plugin
*docker cp theme1 /var/www/html/wp-content/plugins/*

NOTE!!
if this want to be deployed into/using kubernetes

first you have to convert the compose file into deploymentsk8s.yaml or files that is readable by kube.

install kompose
curl -L https://github.com/kubernetes/kompose/releases/download/v1.25.0/kompose-linux-amd64 -o kompose
chmod +x kompose
sudo mv ./kompose /usr/local/bin/kompose*

to convert your compose file into kubernetes yaml format
*kompose convert*

apply deployment
*kubectl apply -f deploymentsk8s.yaml*


after that define the set of replicas for example in deploymentsk8s files
"replicas: 3"

also attach it into load balancer, so the traffic will be managed
set the target port into 80 and 443, and set the type into loadbalancer

DEPLOY!! 
