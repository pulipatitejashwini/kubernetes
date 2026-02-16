## Update System
`sudo apt update -y`                

## Install Docker
`sudo apt install -y docker.io`                       
`sudo systemctl enable docker`                      
`sudo systemctl start docker`                  
`sudo usermod -aG docker $USER`                      
`**Re-login**`                                           
Verify:                     
`docker --version`                    
`docker run hello-world`                       

## Install Minikube
Download:                      
`curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64`              
Install:                       
`sudo install minikube-linux-amd64 /usr/local/bin/minikube`                   
Verify:                   
`minikube version`                   

## Install kubectl
Download:                 
`curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"`                            
Make executable:                     
`chmod +x kubectl`                        
Move to path:                  
`Sudo mv kubectl /usr/local/bin/`                  
Verify:                   
`kubectl version --client`                  
