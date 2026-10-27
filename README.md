# Atividade_Instrucoes_SQL

/*Instrução 01: */
SELECT * FROM produto;

/*Instrução 02:*/
SELECT nome_produto,marca,estoque FROM produto;

/*Instrução 03:*/
SELECT nome_produto, categoria, preco_unitario, data_cadastro 
FROM produto 
ORDER BY marca ASC;

/*Instrução 04:*/
SELECT nome_produto, marca, estoque
FROM produto 
ORDER BY data_cadastro DESC;

/*Instrução 05:*/
SELECT * FROM cliente;

/*Instrução 06:*/
SELECT nome_cliente, email, cidade, estado FROM cliente;

/*Instrução 07:*/
SELECT nome_cliente, cidade,
FROM cliente 
ORDER BY estado ASC;

/*Instrução 08:*/
SELECT nome_cliente, email, estado
FROM cliente 
ORDER BY data_cadastro ASC;

/*Instrução 09:*/
SELECT * FROM venda;

/*Instrução 10:*/
SELECT cliente.nome_cliente, data_venda, preco_unitario_venda, forma_pagamento 
FROM cliente 
INNER JOIN venda;

/*Instrução 11:*/
SELECT produto.nome_produto, venda.data_venda, venda.quantidade, venda.status_venda
FROM produto
INNER JOIN venda;

/*Instrução 12:*/
SELECT produto.nome_produto, .produto.preco_unitario, venda.forma_pagamento 
FROM produto 
INNER JOIN venda ON venda.id_produto = produto.id_produto
WHERE venda.forma_pagamento IN ("pix", "boleto");

/*Instrução 13:*/
SELECT cliente.nome_cliente, produto.nome_produto, venda.data_venda, venda.quantidade
FROM cliente 
INNER JOIN venda ON cliente.id_cliente = venda.id_cliente
INNER JOIN produto ON venda.id_produto = produto.id_produto;

/*Instrução 14:*/
SELECT produto.nome_produto, , venda.desconto_percentual, venda.forma_pagamento 
FROM venda 
INNER JOIN cliente  ON venda.id_cliente = cliente.id_cliente 
INNER JOIN produto  ON venda.id_produto = produto.id_produto 
ORDER BY venda.status_venda ASC;



/*Instrução 15:*/
SELECT produto.nome_produto, cliente.nome_cliente, venda.desconto_percentual, venda.forma_pagamento 
FROM produto
INNER JOIN venda ON produto.id_produto = venda.id_produto
INNER JOIN cliente ON venda.id_cliente = cliente.id_cliente ORDER BY status_venda ASC;

/*Instrução 16:*/
SELECT cliente.nome_cliente, cliente.email, produto.nome_produto, produto.marca, produto.categoria, venda.forma_pagamento, venda.status_venda
FROM venda 
INNER JOIN cliente  ON venda.id_cliente = cliente.id_cliente 
INNER  JOIN produto ON venda.id_produto = produto.id_produto 
WHERE venda.status_venda IN ("Cancelada", "Concluída") 
ORDER BY (venda.quantidade * venda.preco_unitario_venda) DESC;
