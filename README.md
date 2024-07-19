# Sistema de Clínica Veterinária

![Status do Projeto](https://img.shields.io/badge/status-em%20desenvolvimento-yellow)

Este projeto é um sistema de gerenciamento para uma clínica veterinária desenvolvido com Laravel 10. O sistema permite o cadastro de clientes e pets, cadastro de veterinários, agendamento de consultas e serviços realizados (como banho, tosa, vacina e outros), e a geração de relatórios.

## Funcionalidades

- **Cadastro de Clientes e Pets:** Permite o registro de clientes e seus respectivos pets.
- **Cadastro de Veterinários:** Permite o registro de veterinários que trabalham na clínica.
- **Agendamento de Consultas:** Permite o agendamento de consultas para os pets.
- **Serviços Realizados:** Registro de serviços realizados como banho, tosa, vacinas, etc.
- **Relatórios:** Geração de relatórios através do `ReportController`.

## Tecnologias Utilizadas

- **Laravel 10**
- **PHP 8.3**
- **Apache**
- **MariaDB**
- **Docker e Docker Compose**

## Requisitos

- Docker
- Docker Compose

## Instalação

1. Clone o repositório:
   
   ```bash
   git clone https://github.com/jacsonbleite/clinivetsys.git
   cd sistema-clinica-veterinaria
   ```

2. Configure o arquivo `.env`:
   
   ```bash
   cp .env.example .env
   ```

3. Gere a chave da aplicação Laravel:
   
   ```bash
   docker-compose exec app php artisan key:generate
   ```

4. Suba os contêineres Docker:
   
   ```bash
   docker-compose up -d
   ```

5. Instale as dependências do Laravel:
   
   ```bash
   docker-compose exec app composer install
   ```

6. Execute as migrações do banco de dados:
   
   ```bash
   docker-compose exec app php artisan migrate
   ```

## Utilização

- Acesse o sistema através da URL: `http://localhost:8000`

## Estrutura do Projeto

- `app/Models`: Contém os modelos Eloquent do Laravel.
- `app/Http/Controllers`: Contém os controladores do sistema.
- `database/migrations`: Contém as migrações do banco de dados.
- `routes/web.php`: Define as rotas da aplicação.
- `resources/views`: Contém as views Blade do Laravel.

## Docker

O projeto utiliza Docker e Docker Compose para facilitar o ambiente de desenvolvimento. O arquivo `docker-compose.yml` define os serviços necessários:

- `app`: Contém a aplicação Laravel com PHP 8.3 e Apache.
- `db`: Contém o banco de dados MariaDB.

### Comandos Úteis

- Subir os contêineres:
  
  ```bash
  docker-compose up -d
  ```

- Parar os contêineres:
  
  ```bash
  docker-compose down
  ```

- Executar comandos Artisan:
  
  ```bash
  docker-compose exec app php artisan <comando>
  ```

- Acessar o contêiner da aplicação:
  
  ```bash
  docker-compose exec app bash
  ```

- Alteração do arquivo /etc/apache2/sites-available/000-default.conf
  
  ```bash
  vi /etc/apache2/sites-available/000-default.conf
  ```
  
  ```
  <VirtualHost *:80>
    DocumentRoot /var/www/html/public
  
    <Directory /var/www/html/public>
        Options Indexes FollowSymLinks
        AllowOverride All
        Require all granted
    </Directory>
  </VirtualHost>
  ```

## Licença

Este projeto está licenciado sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.
