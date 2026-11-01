# Pergunta 5

Pergunta: Qual grupo de servico mais vendeu em valor e qual a sua participacao no total da rede em setembro/2026?

Para responder usei o valor bruto dos itens da tabela fitens_venda, conforme orientacao do desafio.

Medidas criadas na tabela Medidas:

Valor Bruto Itens Venda = SUMX(fitens_venda, fitens_venda[valor_total])

Quantidade de Itens = SUMX(fitens_venda, fitens_venda[quantidade])

Participacao Grupo % = 
DIVIDE(
    [Valor Bruto Itens Venda], 
    CALCULATE([Valor Bruto Itens Venda], ALL(dgrupos_servico))
)

Resultado com filtro em setembro/2026:
- Grupo que mais vendeu: Protocolo
- Valor: R$ 3.277.550,00
- Participacao: 30,9%

No relatorio criei uma tabela com o grupo de servico, valor bruto e a porcentagem de participacao ordenada do maior para o menor. Tambem adicionei o segmentador de mes/ano filtrado em Set/2026 no topo da pagina para pegar o periodo certo.
