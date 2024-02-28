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
<br>`[NOME] [VARCHAR] (150),`
<br>`[RUA] [VARCHAR] (150),`
<br>`[COMPLEMENTO] [VARCHAR] (150),`
<br>`[BAIRRO] [VARCHAR] (150),`
<br>`[ESTADO] [CHAR] (2),`
<br>`[CEP] [CHAR] (8),`
<br>`[DATA DE NASCIMENTO] [DATE],`
<br>`[IDADE] [SMALLINT],`
<br>`[SEXO] [CHAR] (1),`
<br>`[LIMITE DE CREDITO] [MONEY],`
<br>`[VOLUME MINIMO] [FLOAT],`
<br>`[PRIMEIRA COMPRA] [BIT]`
<br>`)`

>Existem vários tipos de dados em uma coluna, e dois deles são o `CHAR` e o `VARCHAR`, a diferença entre ambos é o fato de que o `CHAR (Character Fixed-Length)` que armazena strings de comprimento fixo e o `VARCHAR (Variable Character Length)` que armazena strings de comprimento variável. 
<br> Por exemplo, se você tiver uma coluna para armazenar nomes de pessoas e quiser economizar espaço, poderá usar `VARCHAR`, pois os nomes podem variar muito em comprimento. Por outro lado, se você estiver armazenando códigos de estado com sempre dois caracteres, pode ser mais apropriado usar `CHAR` para garantir o tamanho fixo e previsível do armazenamento.

><br>**O tipo de dados `DATE`** - armazena valores de data no formato "AAAA-MM-DD" (ano-mês-dia).
><br>**O tipo de dado `SMALLINT`** - é um tipo de dado numérico inteiro que pode armazenar valores inteiros pequenos, mínimo –32,767 e máximo 32,767. 
><br>**O tipo de dado `MONEY`** - é usado para guardar valores monetários com precisão fixa, sem pensar em arredondamento.
><br>**O tipo de dado `SMALLMONEY`** - é usado para guardar valores monetários com precisão fixa, sem pensar em arredondamento, porém ele reduz o provisionamento de armazenamento de memória, e ele não requer uma tamanho máximo.
><br>**O tipo de dado `FLOAT`** - é um tipo de dado que permite o registro de casas decimais.
><br>**O tipo de dado `BIT`** - é um tipo de valor lógico booleano, ou seja apenas true ou false, 0 ou 1.

***3 - Criando chaves primárias:***
<br> `CREATE TABLE [TABELA DE PRODUTOS](`

>Estamos setando no código abaixo a `PRIMARY KEY` que quer dizer que o campo será indentificado de forma unica, e o `NOT NULL` porque é obrigatório inserir o código, não pode ser inserido valores nulos:

` [CODIGO DO PRODUTO] [VARCHAR] (20) NOT NULL PRIMARY KEY,`
<br>`[PRIMEIRA COMPRA] [BIT]`
<br>`[NOME DO PRODUTO] [VARCHAR] (50),`
<br>`[EMBALAGEM] [VARCHAR] (50),`
<br>`[TAMANHO] [VARCHAR] (50),`
<br>`[SABOR] [VARCHAR] (50),`
<br>`[PRECO DE LISTA] [SMALLMONEY]`
<br>`)`

| **CATEGORIA**  |            **DESCRIÇÃO**                       | **EXEMPLO**                   |               **COMANDO**           |
|------------------|-----------------------------------------------------|------------------------------------------|---------------------------------|
| **NÚMERICOS EXATOS** | Números de vários tamanhos que podem ser formatados | 9.78 pode ser definida como DECIMAL(3,2) | BIGINT, INT, SMALLINT, TINYINT, DECIMAL(i,j), NUMERIC(i,j) |
| **UNIDADE MONETÁRIA** | Valores que representam dinheiro | 685477.58 é saldo da conta bancária definida do tipo MONEY | MONEY, SMALLMONEY |
| **NÚMERICOS APROXIMADOS** | Números de ponto flutuante com precisão | 7.90 é do tipo FLOAT | FLOAT ou REAL |
| **CADEIAS DE CARACTERES** | Textos de tamanhos fixos  | “modelagem” se encaixa em VARCHAR(9) | CHAR(n) |
|                       | Texto de tamanho variável |           | VARCHAR(n) |
| **VALORES LÓGICOS**  |Termos que representa verdadeiro ou falso |          | BIT |
| **DATAS**  	   | Datas, dias, mês, anos.        | Calendário lunar, calendário comercial | DATE AAAA-MM-DD, SMALLDATE, DATETIMEOFFSET |
|                  | Tempo	                    | 10:59:13 é tipo TIME  | TIME, DATETIME |

***4 - Alterando dados de uma tabela, usando o comando:***
<br> `ALTER TABLE [TABELA DE CLIENTES]`

***4 - Alterando a coluna de uma tabela, usando o comando:***
>Estamos setando no código abaixo a coluna que queremos alterar `[CPF]`, o tipo de dado que ela terá, a quantidade de caracteres e usamos para restringir o `NOT NULL`, para que não aceite dados nulos.

<br> `ALTER TABLE [TABELA DE CLIENTES] ALTER COLUMN [CPF] [CHAR] (11) NOT NULL;`















