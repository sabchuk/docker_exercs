Esse documento é o passo a passo seguido para a resolução do desafio 2, do curso de DockerStart.

1) Foi criado um arquivo dockerfile contendo os seguintes parâmetros:

`FROM redhat/ubi8:8.5
LABEL email="luizasabchuk@gmail.com"
RUN yum install -y httpd
ENV PORT 8080
RUN sed -ri -e "/^Listen 80/c\Listen ${PORT}" /etc/httpd/conf/httpd.conf && \
    chown -R apache:apache /etc/httpd/logs/ && \
    chown -R apache:apache /run/httpd/
COPY /src/index.html /var/www/html/
EXPOSE 80
CMD ["httpd", "-D", "FOREGROUND"]`

- Esses comandos direcionam as configurações iniciais do container

 2) Ao digitar localhost:20080 no navegador, foi possível visualizar a mensagem "Esse é o meu apache!".
