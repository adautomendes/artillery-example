# Projeto exemplo de teste de carga com serviços distribuídos

## Aplicações necessárias para o desenvolvimento

- [NodeJS](https://nodejs.org/en/): Ambiente de execução Javascript.
- [VSCode](https://code.visualstudio.com/): Edição do código fonte (há um pacote de extensões chamado `Node Essentials`, recomenda-se a instalação do mesmo).
- [Git for Windows](https://gitforwindows.org/): Linha de comando.
- [MongoDB](https://www.mongodb.com/try/download/community): Persistência de dados, banco orientado a documentos.
- [Postman](https://www.postman.com/): Teste em APIs.
- [Docker](https://www.docker.com/products/docker-desktop): Criação de imagens e execução da aplicação em containers.
- [Artillery](https://artillery.io/): Execução de testes de carga.

## Como configurar

Em ambos projetos (core e api) há um arquivo `.env.template`. Remova a extensão `.template` do nome do arquivo e altere as seguintes propriedades:

### Core

`PORTA`: porta utilizada para executar a aplciação do Core.  
`DB_URL`: URL do MongoDB que será utilizado para persistir as informações.  
`DB_NAME`: Nome da coleção do MongoDB que será utilizada para persistir as informações.  
`SECRET`: Chave para a geração dos tokens JWT.  

### API

`PORTA`: porta utilizada para executar a aplciação da API.  
`CORE_URL`: URL base de onde está rodando o Core. Ex.: `http://localhost:5000`.  

## Como executar

Abra um terminal em cada projeto (core e api) e execute os seguintes comandos:

```
npm install
```

```
npm start
```

## Testar via Postman

Importe os arquivos `Toddy.postman_collection.json` e `Toddy.postman_environment.json`.

## Testar carga usando o Artillery

Com os projetos rodando, abra um terminal na pasta `test` e execute o comando abaixo:

```
artillery run load.yaml
```