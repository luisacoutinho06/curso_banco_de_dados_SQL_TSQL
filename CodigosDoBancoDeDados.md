***1 - Inserindo o comando para criar uma nova base de dados pela "Nova Consulta" do SSMS:***
<br> `CREATE DATABASE SUCOS_VENDAS;`

***1.1 - Parâmetros de personalização da base de dados usando SQL:***
<br> `NAME` -> Define um nome interno para a base de dados.
<br> `FILENAME` -> Estabelece o caminho da pasta na qual queremos armazenar a base de dados.
<br> `SIZE` -> Estipula o tamanho inicial da base de dados.
<br> `MAXSIZE` -> Limita o tamanho máximo da base de dados.
<br> `FILEGROWTH` -> Estipula a taxa de crescimento de armazenamento do banco de dados.

***Exemplo:***
<br>`CREATE DATABASE Base_Teste`<br>
`ON (NAME = 'base_de_dados_teste.DAT',`<br>
        `FILENAME = 'C:\TEMP\base_de_dados_teste.MDF',`<br>
        `SIZE = 10MB,`<br>
        `MAXSIZE = 50MB,`<br>
        `FILEGROWTH = 5MB);`
>A **taxa de crescimento** funciona da seguinte maneira: o banco inicia com 10MB. Quando passa desse valor, ganha mais 5MB, o que não significa
>que tenha esse valor em dados, mas sim uma área reservada. Quando essa área reservada for preenchida e chegar em 15, ele recebe mais 5, somando 20.
> Assim os valores são sucessivamente adquiridos até atingir os 50MB definidos como tamanho máximo.

***1.2 - Para realizarmos a exclusão do banco de dados, usamos o seguinte comando:***
<br> `DROP DATABASE SUCOS_VENDAS_2;`
<br>
<br> `DROP` -> Este comando exclui permanentemente os objetos e os dados relacionados, o que significa que não há como desfazer essa ação.

***2 - Para realizarmos o comentário em dentro da consulta do SQL, usamos o seguinte comando:***
<br> `/* */`

***3 - Para criarmos uma tabela, usamos o seguinte comando:***
<br> `CREATE TABLE [TABELA DE CLIENTES]`
<br>
<br> `TABLE` -> Este comando específica que queremos falar de uma tabela.
<br> `[]` -> Este comando neste usado para delimitar identificadores. São usados quando o nome do identificador contém espaços em branco ou caracteres especiais, ou se é uma palavra-chave do SQL.

***3 - Para criarmos as colunas de uma tabela, usamos o seguinte comando:***
<br> `CREATE TABLE [TABELA DE CLIENTES](`

>Abaixo estamos informando o nome da coluna, depois o tipo, que no caso é caracteres e quantidade limite de caracteres que são 11:

` [CPF] [CHAR] (11),`
<br>` [NOME] [VARCHAR] (150),`
<br>` [RUA] [VARCHAR] (150),`
<br>` [COMPLEMENTO] [VARCHAR] (150),`
<br>` [BAIRRO] [VARCHAR] (150),`
<br>` [ESTADO] [CHAR] (2),`
<br>` [CEP] [CHAR] (8),`
<br>` [DATA DE NASCIMENTO] [DATE],`
<br>` [IDADE] [SMALLINT],`
<br>` [SEXO] [CHAR] (1),`
<br>`[LIMITE DE CREDITO] [MONEY],`
<br>`[VOLUME MINIMO] [FLOAT],`
<br>`[PRIMEIRA COMPRA] [BIT]`
<br>`)`

>Existem vários tipos de dados em uma coluna, e dois deles são o `CHAR` e o `VARCHAR`, a diferença entre ambos é o fato de que o `CHAR (Character Fixed-Length)` que armazena strings de comprimento fixo e o `VARCHAR (Variable Character Length)` que armazena strings de comprimento variável. 
<br> Por exemplo, se você tiver uma coluna para armazenar nomes de pessoas e quiser economizar espaço, poderá usar `VARCHAR`, pois os nomes podem variar muito em comprimento. Por outro lado, se você estiver armazenando códigos de estado com sempre dois caracteres, pode ser mais apropriado usar `CHAR` para garantir o tamanho fixo e previsível do armazenamento.

><br>**O tipo de dados `DATE`** - armazena valores de data no formato "AAAA-MM-DD" (ano-mês-dia).
><br>**O tipo de dado `SMALLINT`** - é um tipo de dado numérico inteiro que pode armazenar valores inteiros pequenos, mínimo –32,767 e máximo 32,767. 
><br>**O tipo de dado `MONEY`** - é usado para guardar valores monetários com precisão fixa, sem pensar em arredondamento.
><br>**O tipo de dado `FLOAT`** - é um tipo de dado que permite o registro de casas decimais.
