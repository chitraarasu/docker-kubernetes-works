FROM node:14-alpine

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 8080

CMD [ "node", "app.js" ]


# This will run kubernets on docker container you can also use virtual box. 
# minikube start --driver=docker 

# this will lauch the kubernets dashboard
# minikube dashboard 

# Kubernets cluster can't about access the local machine image because it is running as a seprate machine. so, Need to push the image to dockerhub otherwise kubenets cluster don't know about image.
# docker build -t chitraarasu/kube-first-app .

# Deployment Object ----------------------

# This cmd create deployment object by moving the image to manager node
# kubectl create deployment first-app --image=chitraarasu/kube-first-app 

# To see the running pods
# kubectl get pods

# Scale Object ----------------------

# Now image moved to deployment but still we can't access the pod from outside world because ip of the each pod will change at every update or restart.
# To fix that need to create service object
# type = ClusterIp -> this is the default type. Ip will change everytime.
# type = NodePort -> this will expose the worker node IP.
# type = LoadBalancer -> we are using LoadBalancer type to utilize LoadBalancer. This will not change the IP also this will distribute the incomming traffic.
# kubectl expose deployment first-app --type=LoadBalancer --port=8080

# this cmd will list the services
# kubectl get services

# this will provide the URL and launch site on browser.
# minikube service first-app

# navigate to /error and the pod will crach and it will be restart automatically you can see that from bellow cmd.
# kubectl get pods

# Scale ----------------------

# This cmd will scale the pod to given count. 
# kubectl scale deployment/first-app --replicas=3

# Update new version ----------------------

# Need to build image with new tag version
# docker build -t chitraarasu/kube-first-app:2 .
# docker push chitraarasu/kube-first-app:2
# kubectl set image deployment/first-app kub-first-app=chitraarasu/kube-first-app:2
# kubectl rollout status deployment/first-app # Check the status of rollout.

# Undo new version ----------------------

# kubectl rollout undo deployment/first-app # undo the latest deployment
# kubectl rollout history deployment/first-app # This is used to get rollout history.
# kubectl rollout history deployment/first-app --revision=3 # This is used to get rollout history.

# Delete objects ----------------------

# kubectl delete service first-app
# kubectl delete deployment first-app