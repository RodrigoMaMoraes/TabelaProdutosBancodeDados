## Atividade individual - Tema: Tabela Produtos (AGRUPAMENTO E AGREGAÇÃO)

## Descrição
Entrega de atividade individual da materia de Banco de Dados.

## ETAPA 1

Estou criando uma tabela chamada "Produtos" no banco de dados. 
A tabela tem várias colunas, incluindo "ID_produto" (chave primária com incremento automático), "Nome", "Preco", "Estoque", "Perecivel", "Marca" e "Nacionalidade".

CREATE TABLE Produtos (
	ID_produto 	INT AUTO_INCREMENT PRIMARY KEY,
	Nome VARCHAR(255) NOT NULL,
	Preco DECIMAL(10,2) NOT NULL,
	Estoque INT NOT NULL,
	Perecivel BOOLEAN NOT NULL,
	Marca VARCHAR(255),
	Nacionalidade VARCHAR(255)
);


Aqui estou inserindo múltiplos registros (linhas) na tabela "Produtos". 
Cada registro corresponde a um produto e coloca valores para as colunas "Nome", "Preco", "Estoque", "Perecivel", "Marca" e "Nacionalidade".

INSERT INTO Produtos 
(Nome, Preco, Estoque, Perecivel, Marca, Nacionalidade)
VALUES ("Maça Verde", 2.99, 100, TRUE, "Apple Happy", "Brasil"),
	   ("Camisa Azul", 24.99, 30, FALSE, "Camisa Lisas", "Brasil"),
       ("Queijo Gouda", 9.99, 50, TRUE, "Fazenda Minas Frescas", "Brasil"),
       ("Notebook HP", 999.99, 20, FALSE, "HP", "China"),
       ("Sabonete Palmolive", 0.99, 200, FALSE, "Palmolive", "Brasil");


/Retorna todos os registros da tabela "Produtos", exibindo todos os campos de todos os produtos.

SELECT * FROM produtos;

![DadosInseridos](https://github.com/RodrigoMaMoraes/TabelaProdutosBancodeDados/blob/main/RelatoriosBD/DadosInseridos.png)

## ETAPA 2

/* Retorna o número de registros (produtos) na tabela "Produtos" contando a quantidade de valores na coluna "ID_produto". */
SELECT COUNT(ID_produto) FROM produtos;

![Count](https://github.com/RodrigoMaMoraes/TabelaProdutosBancodeDados/blob/main/RelatoriosBD/SelectCount.png)

/* Vai calcular a média dos valores na coluna "Preco" da tabela "Produtos" e retorna o resultado. */
SELECT AVG(Preco) FROM produtos;

![AVGpreco](https://github.com/RodrigoMaMoraes/TabelaProdutosBancodeDados/blob/main/RelatoriosBD/SelectAVGpreco.png)

/* Vai ser calculado a média dos preços agrupados por valores da coluna "Perecivel" e retorna os resultados separados por essa coluna. */
SELECT AVG(Preco), Perecivel FROM produtos GROUP BY (Perecivel);

![AVGPrecoPerecivel](https://github.com/RodrigoMaMoraes/TabelaProdutosBancodeDados/blob/main/RelatoriosBD/SelectAVGPrecoPerecivel.png)

/* Vai Calcular a média dos preços agrupados por valores da coluna "Nome" dos produtos e retorna os resultados. */
SELECT AVG(Preco), Nome FROM produtos GROUP BY (Nome);

/* Vai calcular a média dos preços e a soma dos valores na coluna "Estoque" de todos os produtos na tabela "Produtos" e retorna os resultados em uma única linha. */
SELECT AVG(Preco), SUM(Estoque) FROM Produtos;

/*  Seleciona o nome, a marca e o estoque do produto com o preço mais alto (ordenado de forma descendente) e limita o resultado a apenas um registro. */
SELECT Nome, Marca, Estoque from Produtos ORDER BY Preco DESC LIMIT 1;

/* Retorna todos os campos de produtos cujo preço seja maior que a média de preços de todos os produtos na tabela. */
SELECT * FROM produtos WHERE Preco > (SELECT AVG(Preco) from Produtos);

/* Calcula a soma dos valores na coluna "Estoque" agrupados por valores na coluna "Nacionalidade" dos produtos e retorna os resultados. */
SELECT Nacionalidade, SUM(Estoque) from produtos GROUP BY Nacionalidade;

/* Retorna todos os registros da tabela "Produtos", exibindo todos os campos de todos os produtos. */
SELECT * FROM produtos;
