## Projeto prático DevOps aula 1

### Executar programa java na AWS Lambda.
Para buildar o projeto:
    - na pasta raiz do projeto
    executar no terminal: mvn clean package

**requerimentos**:
maven.compiler.source 11
maven.compiler.target 11
maven-shade-plugin 3.2.4


### AWS Lambda

- criar função lambda
- settar java run time 11
- upar programa buildado .jar (pasta "target")
- mudar entry point da lambda para dev.cloud.HelloCloud::handleRequest
- testar
    - passar string com valor "nome" para evento de teste.