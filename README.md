## Atividade individual - Tema: Tabela Produtos (AGRUPAMENTO E AGREGAÇÃO)

## Descrição
Entrega de atividade individual da materia de Banco de Dados.

## ETAPA 1

/* Estou criando uma tabela chamada "Produtos" no banco de dados. 
A tabela tem várias colunas, incluindo "ID_produto" (chave primária com incremento automático), "Nome", "Preco", "Estoque", "Perecivel", "Marca" e "Nacionalidade". */
CREATE TABLE Produtos (
	ID_produto 	INT AUTO_INCREMENT PRIMARY KEY,
	Nome VARCHAR(255) NOT NULL,
	Preco DECIMAL(10,2) NOT NULL,
	Estoque INT NOT NULL,
	Perecivel BOOLEAN NOT NULL,
	Marca VARCHAR(255),
	Nacionalidade VARCHAR(255)
);


/* Aqui estou inserindo múltiplos registros (linhas) na tabela "Produtos". 
Cada registro corresponde a um produto e coloca valores para as colunas "Nome", "Preco", "Estoque", "Perecivel", "Marca" e "Nacionalidade". */
INSERT INTO Produtos 
(Nome, Preco, Estoque, Perecivel, Marca, Nacionalidade)
VALUES ("Maça Verde", 2.99, 100, TRUE, "Apple Happy", "Brasil"),
	   ("Camisa Azul", 24.99, 30, FALSE, "Camisa Lisas", "Brasil"),
       ("Queijo Gouda", 9.99, 50, TRUE, "Fazenda Minas Frescas", "Brasil"),
       ("Notebook HP", 999.99, 20, FALSE, "HP", "China"),
       ("Sabonete Palmolive", 0.99, 200, FALSE, "Palmolive", "Brasil");


/* Retorna todos os registros da tabela "Produtos", exibindo todos os campos de todos os produtos. */
SELECT * FROM produtos;
