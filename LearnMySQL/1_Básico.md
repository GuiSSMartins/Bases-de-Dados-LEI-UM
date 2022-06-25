# 1 - Básico

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

Criação de uma base de dados  (“Sakila”) com opções de configuração
```mysql
CREATE DATABASE Sakila
    DEFAULT CHARSET=utf8mb4
    DEFAULT ENCRYPTION='N';
```




```mysql

```
