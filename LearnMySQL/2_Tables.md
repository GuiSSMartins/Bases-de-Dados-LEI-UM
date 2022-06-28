# 2 - Tables (Tabelas)

## _NOTA_: Todo o código apresentado foi feito na linguagem _MySQL_.

### || TABLE - Tabela ||

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

#### || Definição das Chaves PRIMÁRIAS e ESTRANGEIRAS + Técnicas de auxílio ||

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



### || Remoção de Tabelas (DROP TABLE) ||

Quando se aplica sobre a base de dados uma instrução de remoção de uma tabela, além de se remover da base de dados a sua definição também se removem todos:
- Registos; 
- Índices e gatilhos; 
- Restrições (constraints); 
- Privilégios; 
- (…)


__ATENÇÃO__: Caso uma tabela contenha uma chave estrangeira, esta só poderá ser removida da base de dados após a remoção da definição da chave estrangeira da tabela.
