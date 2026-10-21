# Atividade_Instrucoes_SQL

/* Instrucao 1 */
USE vendas_informatica;
SELECT * FROM produto;

/* Instrucao 2 */
USE vendas_informatica
SELECT nome_produto, marca, estoque;

/* Instrucao 3 */
USE vendas_informatica
SELECT nome_produto, categoria, preco_unitario, data_cadastro
FROM produto
ORDER BY narca ASC;

/* Instrucao 4 */
USE vendas_informatica
SELECT nome_produto, marca, estoque, data_cadastro FROM produto ORDER BY data_cadastro ASC;

/* Instrucao 5 */
USE vendas_informatica
SELECT * FROM cliente;

/* Instrucao 6 */
USE vendas_informatica
SELECT nome_cliente, email, cidade, estado FROM cliente;

/* Instrucao 7 */
USE vendas_informatica
SELECT nome_cliente, cidade, estado FROM cliente ORDER BY estado ASC;

/* Instrucao 8 */
USE vendas_informatica
SELECT nome_cliente, email, estado FROM cliente ORDER BY data_cadastro  DESC;

/* Instrucao 9 */
USE vendas_informatica
SELECT * FROM venda;

/* Instrucao 10 */
SELECT cliente.nome.cliente, data_venda, preco_unitario_venda, forma_pagamento FROM cliente INNER JOIN venda;

/* Instrucao 11 */

/* Instrucao 12 */
USE vendas_informatica;
SELECT produto.nome_produto, produto.preco_unitario, venda.forma_pagamento FROM produto INNER JOIN venda 
ON venda.id_produto = produto.id_produto
WHERE venda.forma_pagamento IN ("pix", "boleto");

/* Instrucao 13 */
USE vendas_informatica
SELECT nome_produto, desconto, forma_pagamento, FROM produto ORDER BY data_venda DESC;
/* Instrucao 14 */

/* Instrucao 15 */

/* Instrucao 16 */
