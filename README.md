# Kubernetes

## Pods
- Para criar: 
```shell
kubectl create -f pod.yaml
```
- Para listar os existentes:
```shell
kubectl get pods
kubectl get pods -o wide
```
- Para deletar:
```shell
kubectl delete pod nginx-2
```

## ReplicaSet
- Para criar:
```shell
kubectl create -f replicasets/rs.yaml 
```
- Para listar os existentes:
```shell
kubectl get replicasets
```
- Para deletar:
```shell
kubectl delete replicaset frontend-rs-sjdpv
```

## Deployment

- Para criar:
```shell
kubectl create -f deployments/dp.yaml
```
- Para listar os existentes:
```shell
kubectl get deployment
kubectl describe deployment frontend-dp
```
- Para deletar:
```shell
kubectl delete -f deployments/dp.yaml
```
- Para atualizar:
```shell
kubectl apply -f deployments/dp.yaml 
kubectl set image deployment frontend-dp frontend-container=nginx:1.18
```
- Para listar o histórico de revisões
kubectl rollout history deployments/frontend-dp
```shell
```
- Para voltar para versões anteriores
```shell
kubectl rollout undo deployment/frontend-dp
kubectl rollout undo deployment/frontend-dp --to-revision=1
```

## Rede
Para se comunicar entre Pods podemos utilizar o endereço IP de cada pod.
- Para descobrir o endereço IP do pod:
```shell
kubectl describe pod postgres-pod
```
- Para entrar no pod:
```shell
kubectl exec -it webapp-pod -- bash
```