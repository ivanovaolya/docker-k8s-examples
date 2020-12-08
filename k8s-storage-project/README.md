# Node K8s deployment project 
Contains samples of https://www.udemy.com/course/docker-kubernetes-the-practical-guide.   
Section 13: Managing Data & Volumes with Kubernetes
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
> docker build -t k8s-simple-app:stories .
> docker tag k8s-simple-app:stories olyaaivanova/k8s-simple-app:stories
> docker push olyaaivanova/k8s-simple-app:stories
```
5. Create a deployment based on the image
```
> kubectl apply -f deployment.yml
```
6. Reach your application URL via
```
> minikube service story-service
```