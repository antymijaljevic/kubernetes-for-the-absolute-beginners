# describe pod
kubectl run nginx --image=nginx
kubectl describe pod nginx
kubectl get pods
kubectl get pods -o wide
kubectl port-forward pod/nginx 8080:80
kubectl delete pod nginx

# create pod with yaml
kubectl apply -f pod.yaml