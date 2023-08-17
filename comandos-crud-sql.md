# Comandos para operações CRUD Banco de Dados

## Resumo

- C -> (inserir dados usando comando `INSERT`)
- R -> (ler dados usando comando `SELECT`)
- U -> (atualizar dados usando comando `UPDATE`)
- D -> (excluir dados usando comando `DELETE`)

## INSERT

### Fabricantes
<!-- Vamos incluir os nomes do fabricantes na tapela Fabricantes que tem o ID e nome -->

```sql
-- INSERT -> insere só nome o ID o banco que vai gerar(AI)
INSERT INTO fabricantes (nome) VALUES('Asus');
```

```sql
-- INSERT -> vazer com duas linhas
INSERT INTO fabricantes (nome) VALUES('Dell');
INSERT INTO fabricantes (nome) VALUES('Apple');
```

```sql
-- INSERT -> vazer com uma linha
INSERT INTO fabricantes (nome) 
VALUES('LG'), ('Samsung'), ('Brastemp');


INSERT INTO fabricantes (nome) 
VALUES('Positivo'), ('Microsoft');

```
![](crud_fabricante.PNG)


### Produtos
<!-- vamos inserir na tabela prodturos o que foi pedido no caso nome, preco, descricao, quantidade, fabricante_id-->

```sql
-- Linha 1
INSERT INTO produtos (
         nome, preco, descricao, quantidade, fabricante_id) 
    VALUES (
        'Ultrabook',
        3500,
        'Equipamento de última geração cheio de recursos, com processador Inter Core i9 do balacobaco',
        7,
        2    --id do fabricante Dell    
        --no fabricante quero associar esse Ultrabook com o fabricante Dell está na segunda posição id2
    );

-- Linha 2 
INSERT INTO produtos (
         nome, descricao, preco,  quantidade, fabricante_id) 
    VALUES (
        'Tablet Android',        
        'Tablet com versão 14 do sistema operacional Android, possui tela de 10 polegadas e armazenamento de 128 GB, e 64 GB de RAM.',
        1500.99,
        5,
        5   --id do fabricante Samsung           
    );

-- Linha 3 , Linha  4 e Linha 5
INSERT INTO produtos (
         nome, descricao, preco,  quantidade, fabricante_id) 
    VALUES (
        'Geladeira',        
        'Refrigerador frost-free com acesso à Internet.',
        5000,
        12,
        6   --id do fabricante Brastemp           
    ), -- Linha 3

    (
        'iPhone 18 pro Max',
        'Smartphone Apple cheio de frescuras e caro pra caramba.',
        12666.66,
        3,  
        3
    ),-- Linha 4

    (
        'iPad Mini',
        'Tablet Apple com tela retina display e bla bla bla.',
        4999.01,
        5,  
        3
    );-- Linha 5


    INSERT INTO produtos (
         nome, descricao, preco,  quantidade, fabricante_id) 
    VALUES (
        'Xbox Serie S',        
        'Velocidade e desempenho de última geração.',
        1997.00,
        5,
        8   --id do fabricante Microsoft           
    ), -- Linha 6

    (
        'Notebook Motion',
        'Intel Dual Core 4GB de RAM, 128GB SSD e Tela 14,1 polegadas.',
        1213.65,
        8,  
        7 --id do fabricante Positivo
    );-- Linha 7 


```

![](crud_fabricantes.PNG)



---
---

## SELECT
<!-- SELECT ler dados que estão no FROM (tabela) -->

<!-- O * é para ler todos os dados da tabela(FROM)-->
```sql
SELECT * FROM produtos;
```

<!-- para ler o nome e preço da tabela(FROM) é só escrever o nome que você deu para esses campos-->
```sql
SELECT nome, preco FROM produtos;
```

<!-- para ler o preço e depois o nome da tabela(FROM) é só escrever o nome que você deu para esses campos-->
```sql
SELECT preco, nome FROM produtos;
```

<!-- para ler o mesmo de cima, porém com criterio coloque o WHERE e o que você precisa -->
```sql
SELECT  nome, preco, quantidade FROM produtos WHERE preco < 5000 ;
```


```sql
--Exercício :Mostre nome e descrição somente dos produtos da Apple
SELECT  nome, descricao FROM produtos WHERE fabricante_id = 3 ;
```

### Usar SELECT com Operadores Lógicos: E(AND), OU(OR), NÂO(!)

```sql
--Ver os produtos que custa entre 2 mil e 6 mil (Usado o operador logico E (AND) ) da tabela 
SELECT  nome, preco FROM produtos WHERE preco >= 2000 AND preco <= 6000;

--A query abaixo não retorna o resgistro. Já que as condicões não foram totalmente atendidas
SELECT  nome, preco FROM produtos WHERE preco > 5000 AND preco <= 6000;




```




