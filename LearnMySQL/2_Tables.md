# 2 - Tables (Tabelas)

## _NOTA_: Todo o código apresentado foi feito na linguagem _MySQL_.

### || TABLE - Tabela ||

- __CREATE TABLE__ – criação do esquema de uma tabela na base de dados.
- __ALTER TABLE__ – alteração do esquema de uma tabela da base de dados.
- __DROP TABLE__ – remoção de uma tabela da base de dados.

__ATENÇÃO__: Mesmo que a Tabela seja _TEMPORÁRIA_, é preciso fazer __DROP__ depois de a usarmos para o que queríamos! 

---------------------------------------------------------------------------------

#### || Definição das Chaves PRIMÁRIAS e ESTRANGEIRAS + Técnicas de auxílio ||

- __NOT NULL__: obrigatório preencher coluna com algum valor.
- __AUTO_INCREMENT__: aumenat de avlor ao longo que avmos inserindo registos.

__ATENÇÃO__: As chaves Primárias (PRIMARY KEY) _não podem ser_ __negativas__!!!

__ATENÇÃO 2__: As chaves Primárias (PRIMARY KEY) podem conter duplas entradas!!!

_EXEMPLO_: PRIMARY KEY (idAluno, nomeAluno);


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

__ATENÇÃO__: Caso uma tabela contenha uma chave estrangeira, esta só poderá ser removida da base de dados após a remoção da definição da chave estrangeira da tabela.
