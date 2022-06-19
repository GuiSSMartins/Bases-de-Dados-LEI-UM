# | Teste 2022 - HDR |

## 0) Identificação de Entidades (e seus atributos + chaves)

__NOTA:__ Não é pedido no teste para o fazer, é apenas uma forma de organizar os dados antes de iniciar a resolução dos exercícios!

## 1) Definição do Sistema

### - CONTEXTUALIZAÇÃO

A HDR (_Hand-Delivery Requests_) é uma empresa que se dedica _em exclusivo_ à entrega de encomendas pessoais. Os seus clientes entregam à HDR as encomendas que querem que sejam entregues num determiando lugar, num determinado momento e a uma determianda pessoa.

### - FUNDAMENTAÇÃO
(Não especificada no enunciado) 

__Possível "porquê" da criação desta base de dados__: As bases de dados são essenciais para o bom funcionamento de qualquer organização.

### - VIABILIDADE
(Não especificada no enunciado)

## 2) Levantamento dos Requisitos

### - Requisitos de DESCRIÇÃO

__RD1__ - Para que um cliente possa enviar uma encomenda, o cliente tem de estar registado na base de dados da HDR, sendo que devem estar os seguintes dados: número, nome

### - Requisitos de MANIPULAÇÃO

__RM1__ - Quando um funcionário aprova um pedido, o funcionário tem que lhe atribuir um número  específico, prrenche a data de aprovação

### - Requisitos de CONTROLO

__RC1__ - Para que um cliente possa enviar uma encomenda (ou seja, para a HDR fazer uma entrega), o cliente tem de estar registado com os dados completos (ver _RD1_) na base de dados da HDR. SENÃO, o seu pedido de entrega não será aceite pela empresa.

__RC2__ - (Ver _RM1_) O funcionário deve ter acesso à base de dados para puder inserir os dados necessários, caso 

## 3) Modelo Conceptual

# (POR FAZER)

## 4) Modelo Lógico

Atenção: As chaves __Primárias__ devem ser as 1ª a identificar dentro de cada tabela, enquanto que
         as chaves __Estrageiras__ devem ser as últimas.
         
# (POR FAZER)

## 5) Implementação física da Base de Dados
__(para 2 entidades e um relacionamento entre elas)__

```mysql
CREATE DATABASE IF NOT NULL hdr;

USE hdr;

CREATE TABLE IF NOT EXISTS Encomenda (
         Num_enc INT NOT NULL AUTOINCREMENT,
         Descricao TEXT NOT NULL,
         Custo_servico INT,
         Data_aprovacao DATE,
         Id_latitude INT,
         Id_longitude INT,
         
         PRIMARY KEY (Num_enc),
         FOREIGN KEY (Id_latitude, Id_longitude)
                  REFERENCES Lugar(Id_latitude, Id_longitude)
);

CREATE TABLE IF NOT EXISTS Lugar (
         Id_latitude INT NOT NULL,
         Id_longitude INT NOT NULL,
         Latitude VARCHAR(30) NOT NULL,
         Longitude VARCHAR(30) NOT NULL,
         Rua TEXT NOT NULL,
         Local TEXT NOT NULL,
         
                  PRIMARY KEY(Id_latitude, Id_longitude)
);


``` 
