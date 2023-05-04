## Criando nossa primeira imagem Docker

### Hello Docker!

- Buildar:
    - na pasta /HelloDocker/ execute o comando: docker build -t <nome_da_imagem> .

- Executar o container: 
    docker run <nome_da_imagem>


## Subir imagem docker para AWS ECR

- criar repositório: aws ecr create-repository --repository-name hello --region us-east-1

- Executar comando de login no ECR:
    
    aws ecr get-login-password --region <regiao> | docker login --username AWS --password-stdin <aws_account>.dkr.ecr.<regiao>.amazonaws.com

- Executar build:
    
    docker build -t <nome_da_imagem> .

- Executar tag:

    docker tag <nome_da_imagem>:latest <aws_account>.dkr.ecr.<regiao>.amazonaws.com/<nome_da_imagem>:latest


- Executar push:

    docker push <aws_account>.dkr.ecr.<regiao>.amazonaws.com/<nome_da_imagem>:latest


