# Docker MySQL 5.7

___

Cria um serviço de banco de dados MySQL na versão 5.7 utilizado o Docker Compose.

## Dependências

___

* Docker Compose;
* Rede mercury-network.

## Instalação

___

Siga as etapas abaixo para um correto funcionamento do serviço.

### Rede mercury-network

Crie a rede **mercury-network** e conecte os seus serviços a ela para utilizar o banco de dados.

```docker
docker network create --driver bridge mercury-network
```

### Variáveis de ambiente

Renomeei o arquivo .env.example para .env e preencha com os dados solicitados.

```dotenv
MYSQL_USER=
MYSQL_PASSWORD=
MYSQL_ROOT_PASSWORD=
```

### Usuário de banco de dados

Abra o arquivo **set-grant-permission-to-user.sql** e, onde tem o texto **MYSQL_USER**, altere para o mesmo valor de **MYSQL_USER** do arquivo **.env**.

```sql
TRIGGER ON *.* TO 'MYSQL_USER'@'%';
```

### Serviço

```docker
docker-compose up -d
```

## Créditos

___

* [Giovanni Alves de Lima Oliveira](https://github.com/giovannialo) (Desenvolvedor)