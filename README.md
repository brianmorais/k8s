# k8s

## Kubectl

### Criar pod a partir da linha de comando
- kubectl run [pod-name] --image [image-name]

### Obter todos os pods do cluster
- kubectl get pods

### Deletar pod pela linha de comando
- kubectl delete pod [pod-name]

### Obter replica set
- kubectl get replicaset

### Aplicar manifesto
- kubectl apply -f [manifesto.yaml]
- kubectl create -f [manifesto.yaml]
- Aplicar registro da alteração (depreciado)
    - kubectl apply -f [manifesto.yaml] --record

### Deletar recursos por manifesto
- kubectl delete -f [manifesto.yaml]

### Obter status de recursos
- kubectl rollout status [deployment/nome-do-recurso]
    - Exemplo: kubectl rollout status deployment/my-deployement

### Obter todas as informações do cluster
- kubectl get all

### Obter o histórico do deployment
- kubectl rollout history [deployment/nome-do-deployment]

### Obter todas as informações do recurso
- kubectl describe [recurso/nome-do-recurso]

### Alterar a vesão de uma imagem de container que esteja em execução
- kubectl set image [deployment/nome-do-deployment] [nome-do-container=nginx:latest]
- kubectl set image [deployment/nome-do-deployment/nome-do-container=nginx:latest]

### Voltar a versão do deployment para a anterior
- kubectl rollout undo [deployment/nome-do-deployment]

### Voltar a versão do deployment para versão específica
- kubectl rollout undo [deployment/nome-do-deployment] --to-version=0

### Executar um comando em um Pod específico, no caso abaixo acessando bash do Pod
- kubectl exec -it [nome-do-pod] -- bash

## Minikube

### Iniciar o cluster
- minikube start

### Deletar o cluster
- minikube delete

### Definir o Docker como driver default
- minikube config set driver docker

### Verificar o status do minikube
- minikube status

### Obter a url de algum serviço
- minikube service [nome-do-servico] --url

### Carregar imagem para o minikube (para utilizar imagens locais)
- minikube image load [nome-da-imagem]
