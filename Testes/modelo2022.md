# | Teste MODELO 2022 |

```
Uma agência de detetives tem a trabalhar para si dez investigadores, cada um deles associado a
uma área de investigação específica (crime, fraude, rapto, etc.). Para trabalharem na agência,
os investigadores têm que indicar o seu nome completo, a sua data de nascimento, o número da sua
cédula profissional e, pelo menos, dois endereços de email e dois números de telefone. Os casos
que são entregues à agência para investigação são distribuídos pelos vários detetives, de acordo
com a sua área de investigação. Quando iniciam o seu trabalho, no âmbito de um dado caso, os
investigadores criam um dossier de investigação específico, atribuindo-lhe um número único, uma
data de criação, o nome da entidade que requereu a investigação, o número de dias que têm para o
resolver e o seu número de investigador. À medida que vão trabalhando num dado processo, os
investigadores vão registando tudo aquilo que vão realizando, introduzindo no dossier do
processo, para cada uma das atividades realizadas, a data, a hora e a sua descrição. Além disso,
registam também, todos os contactos realizados, isto é, os nomes das pessoas com que foram
falando, bem como as datas na qual fizeram os contactos. (...)
```

## 0) Identificação de Entidades (e seus atributos + chaves)

__NOTA:__ Não é pedido no teste para o fazer, é apenas uma forma de organizar os dados antes de iniciar a resolução dos exercícios!

- __Investigador__ : nome completo, data de nascimento, nº da cédula profissional (chave primária), pelo menos 2 email e 2 nºs de telefone, nome da área
- __Dossier__ : número único (chave primária), data de criação, nome da entidade que requeriu a investigação, nº de dias que têm para o resolver, nº de investigador (chave estrangeira), (chaves estrangeiras das várias atividades), (chaves estrangeiras das pessoas contactadas)
- __Atividade__ : data, hora, descrição
- __Pessoa contactada__ : nome da pessoa, data do contacto

## 1) Definição do Sistema

### - CONTEXTUALIZAÇÃO

Uma agência de detetives tem a trabalhar para si dez investigadores, cada um deles associado a uma área de investigação específica. Os casos que são entregues à agência para investigação são distribuídos pelos vários detetives, de acordo com a sua área de investigação.

### - FUNDAMENTAÇÃO
(Não especificada explicitamente no enunciado) 

__Possível "porquê" da criação desta base de dados__: As bases de dados são essenciais para o bom funcionamento de qualquer organização. Por isso, para que a agência de investigadores consiga organizar os vários pedidos que recebe de forma é preciso definir e modelar a estrtutura de dados. 

### - VIABILIDADE
(Não especificada explicitamente no enunciado)

## 2) Levantamento dos Requisitos

### - Requisitos de DESCRIÇÃO

__RD1__ - Os investigadores (para que possam trabalhar na agência) têm de indicar o seu nome completo, a sua data de nascimento, o número da sua cédula profissional e, pelo menos, dois endereços de email e dois números de telefone.

__RD2__ - Cada área de investigação deve ser identificada (crime, fraude, rapto, etc.).

__RD3__ - À medida que vão trabalhando num dado processo, os investigadores vão introduzindo no dossier do processo, para cada uma das atividades realizadas, a data, a hora e a sua descrição.

__RD4__ - Também à medida que vão trabalhando num dado processo, os investigadores têm de registar no dossier todos os contactos realizados, isto é, os nomes das pessoas com que foram falando, bem como as datas na qual fizeram os contactos.

# (_POR CONCLUIR_)

### - Requisitos de MANIPULAÇÃO

__RM1__ - Os casos entregues à agência são distribuídos pelos vários agentes, de acordo com a sua área.

__RM2__ - Quando iniciam o seu trabalho, no âmbito de um dado caso, os investigadores criam um dossier de investigação específico.

### - Requisitos de CONTROLO

__RC1__ - Os investigadores vão registando tudo aquilo que vão realizando.

## 3) Modelo Conceptual

![alt text](https://github.com/GuiSSMartins/Bases-de-Dados-LEI-UM/blob/main/Testes/modelo%20conceptual.PNG?raw=true)

## 4) Modelo Lógico

Atenção: As chaves __Primárias__ devem ser as 1ª a identificar dentro de cada tabela, enquanto que
         as chaves __Estrageiras__ devem ser as últimas.
         
# (POR FAZER)

## 5) Implementação física da Base de Dados
__(para 2 entidades e um relacionamento entre elas)__

### | _Tipos de dados que podemos utilizar_ |
- __INT__ ou __INTEGER__ : valores inteiros
- __FLOAT__ ou __REAL__ : valor decimais
- __VARCHAR(n)__ : string com 'n' caracteres
- __TEXT__ : estrutura de dados para Textos GRANDES
- __DATE__ : datas com formato YYYY-MM-DD
- __TIME__ : horas com formato hh:mm:ss
- __DATETIME__ : formato YYYY-MM-DD hh:mm:ss
- __BIT__ e __BOOLEAN__ : 0 -> falso; >0 ->

```mysql
CREATE DATABASE IF NOT EXISTS Modelo;

USE Modelo;

CREATE TABLE IF NOT EXISTS Investigador (
   Num_cedula_profissional INT NOT NULL, -- chave Primária
   Nome VARCHAR(100) NOT NULL,
   Data_nascimento DATE NOT NULL,
   Email VARCHAR(100) NOT NULL,
   Telefone VARCHAR(9) NOT NULL,
      PRIMARY KEY (Num_cedula_profissional)
);

CREATE TABLE IF NOT EXISTS Dossier (
   Numero_dossier INT NOT NULL,
   Data_criacao DATE NOT NULL,
   
   Num_investigador INT NOT NULL, -- chave Estrangeira
      FOREIGN KEY (Num_investigador)
         REFERENCES Dossier()
);
``` 

## 6) Povoamento e exploração da Base de Dados

### a) Povoamento da BD (de duas tabelas que estejam relacionadas entre si)

Vamos fazer para as tabelas correspondentes: _Investigador_ e _Dossier_

```mysql
INSERT INTO Investigador
   (Num_cedula_profissional, Nome, Data_nascimento, Email, Telefone)
   VALUES (20, 'Mateus', 1990-02-05, 'matsql@bd.pt', '00000009');
```

### b) Apresentar duas queries SQL (uma que combine dados entre duas ou mais tabelas e outra que agrupe os dados de uma tabela e apresente os resultados ordenados, segundo critérios arbitrários)

_1ª Query_: 

_2ª Query_ :
