Esse documento é o passo a passo seguido para a resolução do desafio 2, do curso de DockerStart.

1) Foi criado um arquivo dockerfile contendo os seguintes parâmetros:

`FROM redhat/ubi8:8.5
MAINTAINER 'Luíza Sabchuk  <luizasabchuk at gmail.com>'
LABEL description="A custom container for the Docker course"
RUN yum install -y httpd && \
    yum clean all
ENV PORT 8080
EXPOSE 80
CMD bash`

- Esses comandos direcionam as configurações iniciais do container
 2) Acessado o arquivo de configuração do Apache httpd.conf, utilizando os seguintes comandos:

 `docker exec -it 77b4 /bin/bash` #para acessar os arquivos do Container
 `cd /etc/httpd/conf` #para acessar a pasta que contém o arquivo a ser alterado
 `RUN --mount=type=cache,target=/run/httpd,gid=48,uid=48
  RUN --mount=type=cache,target=/etc/httpd/logs,gid=48,uid=48` #alteradas as propriedades das pastas /etc e /run.
 - Utilizado o editor Vi para alteração.

 3)
