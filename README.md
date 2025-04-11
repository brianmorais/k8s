# k8s

## Kubectl

### Criar pod a partir da linha de comando
```bash
kubectl run [pod-name] --image [image-name]
```

### Obter todos os pods do cluster
```bash
kubectl get pods
```

### Deletar pod pela linha de comando
```bash
kubectl delete pod [pod-name]
```

### Obter replica set
```bash
kubectl get replicaset
```

### Aplicar manifesto
```bash
kubectl apply -f [manifesto.yaml]
```
```bash
kubectl create -f [manifesto.yaml]
```
- Aplicar registro da alteração (depreciado)
    ```bash
    kubectl apply -f [manifesto.yaml] --record
    ```

### Deletar recursos por manifesto
```bash
kubectl delete -f [manifesto.yaml]
```

### Obter status de recursos
```bash
kubectl rollout status [deployment/nome-do-recurso]
```
- Exemplo: 
    ```bash
    kubectl rollout status deployment/my-deployement
    ```

### Obter todas as informações do cluster
```bash
kubectl get all
```

### Obter o histórico do deployment
```bash
kubectl rollout history [deployment/nome-do-deployment]
```

### Obter todas as informações do recurso
```bash
kubectl describe [recurso/nome-do-recurso]
```

### Alterar a vesão de uma imagem de container que esteja em execução
```bash
kubectl set image [deployment/nome-do-deployment] [nome-do-container=nginx:latest]
```
```bash
kubectl set image [deployment/nome-do-deployment/nome-do-container=nginx:latest]
```

### Voltar a versão do deployment para a anterior
```bash
kubectl rollout undo [deployment/nome-do-deployment]
```

### Voltar a versão do deployment para versão específica
```bash
kubectl rollout undo [deployment/nome-do-deployment] --to-version=0
```

### Executar um comando em um Pod específico, no caso abaixo acessando bash do Pod
```bash
kubectl exec -it [nome-do-pod] -- bash
```

## Minikube

### Iniciar o cluster
```bash
minikube start
```

### Deletar o cluster
```bash
minikube delete
```

### Definir o Docker como driver default
```bash
minikube config set driver docker
```

### Verificar o status do minikube
```bash
minikube status
```

### Obter a url de algum serviço
```bash
minikube service [nome-do-servico] --url
```

### Carregar imagem para o minikube (para utilizar imagens locais)
```bash
minikube image load [nome-da-imagem]
```

### Adicionar Docker registry dentro do minikube

- Ao inicializar o minikube, usar a flag --ports com a porta do registry a ser exposta

```bash
minikube start --ports 5000:5000
```

- Após a subida do minikube, fazer acesso ao mesmo via ssh

```bash
minikube ssh
```

- Dentro do minikube fazer a execução do container com o registry

```bash
docker run --name registy -d -p 5000:5000 --restart always registry:2
```

- As imagens geradas devem possuir o seguinte formato: `localhost:5000/<NOME_DA_IMAGEM>:<TAG>`

## K9S

### Instalação

#### Baixe o executável compactado
Faça o download do executável compactado no formato `.tar.gz` para a pasta temporária. Observação: Substituir pela versão desejada.
```bash
wget https://github.com/derailed/k9s/releases/download/v0.26.7/k9s_Linux_x86_64.tar.gz -O /tmp/k9s.tar.gz
```

#### Extraia
Extraia o executável de dentro do pacote `.tar.gz` para a pasta /tmp
```bash
tar -zxvf /tmp/k9s.tar.gz --directory /tmp/
```

#### Permissão de executar
Dê a permissão de excecução para o K9s
```bash
chmod +x /tmp/k9s
```

#### Mova o executável
Pra que você consiga invocar o comando `k9s` de qualquer lugar/diretório, você precisa mover ele pra uma pasta que esteja no `PATH` da sua máquina.  
Nesse caso: `/usr/local/bin/`

```bash
sudo mv /tmp/k9s /usr/local/bin/k9s
```
---
### Acessar o K9S
- Digitar o comando `k9s` no terminal

### Exibir todos os comandos
- Apertar a tecla `?`

### Exibir a barra de comandos
- Apertar a tecla `:`

### Filtrar os recursos listados
- Apertar a tecla `/`

### Alterar o contexto (cluster)
- Digitar o comando `ctx` na barra de comandos

### PortForward

#### Adicionar um PortForward
- Posicionar o cursor sobre o um pod ou service e apertar `Shift+f`

#### Listar todos os PortFowards relativos ao recurso
- Manter selecionado o recurso e apertar `f`

### Deletar o recurso
- Posicionar o cursor sobre o recurso e apertar a tecla `ctrl+d`

### Voltar um recurso
- Apertar a telcla `Esc`

### Exibir logs de um recurso
- Posicionar o cursor sobre um pod ou um deployment e apertar a tecla `l`

### Acessar o container do pod
- Posicionar o cursor sobre um pod e apertar a tecla `s`

### Sair do container do pod
- Apertar `ctrl+d`

### Exibir o yaml do recurso
- Posicionar o cursor sobre o recurso e apertar a tecla `y`

### Copiar o yaml do recurso
- Após exibir o yaml do recurso, apertar a tecla `c`

### Salvar o yaml do recurso em uma pasta temporária
- Após exibir o yaml do recurso, apertar `ctrl+s`

### Exibri o secret decodificado
- Posicionar o cursor sobre o secred e apertar a tecla `x`

### Exibir a descrição do recurso
-  Posicionar o cursor sobre o recurso e apertar a tecla `d`
