
# Projecto One For All
![MySQL](https://img.shields.io/badge/MySQL-00000F?style=for-the-badge&logo=mysql&logoColor=white)
<br>
Este é mais um projeto desenvolvido durante o curso de desenvolvimento web da Trybe. Aqui, a proposta era usar os conhecimentos adiquirirdos em MySQL para criar, e manipular um banco de dados. A partir de uma tabela com vários dados, foi feita a normalização da mesma e implementação dela utilizando MySQL.

## Habilidades
* Modelar um banco de dados; 
* Identificar entidades , atributos e relacionamentos;
* Aplicar a 1ª, 2ª e 3ª Forma Normal;
* Criar tabelas;
* Lidar com VIEWs;
* Alterar tabelas existentes;
* Criar reações dinâmicas com TRIGGERS;

## Problema a ser resolvido

Foi recebido uma tabela não normalizada semelhante ao que poderia ser uma versão simplificada do banco de dados do Spotify. O trabalho consistiu de duas partes: 

1. Normalizar essa tabela, criar o schema no seu banco de dados local e populá-lo; 

2. Realizar os desafios no seu banco normalizado e populado.
 

**Aviso:** Todos os dados da tabela são fictícios e foram gerados aleatoriamente através de ferramentas, com o intuito de deixar o projeto mais real 😉. Quaisquer similaridades com informações reais são meras coincidências.  

[Faça o download dela aqui](./SpotifyClone-Non-NormalizedTable.xlsx)



# Requisitos do projeto

  

## Desafio 1

  

* [x] Crie um banco com o nome de **`SpotifyClone`**.

  

* [x] Providencie as queries necessárias para criar tabelas normalizadas que atendam aos requisitos descritos na seção anterior;

  

* [x] Providencie as queries necessárias para popular as tabelas de acordo com os dados listados na seção anterior;

  

* [x] Crie um arquivo de configurações `desafio1.json`, que mapeará em qual tabela e coluna se encontram as informações necessárias para a avaliação automatizada deste desafio. As configurações devem possuir o seguinte formato:

  

```json

{

"coluna_usuario": "nome-da-coluna",

"tabela_que_contem_usuario": "nome-da-tabela-que-armazena-a-coluna",

"coluna_plano": "nome-da-coluna",

"tabela_que_contem_plano": "nome-da-tabela-que-armazena-a-coluna",

"coluna_historico_de_reproducoes": "nome-da-coluna",

"tabela_que_contem_historico_de_reproducoes": "nome-da-tabela-que-armazena-a-coluna",

"coluna_seguindo_artistas": "nome-da-coluna",

"tabela_que_contem_seguindo_artistas": "nome-da-tabela-que-armazena-a-coluna",

"coluna_artista": "nome-da-coluna",

"tabela_que_contem_artista": "nome-da-tabela-que-armazena-a-coluna",

"coluna_album": "nome-da-coluna",

"tabela_que_contem_album": "nome-da-tabela-que-armazena-a-coluna",

"coluna_cancoes": "nome-da-coluna",

"tabela_que_contem_cancoes": "nome-da-tabela-que-armazena-a-coluna"

}

```

Essa configuração deve ser feita baseada no seu banco de dados **após a normalização**. Ou seja, se você criou uma tabela chamada `users` que possui a coluna `name`, você substituiria `"coluna_usuario"` e `"tabela_que_contem_usuario"` da seguinte forma:

  

```json

{

"coluna_usuario": "name",

"tabela_que_contem_usuario": "users",

...

}

```

 
* [x] Salve as queries criadas no arquivo `desafio1.sql`. Seu código deverá ser similar ao seguinte:

  

```sql

DROP  DATABASE  IF  EXISTS SpotifyClone;

  

CREATE  DATABASE SpotifyClone;

  

USE SpotifyClone;

  

CREATE  TABLE tabela1(

coluna1 tipo restricoes,

coluna2 tipo restricoes,

colunaN tipo restricoes,

) engine = InnoDB;

  

CREATE  TABLE tabela2(

coluna1 tipo restricoes,

coluna2 tipo restricoes,

colunaN tipo restricoes,

) engine = InnoDB;

  

INSERT  INTO tabela1 (coluna1, coluna2)

VALUES

('exemplo de dados 1', 'exemplo de dados A'),

('exemplo de dados 2', 'exemplo de dados B'),

('exemplo de dados 3', 'exemplo de dados C');

  

INSERT  INTO tabela2 (coluna1, coluna2)

VALUES

('exemplo de dados 1', 'exemplo de dados X'),

('exemplo de dados 2', 'exemplo de dados Y');

```
 

## Desafio 2

  

Crie uma `VIEW` chamada `estatisticas_musicais` que exiba três colunas:

  

1.  [x] A primeira coluna deve exibir a quantidade total de canções. Dê a essa coluna o alias "**cancoes**".

  

2. [x] A segunda coluna deve exibir a quantidade total de artistas e deverá ter o alias "**artistas**".

  

3. [x] A terceira coluna deve exibir a quantidade de álbuns e deverá ter o alias "**albuns**".

## Desafio 3

  

Crie uma `VIEW` chamada `historico_reproducao_usuarios`. Essa `VIEW` deverá ter apenas duas colunas:

  

1.  [x] A primeira coluna deve possuir o alias "**usuario**" e exibir o nome da pessoa usuária.

  

2. [x] A segunda coluna deve possuir o alias "**nome**" e exibir o nome da canção ouvida pela pessoa com base no seu histórico de reprodução.

  

Os resultados devem estar ordenados por nome da pessoa usuária em ordem alfabética e em caso de empate no nome os resultados devem ser ordenados pelo nome da canção em ordem alfabética.

## Desafio 4

  

Crie uma `VIEW` com o nome `top_3_artistas` que deve mostrar somente as três pessoas artistas mais populares no banco `SpotifyClone`, possuindo as seguintes colunas:

  

1. [x]  A primeira coluna deve possuir o alias "**artista**" e exibir o nome da pessoa artista.

  

2. [x]  A segunda coluna deve ter o alias "**seguidores**" e exibir a quantidade de pessoas que estão seguindo aquela pessoa artista.

  

Seu resultado deve estar ordenado em ordem decrescente, baseando-se na quantidade de seguidores. Em caso de empate, ordene os resultados pelo nome da pessoa artista em ordem alfabética.

## Desafio 5 

Estamos fazendo um estudo das músicas mais tocadas e precisamos saber quais são as duas músicas mais tocadas no momento. Crie uma `VIEW` chamada `top_2_hits_do_momento` que possua duas colunas:

  

1. [x] A primeira coluna deve possuir o alias "**cancao**" e exibir o nome da canção.

  

2.  [x] A segunda coluna deve possuir o alias "**reproducoes**" e exibir a quantidade de pessoas que já escutaram a canção em questão.

  

Seu resultado deve estar ordenado em ordem decrescente, baseando-se no número de reproduções. Em caso de empate, ordene os resultados pelo nome da canção em ordem alfabética. Queremos apenas o top 2 de músicas mais tocadas.

## Desafio 6

  

Tendo como base o valor dos planos e o plano que cada pessoa usuária cadastrada possui no banco, queremos algumas informações sobre o faturamento da empresa. Crie uma `VIEW` chamada `faturamento_atual` que deve exibir quatro dados:

  

1.  [x] A primeira coluna deve ter o alias "**faturamento_minimo**" e exibir o menor valor de plano existente para uma pessoa usuária.

  

2.  [x] A segunda coluna deve ter o alias "**faturamento_maximo**" e exibir o maior valor de plano existente para uma pessoa usuária.

  

3.  [x] A terceira coluna deve ter o alias "**faturamento_medio**" e exibir o valor médio dos planos possuídos por pessoas usuárias até o momento.

  

4.  [x] Por fim, a quarta coluna deve ter o alias "**faturamento_total**" e exibir o valor total obtido com os planos possuídos por pessoas usuárias.

  

Para cada um desses dados, por se tratarem de valores monetários, deve-se arredondar o faturamento usando apenas duas casas decimais.

 ## Desafio 7

Mostre uma relação de todos os álbuns produzidos por cada pessoa artista, com a quantidade de seguidores que ela possui, de acordo com os detalhes a seguir. Para tal, crie uma `VIEW` chamada `perfil_artistas`, com as seguintes colunas:

  

1.  [x] A primeira coluna deve exibir o nome da pessoa artista, com o alias "**artista**".

  

2.  [x] A segunda coluna deve exibir o nome do álbum, com o alias "**album**".

  

3.  [x] A terceira coluna deve exibir a quantidade de pessoas seguidoras que aquela pessoa artista possui e deve possuir o alias "**seguidores**".

  

Seus resultados devem estar ordenados de forma decrescente, baseando-se no número de pessoas seguidoras. Em caso de empate no número de pessoas, ordene os resultados pelo nome da pessoa artista em ordem alfabética e caso há artistas com o mesmo nome, ordene os resultados pelo nome do álbum alfabeticamente.


## Desafio 8  

Crie uma trigger chamada `trigger_usuario_delete` que deve ser disparada sempre que uma pessoa usuária for excluída do banco de dados, refletindo essa exclusão em todas as tabelas que ela estiver.



## Desafio 9

  

Crie uma procedure chamada `albuns_do_artista` que recebe como parâmetro o nome de uma pessoa artista e em retorno deve exibir as seguintes colunas:

  

1. [x] O nome da pessoa artista, com o alias "**artista**".

  

2.  [x] O nome do álbum, com o alias "**album**".

  

Os resultados devem ser ordenados pelo nome do álbum em ordem alfabética.

## Desafio 10
 

Crie uma function chamada de `quantidade_musicas_no_historico` que exibe a quantidade de músicas que estão presentes atualmente no histórico de reprodução de uma pessoa usuária. Ao receber o código identificador da pessoa, exiba a quantidade de canções em seu histórico de reprodução.


## Desafio 11

Crie uma `VIEW` chamada `cancoes_premium` que exiba o nome e a quantidade de vezes que cada canção foi tocada por pessoas usuárias do plano familiar ou universitário, de acordo com os detalhes a seguir:  

* [x] A primeira coluna deve exibir o nome da canção, com o alias "**nome**";  

* [x] A segunda coluna deve exibir a quantidade de pessoas que já escutaram aquela canção, com o alias "**reproduções**";  

* [x]  resultados devem estar agrupados pelo nome da canção e ordenados em ordem alfabética.
