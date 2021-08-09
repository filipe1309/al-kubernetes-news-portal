# Notes

> notes taken during the course

<!-- https://gitignore.io -->
<!-- https://github.com/github/gitignore -->

```sh
kubectl get nodes
kubectl run nginx-pod --image=nginx:latest
kubectl get nodes --watch
kubectl describe nginx-pod
kubectl edit pod nginx-pod
kubectl delete pod nginx-pod
kubectl delete -f primeiro-pod.yaml
```

### Minikube

https://minikube.sigs.k8s.io/docs/start/

```sh
minikube start
kubectl apply -f first-pod.yaml
kubectl get pods
```
