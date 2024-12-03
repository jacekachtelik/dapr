# DAPR

Niniejszy projekt pokazuje wykorzystanie DAPR w komunikacji między różnymi systemami i aplikacjami.

## Instalacja

> ### Wymagania
> - docker
> 

Pobranie DAPR-a:

```bash
wget -q https://raw.githubusercontent.com/dapr/cli/master/install/install.sh -O - | /bin/bash
```

Weryfikacja instalacji:

```bash
dapr -h
```

Inicjalizacja:

```sh
sudo dapr init
```

```sh
sudo dapr --version
sudo docker ps
```