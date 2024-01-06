# see all objects
kubectl get all

# remove all resources
kubectl delete --all pods,services,deployments,jobs,configmaps,secrets

# deployment
kubectl apply -f deployment.yaml
kubectl get deployment
kubectl describe deployment myapp-deployment
kubectl create deployment <deploy_name> --image=<image> --replicas=<noOfRep>