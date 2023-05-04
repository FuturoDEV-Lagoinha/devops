## Bora rodar um site com Apache em um servidor EC2?

### Criando instância ec2

    Requisitos:

    - Security Group
    - Key pair

#### Passo a passo

    - Sobe a instância EC2;
    - Conecta na máquina localmente via ssh;
    - Instala o docker : sudo amazon-linux-extras install docker
    - Start docker service: sudo service docker start
    - Permissão para ec2-user: sudo usermod -a -G docker ec2-user
    - Settar inicialização automatica do docker: sudo chkconfig docker on
    - Reinicia servidor: sudo reboot
    - reconecta na máquina via ssh

    - Cria o site
        mkdir site
        cd site
        mkdir html
        cd html
        nano home.html
            - adiciona no html: <h3>Hello Ec2!</h3>
            - ctrl+x
            - y
            - enter

    - Criar dockerfile
        cd ..
        nano Dockerfile
            - adiciona no Dockerfile:

            FROM httpd:2.4

            COPY ./html/ /usr/local/apache2/htdocs/

    -buildar imagem: docker build -t <nome-da-imagem> .

    -rodar imagem: docker run -d --name <nome-do-conteiner> -p 80:80 <nome-da-imagem>

