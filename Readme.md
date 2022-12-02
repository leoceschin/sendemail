# Microserviço de envio de e-mail
Este é um microserviço de envio de e-mail utlizando o SMTP do Gmail.

## Configuração
O arquvo /src/main/resources/application.properties deve estar configurado da seguinte maneira:
```
server.port=8080

spring.datasource.url=jdbc:postgresql://localhost:5432/{nome do banco de dados}
spring.datasource.username={nome do usuario}
spring.datasource.password={senha do usuario}
spring.jpa.hibernate.ddl-auto=update

spring.mail.host=smtp.gmail.com
spring.mail.port=587
spring.mail.username={endereço de email}
spring.mail.password={senha de 16 dígitos gerado na área de segurança do Gmail}
spring.mail.properties.mail.smtp.auth=true
spring.mail.properties.mail.smtp.starttls.enable=true
```

## Envio
Enviamos o Json do DTO pela rota http://localhost:8080/sending-email
```
{
	"ownerRef": "Leona",
	"emailFrom": "{email de origem}",
	"emailTo":"{email de destino}",
	"subject":"Teste de envio",
	"text":"Este é um teste de envio de email via spring"
}
```

Temos como retorno o Status Code 200 com o seguinte response:
```
{
	"emailId": "208a6d69-1eb3-4159-88b8-50c465511aa2",
	"ownerRef": "Leona",
	"emailFrom": "{email de origem}",
	"emailTo": "{email de destino}",
	"subject": "Teste de envio",
	"text": "Este é um teste de envio de email via spring",
	"sendDateEmail": "2022-12-02T16:01:06.31398",
	"statusEmail": "SENT"
}
```
