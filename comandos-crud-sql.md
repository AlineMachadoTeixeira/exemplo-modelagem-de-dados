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
    VALUE (
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
    VALUE (
        'Tablet Android',        
        'Tablet com versão 14 do sistema operacional Android, possui tela de 10 polegadas e armazenamento de 128 GB, e 64 GB de RAM.',
        1500.99,
        5,
        5   --id do fabricante Samsung           
    );

-- Linha 3 , Linha  4 e Linha 5
INSERT INTO produtos (
         nome, descricao, preco,  quantidade, fabricante_id) 
    VALUE (
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


```

![](crud_fabricantes.PNG)

