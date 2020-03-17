## Instalação

### Requisitos

- [docker](https://docs.docker.com/install/)
- [docker-compose](https://docs.docker.com/compose/install/)

O projeto foi desenvolvido utilizando React, Express, Typescript, Jest. Foi criado containers dockers para auxiliar na execução do projeto.

Primeiro é necessário clonar o projeto:

```bash
git clone --recursive git@github.com:EduSantosBrito/vizir-app.git
## ou para caso use HTTPS
git clone --recursive https://github.com/EduSantosBrito/vizir-app.git
cd ./vizir-app
```

Para iniciar os containers em modo de produção, execute:

```bash
docker-compose -f docker-compose.yml up --build
```

Para iniciar os containers em modo de desenvolvimento, você primeiro deve instalar os pacotes dos projetos, então execute:

```bash
cd ./vizir-api
yarn
# Utilizei yarn para esse desafio, caso queira rodar com NPM, delete o arquivo yarn.lock para evitar conflitos de pacotes e rode npm install
cd ..
```

```bash
cd ./vizir-client
yarn
# Utilizei yarn para esse desafio, caso queira rodar com NPM, delete o arquivo yarn.lock para evitar conflitos de pacotes e rode npm install
cd ..
```

Logo depois, suba os containers:



```bash
docker-compose -f docker-compose.dev.yml up --build
```

O projeto React irá rodar na porta 3000, o projeto Express irá rodar na porta 3001.

**OBS: No modo de desenvolvimento, a api e o client estão em hot-reload. Caso queira modificar algo, eles atualizarão sozinhos sem necessidade de reiniciar o container**

**OBS2: Caso durante o build do docker, apareça esse erro ao instalar pacotes do yarn:**
```bash
info There appears to be trouble with your network connection. Retrying... 
```
**Você deverá remover o yarn.lock da pasta vizir-api e vizir-client, após isso rode o build novamente.**