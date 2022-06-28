# 1 - Básico

## _NOTA_: Todo o código apresentado foi feito na linguagem _MySQL_.

### Palavras Reservadas

ACTION, AGGREGATE, BEFORE, BOOLEAN, CASCADE, CASE, CONNECT, DELETE, CUBE, COLLATION, NUMERIC, LEVEL, DATA, DAY, OLD, ON, LOOP, MINUTE, SUM, WITH, SELECT, VALUE, USING, ROLE, USER, PUBLIC, SIZE, REFERENCES, OUTPUT, CATALOG, DROP, YEAR, ...

### Tipos de dados 

- __Números inteiros__: INT[EGER], SMALLINT, NUMERIC [(p[,s])], DECIMAL[(p[,s])]
- __Números reais__: FLOAT, REAL, DOUBLE PRECISION
- __Strings e Caracteres__: CHAR[ACTER] [n], CHAR[ACTER] VARYING(n) ou VARCHAR(n), NATIONAL CHAR[ACTER] [n], NATIONAL CHAR[ACTER] VARYING(n)
- __Objetos de dados não estruturados de grande dimensão__: TEXT, CLOB, BLOB
- __Strings binárias__: BIT[(n)], BIT VARYING(n)
- __Tempo e Datas__: DATE, TIME, TIMESTAMP, TIME WITH TIME ZONE, TIMESTAMP TIME WITH TIME ZONE
- __Outros tipos__: BOOLEAN

### DATABASES - Bases de Dados

- __CREATE DATABASE__ – criação de uma base de dados de um sistema.
- __DROP DATABASE__ – remoção de uma base de dados de um sistema.

```mysql
CREATE {DATABASE | SCHEMA} [IF NOT EXISTS] db_name
    [create_option] ...
    create_option: [DEFAULT] {
    CHARACTER SET [=] charset_name
    | COLLATE [=] collation_name
    | ENCRYPTION [=] {'Y' | 'N'}}
    
DROP {DATABASE | SCHEMA} [IF EXISTS] db_name
```

Criação de uma base de dados (“Sakila”) com opções de configuração
```mysql
CREATE DATABASE Sakila
    DEFAULT CHARSET=utf8mb4   -- conjunto de caracteres
    DEFAULT ENCRYPTION='N';   -- opção de cifragem
```

Remoção de uma base de dados (“Sakila”)
```mysql
DROP DATABASE Sakila;
```

### TABLE - Tabela

- __CREATE TABLE__ – criação do esquema de uma tabela na base de dados.
- __ALTER TABLE__ – alteração do esquema de uma tabela da base de dados.
- __DROP TABLE__ – remoção de uma tabela da base de dados.

__ATENÇÃO__: Mesmo que a Tabela seja _TEMPORÁRIA_, é preciso fazer __DROP__ depois de a usarmos para o que queríamos! 
```mysql
CREATE [TEMPORARY] TABLE [IF NOT EXISTS] tbl_name
    (create_definition,...)
    [table_options]
    [partition_options]
    column_definition: { data_type [NOT NULL | NULL] [DEFAULT
    {literal | (expr)} ] [VISIBLE | INVISIBLE] [AUTO_INCREMENT]
    [UNIQUE [KEY]] [[PRIMARY] KEY] [COMMENT 'string'] [COLLATE
    collation_name] [COLUMN_FORMAT {FIXED | DYNAMIC |
    DEFAULT}] [ENGINE_ATTRIBUTE [=] 'string']
    [SECONDARY_ENGINE_ATTRIBUTE [=] 'string'] [STORAGE {DISK | MEMORY}]
    (…)
```

#### Definição das Chaves PRIMÁRIAS e ESTRANGEIRAS + Técnicas de auxílio

- __NOT NULL__: obrigatório preencher coluna com algum valor.
- __AUTO_INCREMENT__

__ATENÇÃO__: As chaves Primárias (PRIMARY KEY) _não podem ser_ __negativas__!!!


Criação de uma tabela com definição de chave primária e uma chave estrangeira:
```mysql
CREATE TABLE Promotions (
    Promotion_Nr INT NOT NULL AUTO_INCREMENT,
    Description VARCHAR(50) NOT NULL,
    Initial_Date DATETIME,
    Final_Date DATETIME,
    Category_Id TINYINT UNSIGNED NOT NULL,
        PRIMARY KEY (Promotion_Nr),   -- Definição de chave primária
        FOREIGN KEY (Category_Id)
            REFERENCES Category (Category_Id));   -- Definição da chave estrangeira
```

Alteração da definição inicial da tabela anterior para introdução de uma chave estrangeira.
```mysql
ALTER TABLE Promotions
    ADD CONSTRAINT fkPromotionsCategories
        FOREIGN KEY (Category_Id)           -- Definição da chave estrangeira
        REFERENCES Category (Category_Id); 
```
