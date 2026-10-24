# 15/10/2026

## Base de Dados

Ao importar as bases de dados para o Power BI, automaticamente ele construiu relacionamentos com base nas colunas.

## Tratamentos que julgo necessários

### Problemas nas tabelas Metas

*Códigos no formato errado*

Nas tabelas metas_valor e metas_quantidade existem colunas chamadas codigo_profissional, codigo_vendedor, codigo_servico e codigo_grupo_servico que possuem algumas linhas vazias. Isso fez com que o Power BI automaticamente importasse essa coluna como tipo Text, impossibilitando que o Power BI criasse de forma automática o relacionamento dessas tabelas com outras como Vendedores e profissionais.

lembrete: ver se realmente as perguntas vão ser necessarias. 

Para resolver isso, proponho modificar o tipo da coluna, de texto para int, possibilitando que o Power BI relacione as tabelas automaticamente.

*Coluna mês*

A coluna mês aparece como número inteiro serial, sendo ideal transformar esse valor para o tipo data no Power Query. Mesmo que os nomes sejam diferentes, podemos relacionar a coluna mês com a coluna data na tabela calendário para estabelecermos o relacionamento ideal, permitindo que os filtros de data funcionem corretamente nas tabelas de metas.

### Valores monetários

Tabelas como vendas e itens_venda possuem valores como valor_bruto, valor_desconto, valor_liquido, valor_unitario e meta_valor salvos como tipo inteiro, sendo necessário modificar para o tipo número decimal para termos maior precisão monetária e evitar problemas com cálculos futuros.