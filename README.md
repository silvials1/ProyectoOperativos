# Sistemas Operativos
Implementación de un repositorio privado en k8s

## Push de contenedor a repositorio privado

- docker images
- docker commit -m "Example" a426516eef96 jpoou/my-repo:lastest
- docker login
- docker push jpoou/my-repo:lastest

## Implementacion de un repositorio privado en k8s

- DOCKER_REGISTRY_SERVER=docker.io
- DOCKER_USER=user_name
- DOCKER_EMAIL=micorreo@hotmail.com
- DOCKER_PASSWORD=password
- kubectl create secret docker-registry myregistrykey   --docker-server=$DOCKER_REGISTRY_SERVER   --docker-username=$DOCKER_USER   --docker-password=$DOCKER_PASSWORD   --docker-email=$DOCKER_EMAIL
- kubectl get nodes
### Crear archivo local.yaml:

```
apiVersion: v1
kind: Pod
metadata:
  name: operativos-final
spec:
  containers:
  - name: operativos-final
    image: josecarta/k8s:4
	imagePullPolicy: Always
```
- kubectl create -f local.yaml 
- kubectl get pods (Para ver el estado de todos los pods del namespaces default)
- kubectl describe pod operativos-final
- kubectl get pods

