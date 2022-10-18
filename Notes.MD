
```bash
## Quickly create alias and load the bash profile
alias k='kubectl' >> /.bashrc && source /.bashrc
```
```bash
# Commands
## Replica set commands
  Kubectl create -f <replicaset-filename.yaml>
  kubeclt get replicaset
  Kubectl edit replicaset <replicas-set-name>
  kubectl delete replicaset <replicaset-name>
  kubectl replace -f <file-name.yaml>
  kubectl scale -relicas=x -f <file-name.yaml>
 ### delete pods in a replicaset
  kubectl scale rs/<replicas-set-name> --replicas=0

## Deployments
  Kubectl get deployment
  Kubectl create -f <deployment-file-name.yml>
 ### redirect that to file
  kubectl create deployment --image=nginx nginx --dry-run=client -o yaml > nginx-deployment.yaml
  kubectl apply -f nginx-deployment.yaml
 ### directly edit the deployment yaml
  kubectl edit deployment/nginx
  
## Namespaces
 ### pods in a namespaces can use the name of the pod as DNS name
 ### pods in a different namespace can access the pods in other namespaces in the below format
  "pod-name.name-space.subdomain(such as svc).domain(cluster.local)" 
 ### name space can be created in following ways
  kubectl create -f <namespace-file.yaml>
  kubectl create namespace <name>
 ### set current context to work in a particular namespace
  kubectl config set-context $(kubectl config current-context) --namespace=name
  
## Imperative Commands
  k run redis --image=redis:alpine --labels="tier=db"
  k expose pod redis --port=6379 --name redis-service
  k create deployment webapp --image=lodekloud/webapp-color --replicas=3
  k run httpd --image=httpd:alpine --port=80 --expose
```
