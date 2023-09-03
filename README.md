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

## K9S

### Acessar o K9S
- Digitar o comndo **k9s** no terminal

### Exibir todos os comandos
- Apertar a tecla **?**

### Exibir a barra de comandos
- Apertar a tecla **:**

### Filtrar os recursos listados
- Apertar a tecla **/**

### Alterar o contexto (cluster)
- Digitar o comando **ctx** na barra de comandos

### PortForward

#### Adicionar um PortForward
- Posicionar o cursor sobre o um pod ou service e apertar **Shift+f**

#### Listar todos os PortFowards relativos ao recurso
- Manter selecionado o recurso e apertar **f**

### Deletar ou recurso
- Posicionar o cursor sobre o recurso e apertar a tecla **ctrl+d**

### Voltar um recurso
- Apertar a telcla **Esc**

### Exibir logs de um recurso
- Posicionar o cursor sobre um pod ou um deployment e apertar a tecla **l**

### Acessar o container do pod
- Posicionar o cursor sobre um pod e apertar a tecla **s**

### Sair do container do pod
- Apertar **ctrl+d**

### Exibir o yaml do recurso
- Posicionar o cursor sobre o recurso e apertar a tecla **y**

### Copiar o yaml do recurso
- Após exibir o yaml do recurso, apertar a tecla **c**

### Salvar o yaml do recurso em uma pasta temporária
- Após exibir o yaml do recurso, apertar **ctrl+s**

### Exibri o secret decodificado
- Posicionar o cursor sobre o secred e apertar a tecla **x**

### Exibir a descrição do recurso
-  Posicionar o cursor sobre o recurso e apertar a tecla **d**
