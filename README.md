# <p align="center">News Portal with Kubernetes 📰</p>

<p align="center">
    <img src="https://img.shields.io/badge/Tools-Kubernetes-informational?style=flat-square&logo=kubernetes&color=326CE5" alt="Kubernetes" />
    <img src="https://img.shields.io/badge/Tools-Docker-informational?style=flat-square&logo=docker&color=2496ED" alt="Docker" />
</p>

## 💬 About

This project was developed following Alura's Kubernetes courses.

Courses:

- [Kubernetes: Pods, Services e ConfigMaps](https://cursos.alura.com.br/course/kubernetes-pods-services-configmap)
- [Kubernetes: Deployments, Volumes e Escalabilidade](https://cursos.alura.com.br/course/kubernetes-deployments-volumes-escalabilidade)

```
[EXTERNAL] -> [CLUSTER]
-> [SERVICE NodePort NEWS PORTAL] -> [POD NEWS PORTAL]
-> [SERVICE NodePort NEWS SYSTEM] -> [POD NEWS SYSTEM] -> [SERVICE ClusterIP NEWS DB] -> [POD NEWS DB]
```

## :computer: Technologies

- [Kubernetes](https://kubernetes.io/)
- [Docker](https://www.docker.com/)

## :scroll: Requirements

- [Kubernetes](https://kubernetes.io/)
- [Docker](https://www.docker.com/)

## :cd: Installation

```sh
git clone git@github.com:filipe1309/al-kubernetes-news-portal.git
```

```sh
cd al-kubernetes-news-portal
```

## :runner: Running

### Pods

```sh
# Start the Pods
kubectl apply -f news-portal.yaml
kubectl apply -f news-system.yaml
kubectl apply -f news-db.yaml
```

### Services

```sh
# Start the NodePort/ClusterIP services
kubectl apply -f svc-news-portal.yaml
kubectl apply -f svc-news-system.yaml
kubectl apply -f svc-news-db.yaml
```

### Config Maps

```sh
# Start ConfigMaps
kubectl apply -f news-portal-configmap.yaml
kubectl apply -f news-system-configmap.yaml
kubectl apply -f news-db-configmap.yaml
```

> Access News Portal: http://localhost:30000/
> Access News System (admin/admin): http://localhost:30001/

## License

[MIT](https://choosealicense.com/licenses/mit/)

## About Me

<p align="center">
    <a style="font-weight: bold" href="https://www.linkedin.com/in/filipe1309/">
    <img style="border-radius:50%" width="100px; "src="https://avatars.githubusercontent.com/u/2081014?s=60&v=4"/>
    </a>
</p>

---

<p align="center">
    Done with ♥ by <a style="font-weight: bold" href="https://www.linkedin.com/in/filipe1309/">Filipe Leuch Bonfim</a> 🖖
</p>

---

> @ Generated with [ShubcoGen™](https://github.com/filipe1309/shubcogen)
