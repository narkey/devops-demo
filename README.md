# devops-demo
## Prerequisites
Install Docker Desktop

Enable kubernetes on Docker Desktop

Install Helm


## Docker
### Existing image from dockerhub
docker run -d -p 27017-27019:27017-27019 --name mongodb mongo

### Personalized image
cd helloworld

docker build . -t nodehelloimg

docker run -d --name nodehello -p 127.0.0.1:3000:3000 -t nodehelloimg

docker rm nodehello  --force

## Kubernetes

cd ../k8s

kubectl apply -f nodehello.yaml

kubectl delete -f nodehello.yaml


## Ansible

cd ../ansible

ansible-playbook -i inventory.ini play.yml


## Helm & Logging

helm init
