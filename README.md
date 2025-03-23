# Fake Shop
Implementação de uma aplicação em um cluster kubernetes da DigitalOcean através de um pipeline CI/CD usando GitHub Actions

## Instruções
Ao fazer um novo commit, o pipeline automaticamente irá:

- Buscar os arquivos do repositório utilizando actions/checkout
- Autenticar com o Docker Hub utilizando docker/login-action@v3.4.0
- Construir uma imagem à partir do diretório /src e o arquivo /src/Dockerfile, e fazer o upload da imagem para o Docker Hub utilizando docker/build-push-action@v6.15.0
- Realizar a configuração do kubeconfig utilizando azure/k8s-set-context@v4
- Realizar o deploy da nova imagem no cluster utilizando Azure/k8s-deploy@v5

## deployment.yaml
O arquivo de manifesto do deployment em k8s/deployment.yaml

## main.yml
O arquivo do workflow no GitHub Actions, em .github/worklfows/main.yml

## Variável de Ambiente
DB_HOST	=> Host do banco de dados PostgreSQL.

DB_USER => Nome do usuário do banco de dados PostgreSQL.

DB_PASSWORD	=> Senha do usuário do banco de dados PostgreSQL.

DB_NAME	=>	Nome do banco de dados PostgreSQL.

DB_PORT	=>	Porta de conexão com o banco de dados PostgreSQL.

FLASK_APP => Arquivo da aplicação Flask

