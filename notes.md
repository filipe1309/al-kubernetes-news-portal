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

## CLASS-3

### Minikube

https://minikube.sigs.k8s.io/docs/start/

```sh
minikube config set driver docker #wsl2
minikube start
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v0.44.0/deploy/static/provider/cloud/deploy.yaml
minikube tunnel
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

## CLASS-4

```sh
kubectl get pods -o wide
kubectl apply -f pod-1.yaml
kubectl apply -f pod-2.yaml
kubectl appapply -f pod-2.yaml # update pod-2 config
kubectl describe pod pod-2
kubectl apply -f svc-pod-2.yaml
kubectl get services
kubectl get svc
kubectl exec -it pod-1 -- bash
curl 10.108.226.16:80
```

```sh
kubectl exec -it news-portal -- bash
curl 10.104.42.9:80
kubectl get nodes -o wide
```

-> tail -1 /etc/resolv.conf | cut -d' ' -f2 # wsl host ip
-> kubectl get svc -A
-> kubectl -n default port-forward --address 0.0.0.0 svc-pod-1 30000:30000

-> minikube dashboard
http://127.0.0.1:41795/api/v1/namespaces/kubernetes-dashboard/services/http:kubernetes-dashboard:/proxy/#/overview?namespace=default
