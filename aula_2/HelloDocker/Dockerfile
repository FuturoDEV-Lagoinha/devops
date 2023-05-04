#imagem base
FROM openjdk:11

#definir o diretório de trabalho
WORKDIR /app

#copiamos nosso programa para a pasta de trabalho
COPY . /app/

#automatizamos a build do programa java
RUN javac HelloDocker.java

#ponto de entrada do conteiner
ENTRYPOINT ["java", "HelloDocker"]
