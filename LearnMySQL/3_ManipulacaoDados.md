# 3 - Manipulação de (Meta)Dados

## _NOTA_: Todo o código apresentado foi feito na linguagem _MySQL_.

- Operações de _inserção_ de dados (__INSERT__): para _povoamento_ da base de dados
- Operações de _modificação_ (__UPDATE__) e _remoção_ de dados (__DELETE__): para _atualização_ dos objetos da base de dados

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

Inserção __simultânea__ de vários registos:
```mysql
INSERT INTO Agents
    (Agent_Id, First_Name, Last_Name)
    VALUES
        ('2','Ralf','Spencer'),
        ('3','Anne','Lopez'),
        ('4','Joseph','Pane');
```

------------------------------------------------------------------------------------------------------

Modificação de __TODOS__ registos de uma tabela:
```mysql
UPDATE Agents
    SET Business_Terms = NULL;
```

```mysql

```

### || Palavras Reservadas ||
