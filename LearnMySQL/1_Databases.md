# 1 - Databases (Bases de dados)

## _NOTA_: Todo o código apresentado foi feito na linguagem _MySQL_.

### || DATABASES - Bases de Dados ||

- __CREATE DATABASE__ – criação de uma base de dados de um sistema.
- __DROP DATABASE__ – remoção de uma base de dados de um sistema.

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
