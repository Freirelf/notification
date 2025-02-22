## Laravel Notification Project
Este projeto implementa uma funcionalidade de notificação para informar os usuários sobre alterações na política de privacidade. O modal é exibido após o login, e o usuário deve aceitar os termos para continuar.

Requisitos
Docker

Docker Compose

Instalação
Siga os passos abaixo para configurar e rodar o projeto.

1. Clone o Repositório
Clone este repositório para o seu ambiente local:
```sh
git clone https://github.com/Freirelf/notification.git
cd laravel-notification
```

2. Configure o Ambiente
2.1. Crie o Arquivo .env
Copie o arquivo .env.example para .env:
```sh
cp src/.env.example src/.env
```
Edite o arquivo .env e configure as credenciais do banco de dados:
```sh
DB_CONNECTION=mysql
DB_HOST=db
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=root
DB_PASSWORD=secret
```
2.2. Dê Permissão à Pasta storage
Dê permissão à pasta storage para evitar problemas com permissões:
```sh
docker-compose exec app chmod -R 775 storage
docker-compose exec app chown -R www-data:www-data storage
```

3. Inicie os Containers
Suba os containers usando o Docker Compose:
```sh
docker-compose up -d
```
Isso iniciará os seguintes serviços:

app: Container do PHP-FPM com Laravel.
webserver: Container do Nginx.
db: Container do MySQL.
phpmyadmin: Container do phpMyAdmin (acessível em http://localhost:8081).

4. Instale as Dependências
Instale as dependências do Composer:
```sh
docker-compose exec app composer install
```

5. Execute as Migrations
Execute as migrations para criar as tabelas no banco de dados:
```sh
docker-compose exec app composer install
```

6. Acesse a Aplicação
Acesse a aplicação no navegador:
```sh
http://localhost:8080
```