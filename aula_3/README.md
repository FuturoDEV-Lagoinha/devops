### Escalabilidade e Elasticidade

<br/><img src="/aula_3/img/scalability.png" width="600" height="500">

#### Amazon ECS

1. Configurar cluster ECS com máquinas t2.micro (free tier)

2. Configurar Task para seu cluster viinculando à imagem oficial do Webserver Apache

3. Configurar Service para sua task do Apache no cluster;

     - Configurar Load Balancer;

4. Para validar a execução do Apache no cluster faça Requisição HTTP no DNS do Load Balancer.

##### Arquitetura do Amazon ECS
<br/><img src="/aula_3/img/ecs-architecture.png" width="600" height="500">


#### Kubernetes (minikube)

    - [instalar](https://minikube.sigs.k8s.io/docs/start/) minikube 

    - Subir cluster

        minikube start --cpus 4 --memory 4000 --disk-size 10

    - verificar cluster 

        kubectl cluster-info 

    - verificar kubernetes

        kubectl describe service kubernetes

    - verificar pods

        kubectl get pods

    - bora levantar um pod da nossa imagem local (do programa helloDocker.java)

    - com a imagem docker já buildada execute:

        minikube image load nomeImagem
    - para verificar se a imagem está no registry do minikube

        minikube image ls --format table
    
    - para executar a imagem um pod de nosso cluster:

         kubectl run nome-container --image=nome-image --image-pull-policy=Never --restart=Never

    - verifique se o pod rodou
        
         kubectl get pods

    - verifique o output do pod
        
        kubectl logs nome-container

##### Diagrama do Exercício com Kubernetes

<br/><img src="/aula_3/img/dev-to-k8s.png" width="600" height="500">