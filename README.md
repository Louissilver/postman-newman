# Postman Newman

[![Version](https://img.shields.io/badge/version-1.0.0-brightgreen.svg)](https://github.com/seu-usuario/seu-repositorio)
[![License](https://img.shields.io/badge/license-ISC-blue.svg)](LICENSE)
[![Status de Testes](https://github.com/Louissilver/postman-newman/actions/workflows/test.yml/badge.svg)](https://github.com/Louissilver/postman-newman)

Este é um projeto que demonstra como instalar e usar o Newman para executar testes em APIs com o Postman.

A API utilizada nos testes é a [Go REST](https://gorest.co.in/).

## Índice

1. [Endpoints](#endpoints)
2. [Instalação](#instalação)
3. [Scripts](#scripts)
4. [Visualização do Relatório](#visualização-do-relatório)
   - 1.1 [Artefatos gerados em pipeline](#artefatos-gerados-em-pipeline)
5. [Autor](#autor)
6. [Licença](#licença)
7. [Palavras-chave](#palavras-chave)

## Endpoints

A API GoRest fornece uma variedade de endpoints para interagir com recursos, como usuários, posts e comentários. Abaixo estão alguns dos principais endpoints disponíveis:

1. **Usuários (Users)**

   - Endpoint: `https://gorest.co.in/public/v2/users`
   - Métodos HTTP suportados: GET, POST, PUT, DELETE

2. **Publicações (Posts)**

   - Endpoint: `https://gorest.co.in/public/v2/posts`
   - Métodos HTTP suportados: GET, POST, PUT, DELETE

3. **Comentários (Comments)**
   - Endpoint: `https://gorest.co.in/public/v2/comments`
   - Métodos HTTP suportados: GET, POST, PUT, DELETE

Certifique-se de consultar a documentação oficial da API GoRest para obter informações detalhadas sobre como usar esses endpoints, os parâmetros necessários e as respostas esperadas. Você pode realizar operações como listar, criar, atualizar e excluir recursos com esses endpoints, dependendo dos métodos HTTP suportados.

Para execução correta dos cenários, todas as requests de método DELETE foram incluídas ao final da collection.

## Instalação

Para instalar o Newman e o Reporter HTML na sua máquina, execute o seguinte comando:

```bash
npm install -g newman
npm install -g newman-reporter-html
```

## Scripts

O projeto inclui os seguintes scripts para executar testes com o Newman:

- Para executar todos os testes:
  ```bash
  npm run newman:all
  ```
- Para executar testes específicos do folder "User":
  ```bash
  npm run newman:user
  ```
  Certifique-se de que os arquivos de coleção (collections/GoRest.postman_collection.json) e ambiente (environments/GoRest.postman_environment.json) estão configurados corretamente antes de executar os scripts.

## Geração de Relatório

O comando a seguir permite que você execute a coleção do Postman e gere um relatório com htmlextra:

```bash
npm run newman:all:reporter
```

Este comando executa a coleção localizada em `collections/GoRest.postman_collection.json` usando o ambiente em `environments/GoRest.postman_environment.json` e gera um relatório em HTML com o reporter htmlextra, que é exportado para `report/index.html`.

### Visualização do Relatório

Após a execução do comando acima, o relatório gerado em HTML estará disponível no arquivo `report/index.html`. Você pode abrir este arquivo em seu navegador da web para visualizar o relatório detalhado das execuções da coleção. Certifique-se de que o caminho para o arquivo HTML corresponda ao local onde você o exportou.

### Artefatos gerados em pipeline

Caso você tenha executado a geração de relatório através de CI/CD, o relatório deve estar disponível nos artefatos da pipelina executada. Basta realizar o download do artefato e abrir com seu navegador.

## Autor

- Luís Fernando da Silveira

## Licença

Este projeto está licenciado sob a Licença ISC - consulte o arquivo [LICENSE](LICENSE) para obter detalhes.

## Palavras-chave

- newman
- postman
- api
