# 7 - Criação de Subqueries

## _NOTA_: Todo o código apresentado foi feito na linguagem _MySQL_.


### || Funções de STRINGS || (as mais importantes)

- __CONCAT__ - Concatena duas ou mais strings numa só;
- INSTR - Retorna a posição da primeira ocorrência de uma substring numa string;
- LENGTH – Devolve o comprimento de uma string em bytes e em caracteres;
- LEFT - Retorna um número específico de caracteres mais à esquerda de uma string;
- LOWER – Converte uma string para minúsculas;
- LTRIM - Recebe um argumento de string e retorna uma nova string com todos os caracteres de espaço à esquerda removidos;
- REPLACE – Procura e substitui o valor de uma substring numa string;
- RIGHT - Devolve um número específico de caracteres mais à direita de uma string;
- RTRIM - Recebe um argumento de string e retorna uma nova string com todos os caracteres de espaço à direita removidos;
- SUBSTRING - Extrai uma substring de uma string começando de uma posição com um comprimento especificado;
- SUBSTRING_INDEX - Retorna uma substring de uma string antes de um número especificado de ocorrências de um delimitador;
- TRIM - Remove caracteres indesejados de uma string;
- FIND_IN_SET - Encontra uma string dentro de uma lista de strings separadas por vírgulas;
- FORMAT(N, D, locale) - Formata um número N para D casas decimais. O locale é um argumento opcional que determina os separadores de milhar e o agrupamento entre os separadores.
- UPPER – Converte uma string para maiúsculas

-------------------------------------------------------------------------------------------

### || ORDENAR Registos de COLUNAS (ORDER BY) ||

ORDER BY permite que as linhas sejam apresentadas por _ordem_ __ascendente (ASC)__ ou __decrescente (DESC)__ de qualquer coluna ou combinação de colunas. 

__ATENÇÃO__: A cláusula ORDER BY deve ser sempre a __última cláusula__ da instrução SELECT.


-------------------------------------------------------------------------------------------

### || AGRUPAR Registos de COLUNAS (GROUP BY) ||

GROUP BY pode ser usada em diferentes contextos:

- A) Uso em alternativa ao SELECT DISTINCT(<nome coluna>)
  
```mysql
SELECT DISTINCT localidade FROM pacientes;
SELECT localidade FROM pacientes GROUP BY localidade;
```

-
-
-
