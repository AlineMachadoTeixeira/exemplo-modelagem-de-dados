# Comandos SQL - Referências

## Modelagem Física com comandos DDL

### Criar banco de dados 

CREATE DATABASE vendas CHARACTER SET utf8mb4; 

### Criar tabela de fabricantes 

```sql
CREATE TABLE fabricantes(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(45) NOT NULL    
); 
```

### Visualizar detalhes estruturais da tabela

```sql
DESC fabricantes; 
```

### Criar tabela de produto

```sql
CREATE TABLE produtos(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(45) NOT NULL,
    descricao TEXT(500) NULL,
    preco DECIMAL(6,2) NOT NULL,
    fabricante_id INT NOT NULL
);
```

### Criação do relacionamento entre as tabelas (Chave estrangeira)

```sql
ALTER TABLE produtos
    -- CONSTRAINT / RESTRIÇÃO indicando o nome do relacionamento
    ADD CONSTRAINT fk_produtos_fabricantes

    -- Criando a chave-estrangeira (fabricantes_id) que
    -- aponta para a chave-primaria (id) de outra tabela (fabricantes)
    FOREIGN KEY (fabricante_id) REFERENCES fabricantes(id);
```

### Exemplos de alterações estruturais na tabela


### Renomear a tabela 

```sql
ALTER TABLE fabricantes RENAME TO fornecedores;

```

```sql
-- Voltar para o normal nome fabricantes
ALTER TABLE fornecedores RENAME TO fabricantes;

```

### Modificar colunas 
```sql
ALTER TABLE produtos
-- modificar tipo
    MODIFY COLUMN preco INT NULL; 
```

```sql
ALTER TABLE produtos
-- Voltar para o normal preço para DECIMAL que é o correto
    MODIFY COLUMN preco DECIMAL(6,2) NOT NULL; 
```

### Renomear colunas 
```sql
-- modificar nome
ALTER TABLE fabricantes
    CHANGE nome nome_do_fabricantes VARCHAR(20) NOT NULL;
```

```sql
-- Voltar para o normal o nome
ALTER TABLE fabricantes
    CHANGE nome_do_fabricantes nome VARCHAR(45) NOT NULL;
```

###
