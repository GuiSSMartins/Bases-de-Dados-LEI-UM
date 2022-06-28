# 3 - Manipulação de (Meta)Dados

## _NOTA_: Todo o código apresentado foi feito na linguagem _MySQL_.

- Operações de _inserção_ de dados (__INSERT__): para _povoamento_ da base de dados
- Operações de _modificação_ (__UPDATE__) e _remoção_ de dados (__DELETE__): para _atualização_ dos objetos da base de dados

```mysql
INSERT [LOW_PRIORITY | DELAYED | HIGH_PRIORITY] [IGNORE]
    [INTO] tbl_name
    [PARTITION (partition_name [, partition_name] ...)]
    [(col_name [, col_name] ...)]
    { {VALUES | VALUE} (value_list) [, (value_list)] ... }
    [AS row_alias[(col_alias [, col_alias] ...)]]
    [ON DUPLICATE KEY UPDATE assignment_list]
    (…)
```
Inserção de um registo numa tabela
```mysql
INSERT INTO Producers
  (Producer_Id, First_Name, Last_Name, Gender, Country_Id,Date_Of_Birth, eMail, Facebook, Instagram, Notes)
  VALUES ('21','Jonh','Well-Done','M','103','1978-01-01','jonhw@email.com',NULL,NULL,NULL);
```

Inserção de um registo numa tabela, utilizando __apenas uma parte__ do seu esquema da tabela:
```mysql
INSERT INTO Producers
    (Producer_Id, First_Name, Last_Name, Gender)
    VALUES ('22','Anne','Carson','F');
```

Inserção simultânea de vários registos:
```mysql
INSERT INTO Agents
    (Agent_Id, First_Name, Last_Name)
    VALUES
        ('2','Ralf','Spencer'),
        ('3','Anne','Lopez'),
        ('4','Joseph','Pane');
```


```mysql
UPDATE [LOW_PRIORITY] [IGNORE] table_reference
    SET assignment_list
    [WHERE where_condition]
    [ORDER BY ...]
    [LIMIT row_count]
    value:
        {expr | DEFAULT}
    assignment:
        col_name = value
    assignment_list:
        assignment [, assignment] ...
```



```mysql

```

### || Palavras Reservadas ||
