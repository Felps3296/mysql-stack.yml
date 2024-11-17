<p align="center">
  <img src="https://www.docker.com/wp-content/uploads/2022/03/horizontal-logo-monochromatic-white.png" alt="Docker Logo" width="300">
</p>

# MySQL + phpMyAdmin Stack

Este repositório configura um ambiente de desenvolvimento com **MySQL** e **phpMyAdmin** usando contêineres Docker Compose. A configuração gerenciamento com banco de dados MySQL com facilidade usando a interface gráfica do phpMyAdmin.

## Tecnologias

- ![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
- ![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
- ![phpMyAdmin](https://img.shields.io/badge/phpMyAdmin-6C78AF?style=for-the-badge&logo=phpmyadmin&logoColor=white)

## Pré-requisitos

- **Docker** instalado
- **Docker Compose** instalado

## Estrutura do Projeto

- **.data/**: Diretório de armazenamento de dados para persistência do MySQL.
- **mysql-stack.yml**: Arquivo Docker Compose para configurar e iniciar os contêineres.

## Configuração dos Contêineres

### MySQL

- **Imagem**: `mysql:8.0`
- **Nome do Contêiner**: `dev-mysql`
- **Porta**: `3306` (localhost) mapeada para `3306` (contêiner)
- **Credenciais**:
  - Banco de Dados: `mydatabase`
  - Senha Root: `1234567`
- **Volume**: `./.data/mysql/data` (persistência de dados)

### phpMyAdmin

- **Imagem**: `phpmyadmin/phpmyadmin`
- **Nome do Contêiner**: `dev-phpmyadmin`
- **Porta**: `8081` (localhost) mapeada para `80` (contêiner)
- **Configuração**:
  - Host MySQL: `mysql-docker`
  - Senha Root: `1234567`

### Rede

- **Nome da Rede**: `dev-network`
- **Driver**: `bridge`

## Como Usar

1. **Inicie os contêineres**:
   No terminal, navegue até a pasta do projeto e execute:

   ```bash
   docker-compose -f mysql-stack.yml up -d

<h2>✍️ Autor</h2>

<a href="https://github.com/Felps3296">
  <img loading="lazy" src="https://avatars.githubusercontent.com/u/64935845?v=4" width="115" alt="Felipe Viana Reis">
</a>
<br>
<sub><b>Felipe Viana Reis</b></sub>
<br>
