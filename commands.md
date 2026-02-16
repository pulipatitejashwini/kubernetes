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

## Create Deployment
Apply deployment YAML:                    
`kubectl apply -f deployment.yml`                                   
Verify Deployment:                  
`kubectl get deploy`                      
Verify ReplicaSet:                  
`kubectl get rs`                     
Verify Pods:                    
`kubectl get pods -o wide`                          
Describe Deployment:                    
`kubectl describe deployment nginx-deployment`                    

## Verify Probes
Describe Pod:                         
`kubectl describe pod <pod-name>`                 
Check for:                 
- **Liveness**               
- **Readiness**                   
- **Events section**                       

## Scale Deployment
Scale to 5 replicas:                   
`kubectl scale deployment nginx-deployment --replicas=5`                   
Verify scaling:                     
`kubectl get pods`                  
`kubectl get rs`                    

## Perform Rolling Update (Image Change)
Update image version:                  
`kubectl set image deployment/nginx-deployment nginx-container=nginx:1.24`                     
Check rollout status:                  
`kubectl rollout status deployment/nginx-deployment`              
Verify Pods:               
`kubectl get pods`                

## Check Rollout History
View rollout history:                  
`kubectl rollout history deployment/nginx-deployment`                    
View specific revision:               
`kubectl rollout history deployment/nginx-deployment --revision=1`               

## Rollback Deployment
Rollback to previous version:                    
`kubectl rollout undo deployment/nginx-deployment`                      
Verify rollback:                          
`kubectl rollout status deployment/nginx-deployment`                     
`kubectl get pods`                    

## Expose Deployment 
Create Service:                   
`kubectl expose deployment nginx-deployment --type=NodePort --port=80`                  
Check Service:                  
`kubectl get svc`                   
Get Service URL (Minikube):                   
`minikube service nginx-deployment --url`                      

## Delete Resources
Delete deployment:                    
`kubectl delete deployment nginx-deployment`                    
Delete service:                         
`kubectl delete svc nginx-deployment`                       
