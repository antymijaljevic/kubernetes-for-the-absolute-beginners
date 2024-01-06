# create
kubectl create -f rollout.yaml

# get
kubectl get deployments

# rolling deployment
kubectl apply -f rollout.yaml
kubectl set image deployment myapp-deployment nginx-container=nginx:stable
kubectl edit deployment myapp-deployment --record

# replace deployment
kubectl replace -f rollout-2.yaml

# status
kubectl rollout status deployment myapp-deployment
kubectl rollout history deployment myapp-deployment

# record status
kubectl create -f rollout-2.yaml --record && kubectl rollout status deployment/myapp-deployment

# describe
kubectl describe deployment myapp-deployment

# rollback
kubectl rollout undo deployment myapp-deployment

# delete
kubectl delete deployment myapp-deployment