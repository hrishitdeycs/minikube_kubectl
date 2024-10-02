# minikube_kubectl
### 1.Create an account on aws
### 2.Sign in to your account 
### 3.Go to your dashboard
### 4.Click on launch instance
### 5.Enter your server name and select ubuntu(22.04) and t3.xlarge
### 6.Click on create new key pair
### 7.Enter your key pair name then select .ppk and click on create new key pair
### 8.In the network settings click on allow all traffic from the internet
### 9.Increase storage to 30gb and click on launch instance
### 10.Copy the public ipv4 address from your instance and download putty. 
### 11.Paste the ip address in host name   
### 12.Click on SSH then auth then credentials
### 13.Click browse and open the key pair you downloaded
### 14.Click accept then type ubuntu and then press enter
### 15.Use the following docker commands
```bash
curl -sL https://github.com/ShubhamTatvamasi/docker-install/raw/master/docker-install.sh | bash
```
```bash
sudo usermod -aG docker $USER
```
```bash
newgrp docker
```
### 16.Use the folowing commands to install kubectl

```bash
sudo snap install kubectl --classic
```
```bash
kubectl version --client
```
### 17.Use the following commands to install minikube
```bash
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
```
```bash
sudo install minikube-linux-amd64 /usr/local/bin/minikube
```
```bash
minikube version
```
### 18.Use the following minikube and kubectl commands
```bash
minikube start --driver=docker
```
```bash
minikube status
```
```bash
kubectl cluster-info
```
```bash
kubectl config view
```
```bash
kubectl get nodes
```
```bash
kubectl get pods
```
```bash
minikube dashboard
```
### 20.Use the following commands to deploy a nginx web server
```bash
kubectl create deployment nginx-web --image=nginx
```
```bash
kubectl expose deployment nginx-web --type NodePort --port=80
```
```bash
kubectl get deployment,pod,svc
```
### 21.Use the following commands to manage minikube addons
```bash
minikube addons list
```
```bash
minikube addons enable dashboard
```
```bash
minikube addons enable ingress
```
```bash
minikube dashboard --url
```
```bash
kubectl proxy --address='0.0.0.0' --disable-filter=true &
```
### 22.Replace server_ip with your public ip
```bash
http://server_ip:8001/api/v1/namespaces/kubernetes-dashboard/services/http:kubernetes-dashboard:/proxy/
```
### 23.
