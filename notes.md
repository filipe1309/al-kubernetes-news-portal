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
```

## CLASS 3

### Minikube

https://minikube.sigs.k8s.io/docs/start/

```sh
minikube start
kubectl apply -f first-pod.yaml
kubectl get pods
kubectl delete -f first-pod.yaml
```

```sh
kubectl apply -f news-portal.yaml
kubectl get pods --watch
kubectl describe pod news-portal
kubectl exec -it news-portal -- bash
root@news-portal:/var/www/html# curl localhost
```
