# Microserviço de envio de e-mail
Este é um microserviço de envio de e-mail utlizando o SMTP do Gmail.

## Configuração
O arquvo /src/main/resources/application.properties deve estar configurado da seguinte maneira:
```
server.port=8080

spring.datasource.url=jdbc:postgresql://localhost:5432/ms-email
spring.datasource.username={nome do usuario}
spring.datasource.password={senha do usuario}
spring.jpa.hibernate.ddl-auto=update
```

