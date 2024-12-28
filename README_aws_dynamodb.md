# AWS DynamoDB

## Instalacja lokalna

1. Instalacja AWS CLI:

```sh
sudo snap install aws-cli --classic
aws --version
```

2. Pobranie obrazu Docker-a dla DynamoDB Local:
   
```sh
sudo docker pull amazon/dynamodb-local
```

2. Uruchomienie kontenera DynamoDB Local

Kontener uruchomiony jest na porcie 
```bash
sudo docker run --rm -p 8000:8000 amazon/dynamodb-local
```

3. Konfiguracja AWS:

```bash
aws configure
```

Nalezy uzupełnić region ``` eu-north-1 ``` oraz outpiut format na json

```
AWS Access Key ID [None]: TESTKLUCZID
AWS Secret Access Key [None]: TESTSEKRETNYKLUCZDOSTEPU123
Default region name [None]: us-west-2
Default output format [None]: json
```

4. Listowanie tabel

```bash
aws dynamodb list-tables --endpoint-url http://localhost:8000
```

5. Utworzenie tabeli w bazie AWS DynamoDB

```bash
aws dynamodb create-table \
--table-name dev-local-documents \
--attribute-definitions AttributeName=DocumentId,AttributeType=S \
--key-schema AttributeName=DocumentId,KeyType=HASH \
--provisioned-throughput ReadCapacityUnits=5,WriteCapacityUnits=5 \
--endpoint-url http://localhost:8000
```