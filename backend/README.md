# Backend - GoGym

Este é o backend do projeto GoGym, desenvolvido em Laravel.
Ele é responsável por gerenciar os dados da aplicação, autenticação de usuários e integração com o frontend via API REST.

# Instalação

Antes de começar, garanta que você tem instalado:

PHP 8.1+

Composer

MySQL (ou SQLite, se preferir)

Laravel CLI

## Entrar na pasta do projeto

    cd GoGym-backend

## Instalar as dependências do Laravel

    composer install


# Configuração do Ambiente

## 1. Copiar o arquivo de ambiente

    cp .env.example .env  

## 2. Gerar a chave da aplicação

    php artisan key:generate 

## 3. Configurar o banco de dados

🔹 Opção 1 — Usando MySQL

  No arquivo .env, edite as seguintes linhas com suas credenciais locais:
  
    DB_CONNECTION=mysql
    DB_HOST=127.0.0.1
    DB_PORT=3306
    DB_DATABASE=gogym
    DB_USERNAME=root
    DB_PASSWORD=


Depois, crie o banco de dados no MySQL:

     CREATE DATABASE gogym; 

🔹 Opção 2 — Usando SQLite

Crie o arquivo do banco:

    touch database/database.sqlite

E altere no .env:

    DB_CONNECTION=sqlite
    DB_DATABASE=/caminho/completo/para/database/database.sqlite

<hr>

# Criar as tabelas

Depois de configurar o banco, rode as migrations para criar as tabelas do sistema:

    php artisan migrate

Se quiser popular o banco com dados iniciais (caso tenha seeders configurados), use:

    php artisan db:seed

 <hr>   

# Executar o servidor

Inicie o servidor local do Laravel com:

    php artisan serve --host=0.0.0.0 --port=8000

O backend ficará disponível em:

    http://0.0.0.0:8000

ou, usando o IP local (para integração com o frontend):

    http://192.168.x.x:8000

<hr>

## Integração com o Frontend

Após o backend estar rodando, copie o IP da sua máquina com:

    hostname -I

Em seguida, vá até o frontend e substitua esse IP no arquivo:

`` src/service/app.ts``

### Dica

Se quiser resetar o banco e recriar todas as tabelas do zero:

      php artisan migrate:fresh --seed
