# Comando s SQL para modelagem física

## Criar banco de dados
CREATE DATABASE vendas_alanssmeira CHARACTER SET utf8mb4;

## Entrar no banco de dados via cód
USE DATABASE vendas_alanssmeira

## Criar tabela fabricantes
CREATE TABLE fabricantes(
    id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(45) NOT NULL,
);

CREATE TABLE produtos(
    id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(45) NOT NULL,
    preco DECIMAL(8,2) NOT NULL,
    quantidade SMALLINT NULL,
    descricao TEXT(1000) NOT NULL,
    fabricantes_id INT NOT NULL,
);

## Alterando a tebela para  criar um relacionamento por meio de uma chave estrangeira
ALTER TABLE produtos
    ADD CONSTRAINT fk_produtos_fabricantes
    FOREIGN KEY(fabricantes_id) REFERENCES fabricantes(id);