## Start Minikube
`minikube start --driver=docker`                        
`minikube status`

## Cluster Verification
`kubectl cluster-info`                 
`kubectl get nodes`                      
`kubectl get pods -n kube-system`

## Create Pod YAML
`vi pod.yml`

## Deploy Pod
`kubectl apply -f pod.yml`                   
`kubectl get pods`                      
`kubectl get pods -o wide`                   

## Describe Pod
`kubectl describe pod nginx-pod`

## Exec into Pod
`kubectl exec -it nginx-pod -- /bin/bash`                     
`ls /usr/share/nginx/html`                 
`exit`                     

## Port Forward
`kubectl port-forward nginx-pod 8080:80 --address 0.0.0.0`                      
Access in browser:                        
`http://<public-ip>:8080`                    

## Delete Pod 
`kubectl delete pod nginx-pod`                    
Recreate:                 
`kubectl apply -f pod.yml`                     


