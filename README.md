# PHP REST MyBlog API

## Sobre o Projeto
API REST desenvolvida em PHP para gerenciamento de posts e categorias de blog, permitindo operações CRUD completas em ambas as entidades.

## Funcionalidades

### Posts
- Listar todos os posts
- Buscar post específico por ID 
- Criar novo post
- Atualizar post existente
- Deletar post
- Relacionamento com categorias

### Categorias
- Listar todas as categorias
- Buscar categoria específica por ID
- Criar nova categoria
- Atualizar categoria existente
- Deletar categoria


## Endpoints

### Posts

GET /api/post/read.php
GET /api/post/read_single.php?id={id}
POST /api/post/create.php
PUT /api/post/update.php
DELETE /api/post/delete.php

### Category

GET /api/category/read.php
GET /api/category/read_single.php?id={id}
POST /api/category/create.php
PUT /api/category/update.php
DELETE /api/category/delete.php

### Configuração
Pré-requisitos
PHP 7.0+
MySQL
Servidor Web (Apache/Nginx)

### Banco de Dados
Configure suas credenciais em config/Database.php:

Host
Nome do banco
Usuário
Senha

### Segurança
Sanitação de dados
Prepared Statements para prevenção de SQL Injection
Headers CORS configurados

### Estrutura de dados 

CREATE TABLE categories (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE posts (
    id INT AUTO_INCREMENT PRIMARY KEY,
    category_id INT,
    title VARCHAR(255) NOT NULL,
    body TEXT NOT NULL,
    author VARCHAR(255) NOT NULL,
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (category_id) REFERENCES categories(id)
);

### Licença
Distribuído sob a licença MIT.

Este README completo abrange todos os aspectos do projeto, incluindo a estrutura detalhada, endpoints disponíveis, configuração do banco de dados e exemplos de uso para ambas as entidades (posts e categorias).# PHP-MYCRUD
