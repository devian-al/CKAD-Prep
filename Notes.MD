
```bash
## Quickly create alias and load the bash profile
alias k='kubectl' >> /.bashrc && source /.bashrc

## Replica set commands
Kubectl create -f replicaset-filename.yaml
kubeclt get replicaset
kubectl delete replicaset <replicaset-name>
kubectl replace -f <file-name.yaml>
kubectl scale -relicas=x -f <file-name.yaml>
# delete pods in a replicaset
kubectl scale rs/<replicas-set-name> --replicas=0
```
