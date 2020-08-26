# 강사 Anderson jo [http://incredible.ai/]

# gcp touring

## create ubuntu 20.04LTS sever
 - `$ sudo apt update`

## install nginx
 - `$ sudo apt install nginx`
 
## install python3-pip
 - `$ sudo apt install python3-pip`

## install jupyter notebook and setup
 - `$ sudo pip3 install numpy pandas jupyter notebook`
 - `jupyter notebook password`
 - `jupyter notebook --ip 0.0.0.0 --port 8888`
 
## create storage server

## create gcp jupyter notebook
 > install tensorflow 2.3
 

## create model 
 - `sudo pip3 install matplotlib sklearn pandas numpy`
 - jupyter notebook   
  ```
  %pylab inline   
  
  import numpy as np   
  from sklearn import datasets, linear_model   
  from sklearn.metrics import mean_squared_error, r2_score

  x_data, y_data = datasets.load_diabetes(return_X_y=True)

  x_data = x_data[:, np.newaxis, 2]

  x_train = x_data[:-20]
  y_train = y_data[:-20]
  x_test = x_data[-20:]
  y_test = y_data[-20:]

  print(x_test.shape)
  print(y_test.shape)
  
  regr = linear_model.LinearRegression()
  regr.fit(x_train, y_train)
  
  y_pred = regr.predict(x_test)

  print('MSE:', mean_squared_error(y_test, y_pred))
  print('R2Score:', r2_score(y_test, y_pred))
  
  scatter(x_test, y_test, color='black')
  plot(x_test, y_pred, color='blue', linewidth=2)
  ```
  
 

# docker

## create ubuntu 20.04LTS sever
 - `$ sudo apt update`

## install nginx
 - `$ sudo apt install nginx`
 
## setup the repository [https://docs.docker.com/engine/install/ubuntu/]
 -  ```
    $ sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
    ```
 - `curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -`
 - ```
   $ sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
   ```
## install docker engine
 - `$ sudo apt-get update`
 - `$ sudo apt-get install docker-ce docker-ce-cli containerd.io`
  
 - `$ sudo groupadd docker`
 - `$ sudo usermod -aG docker $USER`

 - `$ sudo aa-status`
 - `$ sudo systemctl disable apparmor.service --now`
 - `$ sudo service apparmor stop`
  
 - `$ sudo reboot`
  
## run docker hello-world
 - `docker run hello-world`
 - `docker info`

## docker test
 - `docker ps -a`
 - `docker pull ubuntu:20.04`
 - `docker images`
 - `docker run --name haha -it ubuntu:20.04 /bain/bash`
 - `docker run -d --name daemon_ubuntu ubuntu:20.04 /bain/bash`
 
## pull docker nginx image
 - `docker pull nginx`
 - `docker run --name docker-nginx -d -p 8080:80 nginx`
 
## create Dockerfile
 - `docker build -t myfirstcontainer .`

## clear docker processes
 - `docker container prune`
 
## clear docker images
 - `docker images rmi $(docker images -qa)`


# kubenetes

## instal minikube ubuntu[https://kubernetes.io/docs/tasks/tools/install-minikube/]
 - ```
   curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 
   && chmod +x minikube
   ```
 - ```
   sudo mkdir -p /usr/local/bin/
   sudo install minikube /usr/local/bin/
   ```
 - `minikube status`
 - `minikube start`
 > source <(kubectl completion bash)
 >
 > alias k=kubectl   
 > complete -F __start_kubectl k
   
 ## install kubectl ubuntu[https://kubernetes.io/docs/tasks/tools/install-kubectl/]
  - `sudo snap install kubectl --classic
  - `kubectl version`
  - `k get nodes`
  - `k cluster-info`
  
 ## apply Deployment.yaml (example)
  - `kubectl apply -f https://k8s.io/examples/controllers/nginx-deployment.yaml`
 
 ## port forwarding
  - `kubectl port-forward "PODS_NAME" 5000:80 --address 0.0.0.0
