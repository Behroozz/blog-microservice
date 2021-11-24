# blog-microservice

Post 
docker build -t blog/posts .
docker run blog/posts
docker run -it blog/posts sh

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

k rollout restart deployments posts-depl

# Kubernetee Deployment
docker login -u "btabe0914" -p "" docker.io
create reposityory
docker tag blog/posts btabe0914/blog-posts
docker push btabe0914/blog-posts
kubectl rollout restart deployment posts-depl

# Service
k apply -f posts-srv.yaml
k get services
k describe service posts-srv
access post --> http://localhost:30133/posts

Apply app:
k apply -f .

# event bus
docker build -t btabe0914/event-bus .
k apply -f event-bus-depl.yaml

# pods communication
Create a Cluster IP Service and use the Service name

ClusterIp:
Expose service through k8s cluster with ip/name:port
NodePort
Expose service through Internal network VM's also external to k8s ip/name:port
LoadBalancer
Expose service through External world or whatever you defined in your LB.


# Load Balancer
- Load Balancer Service:
  Getting Traffic to single pod

  Outide of the the Cluser

- Ingress
  Pod that have set of routing rules in it and work with LB


Outside world --> Load balancer --> Ingress --> [cluster ip setvice]Pods
# Ingress 
https://kubernetes.github.io/ingress-nginx/deploy/#quick-start

# client
docker build -t btabe0914/client .

# skaffold
https://skaffold.dev/
brew install skaffold
