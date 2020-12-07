# Node K8s deployment project 
Contains samples of https://www.udemy.com/course/docker-kubernetes-the-practical-guide.   
Section 12: Kubernetes in Action
### Setup
1. Create and launch demo cluster using minikube - https://kubernetes.io/ru/docs/tasks/tools/install-minikube/
2. Install kubectl - https://kubernetes.io/ru/docs/tasks/tools/install-kubectl/
3. Create a local cluster (running as administrator)
```
> minikube start --vm-driver=docker
> minikube status
> minikube dashboard
```
4. Build an image locally and push it to DockerHub
```
> docker build -t k8s-simple-app:v1 .
> docker tag k8s-simple-app:v1 olyaaivanova/k8s-simple-app:v1
> docker push olyaaivanova/k8s-simple-app:v1
```
5. Create a deployment based on the image
```
> kubectl create deployment k8s-simple-app --image=olyaaivanova/k8s-simple-app:v1
> kubectl get deployments
```
6. Expose k8s deployment
```
> kubectl expose deployment k8s-simple-app --type=LoadBalancer --port=8080
```
7. Get URL by running as administrator 
```
> minikube service k8s-simple-app
```
8. Or you can use declarative approach
```
> kubectl apply -f deployment.yml
> kubectl apply -f service.yml
```