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

`[CPF] [CHAR] (11),`
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

`[CODIGO DO PRODUTO] [VARCHAR] (20) NOT NULL PRIMARY KEY,`
<br>`[PRIMEIRA COMPRA] [BIT]`
<br>`[NOME DO PRODUTO] [VARCHAR] (50),`
<br>`[EMBALAGEM] [VARCHAR] (50),`
<br>`[TAMANHO] [VARCHAR] (50),`
<br>`[SABOR] [VARCHAR] (50),`
<br>`[PRECO DE LISTA] [SMALLMONEY]`
<br>`)`

| **CATEGORIA**  |            **DESCRIÇÃO**                       | **EXEMPLO**                                     |              **COMANDO**        |
|------------------|-----------------------------------------------------|------------------------------------------|---------------------------------|
| **NÚMERICOS EXATOS**      | Números de vários tamanhos que podem ser formatados | 9.78 pode ser definida como DECIMAL(3,2) | BIGINT, INT, SMALLINT, TINYINT, DECIMAL(i,j), NUMERIC(i,j) |
| **UNIDADE MONETÁRIA**     | Valores que representam dinheiro | 685477.58 é saldo da conta bancária definida do tipo MONEY | MONEY, SMALLMONEY |
| **NÚMERICOS APROXIMADOS** | Números de ponto flutuante com precisão | 7.90 é do tipo FLOAT | FLOAT ou REAL |
| **CADEIAS DE CARACTERES** | Textos de tamanhos fixos  | “modelagem” se encaixa em VARCHAR(9) | CHAR(n) |
|                           | Texto de tamanho variável |           | VARCHAR(n) |
| **VALORES LÓGICOS**  |Termos que representa verdadeiro ou falso |          | BIT |
| **DATAS**  	   | Datas, dias, mês, anos.        | Calendário lunar, calendário comercial | DATE AAAA-MM-DD, SMALLDATE, DATETIMEOFFSET |
|                  | Tempo	                    | 10:59:13 é tipo TIME  | TIME, DATETIME |

***4 - Alterando dados de uma tabela, usando o comando:***
<br> `ALTER TABLE [TABELA DE CLIENTES]`

***4.1 - Alterando a coluna de uma tabela, usando o comando:***
>Estamos setando no código abaixo a coluna que queremos alterar `[CPF]`, o tipo de dado que ela terá, a quantidade de caracteres e usamos para restringir o `NOT NULL`, para que não aceite dados nulos.

<br> `ALTER TABLE [TABELA DE CLIENTES] ALTER COLUMN [CPF] [CHAR] (11) NOT NULL;`

***4.2 - Inserindo uma chave primária a uma coluna que já existe:***
>Estamos setando no código abaixo uma restrição de chave primária à tabela chamada `[TABELA DE CLIENTES]`. <br>

>`ADD CONSTRAINT PK_TABELA_CLIENTE` - Isso adiciona uma nova restrição à tabela. `PK_TABELA_CLIENTE` é o nome dado à restrição de chave primária. `PK` geralmente é usado como prefixo para indicar uma chave primária.<br>

>`ADD CONSTRAINT PK_TABELA_CLIENTE` - Define a coluna `[CPF]` como a chave primária da tabela. `PRIMARY KEY` indica que esta restrição é uma chave primária. `CLUSTERED` indica que o índice criado para a chave primária será organizado de forma a agrupar fisicamente os registros semelhantes no disco, o que pode melhorar o desempenho em algumas consultas. `[CPF]` é o nome da coluna que será a chave primária.<br>

`ALTER TABLE [TABELA DE CLIENTES] ADD CONSTRAINT PK_TABELA_CLIENTE PRIMARY KEY CLUSTERED ([CPF]);`

***5 - Inserindo uma informação na tabela com o comando 'INSERT INTO':***
>Com este código `INSERT INTO` estamos inserindo informações à tabela chamada `[TABELA DE CLIENTES]` e usando o `VALUES()` setamos os valores que queremos inserir dentro, exemplo no código abaixo. <br>

<br>`INSERT INTO [TABELA DE PRODUTOS] VALUES (`
Os valores que estamos inserindo devem seguir a ordem da tabela:
<br>`'1040107'`
<br>`'Light 350 ml - Melancia'`
<br>`'Lata'`
<br>`'350 ml'`
<br>`'Melancia'`
<br>`4.56`
<br>`)`

***5.1 - Inserindo várias informações na tabela com o comando 'INSERT INTO':***
>Com este código `INSERT INTO` estamos inserindo informações à tabela chamada `[TABELA DE CLIENTES]` e usando o `VALUES()` setamos os valores que queremos inserir dentro do parênteses, exemplo no código abaixo. <br>

<br>`INSERT INTO [TABELA DE PRODUTOS] VALUES`
<br>`('10837797', 'Clean - 2 Litros - Laranja', 'PET', '2 Litros', 'Laranja', 16.01),`
<br>`(1000889, Sabor da Montanha 700 ml Uva', 'Garrafa', 700 ml, 'Uva', 6.31),`
<br>`('1004327', Videira do Campo 1,5 Litros Melancia', 'PET', '1,5 Litros', 'Melancia', 19.51),`
<br>`('1088126', 'Linha Citrus 1 Litro Limão', 'PET', '1 Litro', 'Limão', 7.00);`

Outro exemplo:
<br>`INSERT INTO [TABELA DE CLIENTES] VALUES`
<br>`('00384393431', 'João da Silva', 'Rua Projetada A', 'Número 233', 'Copacabana', 'RJ', '20000000', '1965-03-21', 57, 'M', 20000000, 3000.30, 1),`
<br>`('00384393555', 'Maria Clara', 'Rua Projetada A', 'Número 233', 'Copacabana', 'RJ', '20000000', '1975-03-21',47, 'F', 200000, 3000.30, 0);`

Exemplo para comparar o valor inserido e a coluna:
<br>`INSERT INTO [TABELA DE PRODUTOS]`
<br>`([CODIGO DO PRODUTO], [NOME DO PRODUTO], [EMBALAGEM], [TAMANHO], [PRECO DE LISTA], [SABOR])`
<br>`VALUES`
<br>`('5449310', 'Frescor do Verão - 350 ml - Limão', 'Lata', '350 ml',2.45, 'Limão'),`
<br>`('1078680', 'Frescor do Verão - 350 ml - Manga', 'Lata', '350 ml',3.18, 'Manga');`

***6 - Consultando dados e trazendo na tabela usando o 'SELECT * FROM':***
>Com este código `SELECT * FROM` estamos querendo selecionar informações da tabela chamada `[TABELA DE PRODUTOS]` e o `*`  representa todas as linhas e colunas dessa tabela. <br>

<br>`SELECT * FROM [TABELA DE PRODUTOS];`

Para realizarmos a seleção de dados específicos, precisamos alterar os asteriscos para o nome da coluna que desejamos:

<br>`SELECT [NOME], [ESTADO] FROM [TABELA DE PRODUTOS];`

***7 - Consultando dados e trazendo os registros de acordo com a ordenação que desejamos, usando o 'ORDER BY':***
>Com este código `ORDER BY` estamos querendo a tabela de clientes em ordem alfabética de nomes ou estados, a depender de nossa necessidade. <br>

<br>`SELECT [ESTADO], [NOME] FROM [TABELA DE CLIENTES] ORDER BY [NOME];`

***7.1 - Inserindo um apelido para esta coluna:***
>Com este código `AS` estamos inserindo a coluna [NOME] que o apelido seja [NOME DO CLIENTE]. <br>

<br>`SELECT [NOME] AS [NOME DO CLIENTE], [CPF], [ESTADO] FROM [TABELA DE CLIENTES];`

***8 - Consultando uma lista de dados sem repetir caso sejam iguais:***
>Com este código `DISTINCT` trazemos uma lista de valores unicos. Queremos todos os sabores disponíveis, sem repetir. <br>

<br>`SELECT DISTINCT [SABOR] FROM [TABELA DE PRODUTOS];`

***9 - Consultando uma lista de dados filtrada, usando 'WHERE':***
>Com este código `WHERE` trazemos uma lista de dados, porém especificando algo daqueles dados. <br>

<br>`SELECT nome_do_cliente, primeira_compra FROM clientes WHERE [PRIMEIRA COMPRA] = 1;`
<br>`SELECT * FROM [TABELA DE PRODUTOS] WHERE [PRECO DE LISTA] = 7.00;`
<br>`SELECT * FROM [TABELA DE PRODUTOS] WHERE [PRECO DE LISTA] <= 7.00;`

>A partir do uso da cláusula WHERE, conseguimos estabelecer condições específicas usando os operadores em uma coluna numérica. <br>

>Ao realizarmos uma consulta onde inserimos um texto, ocorrerá a seguinte situação: Na **TABELA ASCII**, que codifica letras para números. Dessa forma, teríamos uma codificação para o alfabeto, onde 'B' é maior que 'A', 'C' é maior que 'B' e assim sucessivamente. PET começa com 'P' e, portanto, é maior que 'lata', que começa com 'L', na escala alfabética. Por isso, apareceram apenas os sucos de embalagem PET, que na escala alfabética são maiores que a lata.

<br>`SELECT * FROM [TABELA DE PRODUTOS] WHERE [EMBALAGEM] > 'Lata';`

>OBS: Quando trabalhamos com datas, temos funções específicas que podemos usar, como `YEAR()`, que extrai o ano, `MONTH()`, que extrai o mês, e `DAY()`, que extrai o dia.

![IMG1](https://github.com/luisacoutinho06/aprendendoBancoDeDados/blob/main/img1.png)
<br>
<br>
![IMG2](https://github.com/luisacoutinho06/aprendendoBancoDeDados/blob/main/img2.png)

***10 - Consultando uma lista de dados filtrada com condições combinadas, usando 'WHERE':***
>Com este código `WHERE` trazemos uma lista de dados, e usando o `OR` queremos que os filtros trazidos tenham a condição de um ou de outro da mesma coluna. <br>

`SELECT [NOME], [BAIRRO] FROM [TABELA DE CLIENTES] WHERE [BAIRRO] = 'Copacabana' OR [BAIRRO] = 'Tijuca';`

>Com este código `WHERE` trazemos uma lista de dados, e usando o `AND` queremos que as condições sejam unidas e retorne o filtro. <br>

`SELECT [NOME], [ESTADO], [PRIMEIRA COMPRA] FROM [TABELA DE CLIENTES] WHERE [PRIMEIRA COMPRA] = '1' AND [ESTADO] = 'SP';`

***11 - Alterando dados, usando 'UPDATE':***
>Com este código `UPDATE` alteramos os dados, o `SET` é para definir qual alteração irei realizar. <br>

`UPDATE [TABELA DE PRODUTOS] SET [PRECO DE LISTA] = [PRECO DE LISTA] * 0.9 WHERE [EMBALAGEM] = 'Lata';`

***12 - Deletando dados, usando 'DELETE':***
>Com este código `DELETE` apagamos os dados ou a tabela, e o `FROM ` é para definir onde queremos realizar isso. <br>

`DELETE FROM [TABELA DE PRODUTOS] WHERE [CODIGO DO PRODUTO] = '1004327';`




