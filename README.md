# Como colocar dois ou mais sites no mesmo EC2 usando Docker

- Baixe os arquivos e edite conforme necessário

# A estrutura foi feita para ser usada considerando

- Nginx/Alpine
- Laravel 5 ou 6
- Banco de dados Mysql e/ou MongoDB em um Host separado (RDS)/(Atlas)
- Bando de dados Redis em um Container (caso não for usar é só desativar)

# Entendendo

- Instalar o docker e docker-compose em um EC2, expor a porta 80 para internet.
- Redirecionar o nome DNS cadastrado no arquivo do Nginx para o IP da EC2.
- Todos os sites podem responder para porta 80, o NGINX vai gerenciar as requisições e respostas.
- O Container Redis pode ser usado como banco de Alta Performance para Sessões ou informações Chave/Valor.
- Os códigos do site podem ser colocados dentro da pasta "Code", dentro dela vai outra pasta com o codigo de cada site, esta pasta é Interfaceada com o Docker, salvou dentro dela o docker ja lê e expõe instantaneamente.
- Os logs de Erro e Acesso são expostos para fora dos containers para pasta logs/nginx.
- Rodar o comando "docker-compose up -d" dentro da pasta que contém o arquivo "docker-composer.yml" para subir os containers, na primeira execução a imagem será baixada.
- Rodar o comando "docker-compose build" dentro da pasta que contém o arquivo "docker-composer.yml" se você modificar os arquivos "Dockerfile"
- Rodar o comando "docker-compose down" dentro da pasta que contém o arquivo "docker-composer.yml" para desligar os conteiners
- Para adicionar um novo site basta adicionar a estrutura dentro do arquivo de configuração do Nginx, editar o arquivo "docker-composer.yml" e duplicar editando as informações dos arquivos para gerar o container novo

## Objetivo

- Este, tem o objetivo de gerar containers para Stage e Desenvolvimento, para produção você deve avaliar o uso do seu site/sistema e dimensionar conforme necessario a máquina e os conteiners necessários

# TAGS
docker dockerfile docker-compose php laravel
como colocar mais de um conteiner usando o mesmo nginx webserver proxy reverso apache
como usar diversos sites em conteiner diferentes usando o mesmo nginx webserver proxy reverso apache