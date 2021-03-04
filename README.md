# Dashboard--Estoque

Essa é apenas uma dashboard de visualização de dados contendo algumas medidas calculadas e relacionamento de tabelas.\
This is a data visualization on Power BI with some measures and data relationships.



## Explicando os Painéis / Explaining the Panels

Primeiro, segundo e terceiro painel temos um cartão com o período, que você consegue filtrar e utilizar para outras coisas, uma etiqueta para escolher o produto e a imagem do produto.

In the first, second, and third panels, we have a card with the period of the inventory, one card with an option of product to choose and a card with the image.

\
No terceiro painel temos um grafico de hierarquia com as quantidades de movimentações por localização e também mostra qual foi a movimentação.

In the third panel, we have a hierarchical tree graph that shows the total movement for each local and the type of movement.

\
No quarto painel temos um indicator que mostra a porcentagem de devoluções.
In the fourth panel, we have an indicator that shows the percentage of devolutions.

\
\
Medidas usadas/the measures:

Devolução/Devolution percentage
```
% Devolucao = [TotalDevolucoes]/[TotalVendas]
```

Saldo/Balance
```
Saldo = SUM('Movimentacoes Estoque'[Quantidade Movimentação])
```

Devolução/Devolution 
```
TotalDevolucoes = CALCULATE(
     SUM('Movimentacoes Estoque'[Quantidade Movimentação]), 
     'Movimentacoes Estoque'[Tipo] = "Devolução"
 )
```

Vendas/sales
```
TotalVendas = -CALCULATE(
     SUM('Movimentacoes Estoque'[Quantidade Movimentação]),
     'Movimentacoes Estoque'[Tipo]="Saída"
)
```

The relationship with these two tables was linked by "ID of the Product"
![This is a alt text.](https://github.com/msoaresrocha/Dashboard--Estoque/blob/main/Dashboard%20Estoque/Relationship.jpg)

\
\
The dashboard
![This is a alt text.](https://github.com/msoaresrocha/Dashboard--Estoque/blob/main/Dashboard%20Estoque/Foto%20Dashboard%20Estoque.jpg)
