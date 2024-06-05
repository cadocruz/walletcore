<h1 align="center">
  EDA - Event Driven Architecture com Go (WalletCore)
</h1>

Projeto de criação de uma wallet do curso de EDA - Event Driven Architecture da FullCycle

## Tecnologias
 
- [Golang](https://go.dev/)
- [Apache Kafka](https://kafka.apache.org/)
- [Docker Compose](https://docs.docker.com/compose/)
- [MySQL](https://www.mysql.com/)

## Como Executar

- Clonar repositório git:
  ```
    git clone https://github.com/cadocruz/walletcore.git
  ```
- Executar o Docker
  ```
  docker-compose up -d
  ```
- Acessar o mysql 
  ```
  mysql --host=localhost --port=3306 -u root -p wallet
  ```
- Rodar os scripts do banco de dados
  ```
  Create table clients (id varchar(255), name varchar(255), email varchar(255), created_at date);
  Create table accounts (id varchar(255), client_id varchar(255), balance int, created_at date);
  Create table transactions (id varchar(255), account_id_from varchar(255), account_id_to varchar(255), amount int, created_at date);
  ```
- Acessar o Control Center do Kafka em http://localhost:9021/ e criar 2 topics:
  ```
  transactions e balances
  ```
- Chamar a API disponível em /api/client.http
  
- Update na tabela accounts, pois o serviço não permite adicionar balance ao criar uma account (TODO)
  ```
  update accounts set balance=1000 where id=[ID DA CONTA];
  ```
  
  
