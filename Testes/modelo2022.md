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

- __Investigador__ : nome completo, data de nascimento, nº da cédulo profissional (chave primária)
- __Dossier__ : número único, data de criação, nome da entidade, (chaves estrangeiras das várias atividades 

## 1) Definição do Sistema

### - CONTEXTUALIZAÇÃO

Uma agência de detetives tem a trabalhar para si dez investigadores, cada um deles associado a uma área de investigação específica. Os casos que são entregues à agência para investigação são distribuídos pelos vários detetives, de acordo com a sua área de investigação.

### - FUNDAMENTAÇÃO

### - VIABILIDADE

## 2) Levantamento dos Requisitos

### - Requisitos de DESCRIÇÃO

__RD1__ - Os investigadores, para que possam trabalhar na agência, têm de indicar o seu nome completo, a sua data de nascimento, o número da sua cédula profissional e, pelo menos, dois endereços de email e dois números de telefone.

__RD2__ - Cada área de investigação deve ser identificada (crime, fraude, rapto, etc.).

__RD3__ - 

### - Requisitos de MANIPULAÇÃO

__RM1__ - 

### - Requisitos de CONTROLO

__RC1__ - 

## 3) Modelo Conceptual

# (POR FAZER)

## 4) Modelo Lógico

Atenção: As chaves __Primárias__ devem ser as 1ª a identificar dentro de cada tabela, enquanto que
         as chaves __Estrageiras__ devem ser as últimas.
         
# (POR FAZER)

## 5) Implementação física da Base de Dados
__(para 2 entidades e um relacionamento entre elas)__

```sql
CREATE DATABASE IF NOT EXISTS 'modelo';

USE DATABASE 'modelo';

CREATE TABLE IF NOT EXISTS 'investigador' (
  
  
  
  )
``` 

## 6) Povoamento e exploração da Base de Dados
__(povoamento de duas tabelas que estejam relacionadas entre si)__
