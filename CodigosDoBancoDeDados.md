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
