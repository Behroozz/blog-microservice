# blog-microservice

Post 
docker build -t blog/post .
docker run blog/post
docker run -it blog/post sh

docker ps

# execute a command in running container
docker exec -ti container_id sh 
docker logs container_id

# Kubectl
kubectl apply -f posts.yaml 
docker ps a --> kubectl get pods

docker logs blog/posts:0.0.1 --> kubectl logs posts

docker exec -ti blog/posts:0.0.1 sh --> 
kubectl exec -ti posts posts sh

kubectl delete pods

kubectl describe pod posts


# zsh
code ~/ .zshrc
alias k="kubectl"


# Deployment
k apply -f config.yaml
k get deployments
k describe deployment posts-depl
k delete deployment posts-depl
