***1 - O que é o T-SQL?***
<br><br>
T-SQL significa **Transact SQL** e é o nome da linguagem interpretada usada pelo SQL Server. Inclusive, desde o primeiro treinamento de SQL Server, nós já utilizamos o 
T-SQL. Toda vez que vamos ao **Management Studio**, criamos uma nova consulta e digitamos um comando SQL padrão **ANSI**, este comando é um comando de **T-SQL**.

Sendo assim, todo os comandos de `SELECT`, `INSERT`, `UPDATE`, `CREATE` e `DROP` é T-SQL, então o estamos praticando desde o início dessa formação.

> ***Qual a finalidade de um curso que fala sobre T-SQL?***
> <br>
> <br>
>O ***Transact SQL*** é muito mais que simplesmente comandos de seleção e inclusão, ou comandos de manipulação de banco de dados. Ele pode, ainda, ser comandos estruturados,
>quase como uma linguagem de programação.
O ***T-SQL*** padrão ***ANSI*** faz parte de um conjunto menor de todos os comandos do ***T-SQL***, ou seja, os comandos SQL padrão
>***ANSI*** estão dentro de uma área maior que corresponde aos comandos de ***T-SQL***. No SQL Server, o ***SQL ANSI*** são comandos subconjuntos do T-SQL.

>O padrão ANSI, que explicamos na introdução do SQL, é um padrão respeitado por todos os bancos de dados relacionais do mercado.

<br>

***2 - Declaração de variáveis***
<br><br>
O objetivo dessa declaração de variáveis é o mesmo das demais linguagens de programação. Ela é uma ***entidade*** na qual iremos ***atribuir um valor***, além disso, podemos utilizá-la nos comandos de ***T-SQL***, assim como modificar seus valores.

`DECLARE <NOME DA VARIÁVEL> <TIPO DA VARIÁVEL>`

> O nome da variável deve ser único e iniciar com ***`@`***;
>
> O tipo da variável pode ser qualquer um existente no SQL Server. Inclusive do tipo ***`TABELA`***;
>
> A atribuição do valor de uma variável pode ser efetuada através do comando ***`SET`*** ou através de um ***`SELECT`***.

***Exemplo de declaração de variável:***

![image](https://github.com/luisacoutinho06/curso_banco_de_dados_SQL_TSQL/assets/104804096/65d4532d-2c0c-42de-8653-4352b2495874)

***Exemplo de atribuição a uma variável:***

![image](https://github.com/user-attachments/assets/12bf694d-65bd-4b36-a4fc-7126b32058dd)

***Exemplo de como imprimir na aba ***`MENSAGENS`*** os valores referentes as variáveis:***

![image](https://github.com/user-attachments/assets/138c8877-835b-418a-bcf9-d67829cd6f1a)

> O ***`PRINT`*** funciona como um orientador. Imprimir o valor das variáveis é muito útil em uma depuração, por exemplo, ou até mesmo para medir os valores conforme o programa é executado.

***3 - Usando a variável em um comando SQL:***

O que faremos, agora, é um comando de inserir um novo vendedor utilizando os valores das variáveis. Para isso, utilizamos o comando `INSERT INTO` com a tabela `[TABELA DE VENDEDORES]`. Em seguida, podemos declarar ou não os nomes das colunas, mas se não os declararmos, teremos que declarar os valores na ordem natural dessas colunas na tabela.
<br>

>`SELECT * FROM [TABELA DE VENDEDORES];`<br>
><br>
>`DECLARE @MATRICULA VARCHAR(5), @NOME VARCHAR(100), @PERCENTUAL FLOAT;`<br>
>`DECLARE @DATA DATE, @FERIAS BIT, @BAIRRO VARCHAR(50);`<br>
><br>
>`SET @MATRICULA = '00240';`<br>
>`SET @NOME = 'Cláudia Rodrigues';`<br>
>`SET @PERCENTUAL = 0.10;`<br>
>`SET @DATA = '2012-03-12';`<br>
>`SET @FERIAS = 1;`<br>
>`SET @BAIRRO = 'Jardins'`<br>
><br>
>`PRINT @MATRICULA`<br>
>`PRINT @NOME`<br>
>`PRINT @PERCENTUAL`<br>
>`PRINT @DATA`<br>
>`PRINT @FERIAS`<br>
>`PRINT @BAIRRO;`<br>
><br>
>`INSERT INTO [TABELA DE VENDEDORES]`<br>
>`(MATRICULA, NOME, [PERCENTUAL COMISSÃO], [DATA ADMISSÃO], [DE FERIAS], BAIRRO)`<br>
>`VALUES`<br>
>`(@MATRICULA, @NOME, @PERCENTUAL, @DATA, @FERIAS, @BAIRRO)`<br>
><br>
>`PRINT 'UM VENDEDOR INCLUíDO.'`<br>
><br>
>`SET @MATRICULA = '00244';`<br>
>`SET @NOME = 'Roberto Araujo';`<br>
><br>
>`INSERT INTO [TABELA DE VENDEDORES]`<br>
>`(MATRICULA, NOME, [PERCENTUAL COMISSÃO], [DATA ADMISSÃO], [DE FERIAS], BAIRRO)`<br>
>`VALUES`<br>
>`(@MATRICULA, @NOME, @PERCENTUAL, @DATA, @FERIAS, @BAIRRO)`<br>
><br>
>`PRINT 'UM VENDEDOR INCLUíDO.'`<br>

***Atribuindo valores a variáveis através de um `SELECT`.***
![image](https://github.com/user-attachments/assets/fa6e8ca7-8709-46ed-b739-72f3d1076f73)


***Usando funções em comandos print***
![image](https://github.com/user-attachments/assets/d66e7ebe-72f7-40ff-ac03-0382dc123ee0)


***4 - Controle de Fluxo - IF***
O `T-SQL` por ser uma extensão da linguagem SQL padrão ANSI, possui mais comandos que as regras padrões. Mencionamos anteriormente que as funções de texto, conversão, entre outras, são específicas de cada banco de dados, portanto, cada uma possui uma sintaxe. Isso também acontcece nos comandos de fluxo pois cada banco de dados possui uma implementação.

>O IF<br>
>No comando IF se uma condição for verdadeira será feita uma ou mais instruções.<br>
>Sintaxe:<br>
>`IF <Expressão lógica>`<br>
>`<sentença SQL ou controle de bloco>`<br>

>O ELSE<br>
>Eventualmente ele também acompanha o comando ELSE que em português seria o "se não". Ou seja, se em uma condição for verdadeira determinado comando será executado, caso não outro comando será >executado.<br>
>Sintaxe:<br>
>`ELSE`<br>
>`<sentença SQL ou controle de bloco>`<br>

Pela definição, uma expressão lógica é aquela que retorna um valor verdadeiro ou falso. No caso do IF também podemos utilizar comandos SQL, claro, com o mesmo padrão de retorno.
Vimos anteriormente que controles de bloco são normalmente limitados entre BEGIN e umEND. Isso significa que se depois do IF tivermos que fazer apenas uma instrução não colocamos BEGIN e END, já se for mais de uma sim.

Exemplo 1:
>`IF @X > 0`<br>
>`  PRINT @Y;`<br>

Exemplo 2:
>`IF @X > 0`<br>
>`    BEGIN`<br>
>`        PRINT @Y;`<br>
>`        PRINT @X;`<br>
>`    END;`<br>


***Praticando o IF***
![image](https://github.com/user-attachments/assets/57fd8e5f-9250-4425-96e2-490d8364e92e)
Como há o teste e só depois que o comando é executado, dependendo das combinações, nunca teremos erro. Isso significa que o IF aprimorou nosso script.
