[![N|Solid](https://inscricoespos.unifacef.com.br/mbaesp/2018/images/logo_pos.png)]()

# Trabalho de Mensageria
### _Curso: Desenvolvimento de Aplicações Web Móveis Escaláveis_
### _Módulo: Mensageria com Kafka e RabbitMaq_
#### _Projeto: Realizar a implementação de um cenário de Parking-lot Queues baseado no exemplo 6 da aula (DLQ)._
#


## Requisistos Técnicos

Java 11  |  Docker 


## Execução

(x) No terminal, execute o comando abaixo, para subir o RabbitMQ: 
```
$  docker run -it --rm --name rabbitmq -p 5672:5672 -p 15672:15672 rabbitmq:3-management
```

(X) Em http://localhost:15672/ acesse o RabbitMQ com usuário e senha padrão: 
```
guest
```

(x) Agora no seu terminal, execute a aplicação em spring boot com o seguinte comando:
``` 
$ ./mwnw clean spring-boot:run
```

(x) Teste no terminal com curl, e verá as mensagens entrando na fila dlq e após algumas tentativas, ao atingir o limite de falhas, as mensagens serão direcionadas para outra fila de parking-lot:
``` 
$ curl http://localhost:8080/messages/send
```

Muito Obrigado! **_/\_**
