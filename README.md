# Sobre o projeto

O TSE(Tribunal Superior Eleitoral) libera dados sobre todas as candidaturas no Brasil, sendo que uma em particular
é muito interessante, a de doações, onde podemos ver quem são aqueles que financiam os políticos.

Partindo desse ponto, esse projeto é para fornecer um comparador de doações de campanha entre candidatos a prefeito
do Rio de Janeiro, facilitando visualizar diferenças na forma como cada um está bancando sua campanha.

# Detalhes técnicos

## Como rodar o crawler
Estando na pasta "/data/crawler", execute "php generate.php" e o arquivo "/data/doacoes_geral.json" será atualizado.

## Rodando a Aplicação:

Instale as dependências com o Node:

```sh
$ npm i
```

Para rodar a aplicação:

```sh
$ npm start
```

Para fazer deploy:
```sh
$ npm deploy
```

# Detalhes técnicos para quem quiser ajudar ou forkar para outra cidade

## Como encontrar o ID da sua cidade?

- Accesse a URL `http://divulgacandcontas.tse.jus.br/divulga/rest/v1/eleicao/buscar/{SIGLA}/2/municipios` após substituir sigla pelo seu município (RJ para Rio de Janeiro, SP para São Paulo...)
- Na lista JSON que for retornada, procure pela sua cidade e use o ID;
- Antes de rodar o crawler, procure pela variável `$cidade_id` e atribua o ID da sua cidade.

## Portando para minha cidade

- Substitua o ID da sua cidade como explicado acima;
- Rode o Crawler(veja abaixo);
- Substitua a URL em `$http.get` no arquivo `src/assets/app.coffee`  para apontar para o seu Javascript

## Como rodar o crawler
Estando na pasta `/data/crawler`, execute `php generate.php` e o arquivo `/data/candidatos_dados_processados.json` será atualizado.


## Como executar?
- Abra `dist/index.html` no seu navegador.
