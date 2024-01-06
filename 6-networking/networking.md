# create all at once
kubectl create -f .

# service
kubectl get service
kubectl get svc

# more info about node
kubectl get nodes -o wide

# expose service in browser
minikube service myapp-service --url

# analogy with AWS services
Service
    > NodePort = public load balancer
    > ClusterIP = internal load balancer
    > LoadBalancer = public load balancer