here is the docker-compose file to esgtablish the wp platform.

we are using wordpress and mysql for the database.

run the docker-compose.yaml file by using this command 
"docker compose up -d"

next if the platform of WP already establish, login to the wp and you will be prompted with registration

if you want to create or mount any of the theme or website, log onto the container
using "docker exec -it wordpress_assesment bash"

copy the theme using "docker cp theme1 /var/www/html/wp-content/theme/"
copy the plugin using "docker cp theme1 /var/www/html/wp-content/plugins/"

NOTE!!
if this want to be deployed into/using kubernetes

first you have to convert the compose file into deploymentsk8s.yaml or files that is readable by kube.
use this "kompose convert"

NEXT "kubectl apply -f deploymentsk8s.yaml"
after that define the set of replicas for example in k8s files 
"replicas: 3"

DEPLOY!! 
