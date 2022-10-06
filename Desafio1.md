Passo a passo executado para o desafio 1 do curso Docker Start:

- Inicialmente, foi solicitada a execução de um container com os seguintes parâmetros:
  - Baixar a imagem do Red Hat Training "httpd-parent", tag 2.4 da imagem;
  - Nomear o container como "httpd-basic";
  - Disponibilidade do serviço na porta 8080 da máquina e redirecionada para a porta 80 do container;
  - Container deve ser executado em background.

- O comando digitado para atender a todos os requisitos anteriores foi:

`docker run -d -p 8080:80 -name httpd-basic quay.io/redhattraining/httpd-parent:2.4`

- Em seguida, foi executado o comando localhost:8080 no navegador, para conferir se o container estava sendo executado corretamente.

- A segunda parte do exercício consiste em customizar a mensagem apresentada no navegador ao ser acessado o localhost:8080. Para isso, é necessário acessar o container que está sendo executado. O comando executado para isso foi:

`docker exec -it httpd-basic /bin/bash`

- Em seguida, foi verificada que na pasta var do container existe o arquivo index.html através do seguinte comando:

`cd /var/www/html`
  - Dentro da pasta var, ao digitar o comando "ls", foi listado todos os arquivos contidos nessa pasta, sendo o index.html esse arquivo.

- Utilizando o Vi, foi alterada a mensagem existente no arquivo index.html para a frase "Olá Mundo!", utilizando o seguinte comando dentro da pasta do container:

`vi index.html`

- Finalmente, o container em questão foi parado utilizando o comando:

`docker stop 5c40` 

(5c40 são os quatro primeiros dígitos da hash de ID do container). 
