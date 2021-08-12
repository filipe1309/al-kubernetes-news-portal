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
kubectl apply -f svc-pod-1.yaml
```

-> tail -1 /etc/resolv.conf | cut -d' ' -f2 # wsl host ip
-> kubectl get svc -A
-> kubectl -n default port-forward --address 0.0.0.0 svc-pod-1 30000:30000

-> minikube dashboard
http://127.0.0.1:41795/api/v1/namespaces/kubernetes-dashboard/services/http:kubernetes-dashboard:/proxy/#/overview?namespace=default

## CLASS-5

```sh
kubectl delete pods --all
kubectl delete svc --all
```

```sh
kubectl apply -f news-portal.yaml
kubectl apply -f svc-news-portal.yaml
```

```sh
kubectl apply -f news-system.yaml
kubectl apply -f svc-news-system.yaml
```

## CLASS-6

```sh
kubectl delete pod news-db
kubectl apply -f news-db.yaml
kubectl get pods
kubectl exec -it news-db -- bash
mysql -uroot -p
show databases;
use empresa;
show tables;
```

### Config Map

```sh
kubectl apply -f news-db-configmap.yaml
kubectl get configmap
kubectl describe configmap news-db-configmap
kubectl delete pod news-db
kubectl apply -f news-db.yaml
```

```sh
kubectl apply -f news-system-configmap.yaml
kubectl delete pod news-system
kubectl apply -f news-system.yaml
```

```sh
kubectl apply -f news-portal-configmap.yaml
kubectl delete pod news-portal
kubectl apply -f news-portal.yaml
```

## COURSE-2

## CLASS-1

```sh
kubectl apply -f news-portal-replicaset.yaml
kubectl get pods
kubectl get replicasets
kubectl get rs --watch
```

```sh
kubectl apply -f nginx-deployment.yaml
kubectl get deployments
kubectl rollout history deployment nginx-deployment
kubectl apply -f nginx-deployment.yaml --record
kubectl annotate deployment nginx-deployment kubernetes.io/change-cause="Set nginx with latest version"
kubectl describe pod nginx-deployment-7d684cf94b-7qtb7
kubectl rollout  undo deployment nginx-deployment --to-revision=2
kubectl delete deployment nginx-deployment
kubectl delete -f news-portal-replicaset.yaml
```

```sh
kubectl apply -f news-portal-deployment.yaml
kubectl rollout history deployment news-portal-deployment
kubectl annotate deployment news-portal-deployment kubernetes.io/change-cause="Set news portal with version 1"
```

```sh
kubectl delete pod news-system
kubectl apply -f news-system-deployment.yaml
kubectl rollout history deployment news-system-deployment
kubectl annotate deployment news-system-deployment kubernetes.io/change-cause="Set news system with version 1"
```

```sh
kubectl delete pod news-db
kubectl apply -f news-db-deployment.yaml
kubectl rollout history deployment news-db-deployment
kubectl annotate deployment news-db-deployment kubernetes.io/change-cause="Set news db with version 1"
```

## CLASS-2

### Volume

```sh
kubectl delete pods,svc,deployments --all
kubectl apply -f pod-volume.yaml
kubectl exec -it pod-volume --container nginx-container -- bash
cd first-volume
touch first-volume-file.txt
kubectl describe pod pod-volume.yaml
```

### Persistent Volume

No GCP

```sh
kubectl apply -f gcp-persistent-volume.yaml
kubectl get pv
kubectl apply -f gcp-persistent-volume-claim.yaml
kubectl get pvc
```
