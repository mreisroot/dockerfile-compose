# Criação de container com imagem personalizada usando o Docker Compose

## Introdução

Neste projeto, há a criação de um container personalizado da API do site [VIACEP](https://viacep.com.br/exemplo/jquery/) utilizando um [Dockerfile](./Dockerfile) e um arquivo [docker-compose.yml](./docker-compose.yml).

O Dockerfile apresenta as instruções para a criação da imagem viacep, que incluem:

* Usar a imagem nginx:alpine como base
* Copiar o arquivo [index.html](./data/index.html) para o diretório /usr/share/nginx/html
* Expor a porta 80 do container

O docker-compose.yml realiza as seguintes tarefas:

* Definir o serviço webapp
* Definir o nome do container a ser criado como "viacep-api"
* Definir o nome da imagem a ser utilizada como "viacep"
* Realizar o build da imagem "viacep" a partir do diretório atual do projeto
* Mapear a porta 8080 do host para a porta 80 do container

O script [provision.sh](./provision.sh) executa o comando para subir o serviço webapp:

`docker compose up -d`

## Como usar este projeto

Torne o script provision.sh executável:

`chmod 755 provision.sh`

Execute o script:

`./provision.sh`

Digite o seguinte endereço na barra de pesquisa de um navegador de internet:

`localhost:8080`
