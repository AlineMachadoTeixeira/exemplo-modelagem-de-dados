
CREATE DATABASE catalago_de_filme CHARACTER SET utf8mb4;



```sql
CREATE TABLE generos(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome_genero VARCHAR(45) NOT NULL    
); 
```

```sql
CREATE TABLE filmes(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    titulo_fime VARCHAR(45) NOT NULL,
    ano_de_lancamento YEAR(4) NOT NULL,    
    genero_id INT NOT NULL
);
```

```sql
-- modificar gereno o correto era generos
    ALTER TABLE genero RENAME TO generos;
```

```sql
ALTER TABLE filmes
    
    ADD CONSTRAINT fk_filmes_generos    
    FOREIGN KEY (genero_id) REFERENCES generos(id);
```

