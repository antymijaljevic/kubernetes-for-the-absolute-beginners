# create replication controller
kubectl create -f replication-controller.yaml
kubectl get rc
kubectl describe rs nginx-rs
kubectl delete rc <replication-controller-name>

# create replica set
kubectl create -f replica-set.yaml
kubectl get rs
kubectl delete rs <replica-set-name>

# update/edit replication controler or replica set
kubectl apply -f replica-set.yaml
kubectl replace -f replica-set.yaml
kubectl scale --replicas=5 -f replica-set.yaml
kubectl scale --replicas=5 replicaset nginx-rs
 # (etcd)
    kubectl edit rs nginx-rs 