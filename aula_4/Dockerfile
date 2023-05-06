FROM openjdk:11

WORKDIR /app

COPY . /app/

RUN javac HelloDocker.java

#alteração
ENTRYPOINT ["java", "Hello"]