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
