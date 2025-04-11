# Защита доступа к кластеру Kubernetes      


| Роль                                                          | Права роли                                          | Группы пользователей                                                             |
|---------------------------------------------------------------|-----------------------------------------------------|----------------------------------------------------------------------------------|
| Название роли, которое отвечает требованиям RBAC в Kubernets. | Укажите права, которые необходимо выдать этой роли. | Выделите группы пользователей в организации, которые нужно связать с этой ролью. |
| developer-role                                                | get, list, watch                                    | developers                                                                       |
| devops-role                                                   | get, list, watch, create, update, patch             | devops                                                                           |
| admin-role                                                    | get, list, watch, create, update, patch             | admins                                                                           |


Как создать namespace?
```
kubectl create ns development
```

Как посмотреть namespaces?
```
kubectl get namespace
```

Как создать пользователей?
```
kubectl config set-credentials developer
kubectl config set-credentials devops
kubectl config set-credentials admin
```

Как посмотреть пользователей?
Перейти в папку kubernetes и посмотреть config-файл
```
cd ~/.kube
ls -la
cat config
```

Как создать роли?
```
kubectl apply -f roles.yaml
```

Как посмотреть namespace роли?
```
kubectl get role -n development
```

Как посмотреть кластерные роли?
```
kubectl get clusterrole
```

Как назначить роли пользователям?
```
kubectl apply -f roles_binding.yaml
```

Как посмотреть назначенные роли пользователям?
```
kubectl get clusterrolebinding
kubectl get rolebinding -n development
```