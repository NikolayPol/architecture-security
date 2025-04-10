# Управление трафиком внутри кластера Kubernetes       

Как создать сетевую политику, разграничивающую сетевой трафик между подами?         
Настроить сетевые политики(network-policy.yaml).        
Метки labels выполняют функцию ролей для сервиса.    

Как присвоить метки сервису?     
```
kubectl run front-end-app --image=nginx --labels role=front-end --expose --port 80
```

Как применить сетевую политику?
```
kubectl apply -f network-policy.yaml
```

Как проверить трафик между сервисами?
```
kubectl run test-$RANDOM --rm -i -t --image=alpine -- sh
```





