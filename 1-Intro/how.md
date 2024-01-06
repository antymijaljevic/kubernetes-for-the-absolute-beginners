# https://kubernetes.io/docs/tasks/tools/

# install docker engine
sudo service docker start


# install kubectl
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"
echo "$(cat kubectl.sha256)  kubectl" | sha256sum --check
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
kubectl version --client


# install minikube
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
minikube version


# setup and stop k8s cluster
minikube start --container-runtime=docker --driver=docker
minikube start --driver=hyperv
minikube ssh
minikube status
minikube stop
minikube delete

# cluster info
kubectl get nodes
kubectl describe node <>

# deploy sample nginx
kubectl create deployment nginx --image=nginx:stable
kubectl get deployments
kubectl expose deployment nginx --type=NodePort --port=80
minikube service nginx --url

# remove deployment
kubectl delete services nginx
kubectl delete deployment nginx
kubectl get pods

