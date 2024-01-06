### https://github.com/kodekloudhub/example-voting-app-kubernetes

# microservices
voting-app > redis > worker > postgres > result-app

# spin it up without scaling
kubectl create -f .
kubectl get pods,svc,rs,deployments,nodes
minikube service voting-service --url
minikube service result-service --url

# scale in/out
kubectl scale deployment voting-app-deploy --replicas=3

# remove all
kubectl delete --all pods,services,deployments,jobs,configmaps,secrets