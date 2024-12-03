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

3. Utworzenie tabeli w bazie AWS DynamoDB

```bash
aws dynamodb create-table \
--table-name dev-local-documents \
--attribute-definitions AttributeName=DocumentId,AttributeType=S \
--key-schema AttributeName=DocumentId,KeyType=HASH \
--provisioned-throughput ReadCapacityUnits=5,WriteCapacityUnits=5 \
--endpoint-url http://localhost:8000
```