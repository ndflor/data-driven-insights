# data-driven-insights
Neste projeto, explorei a base de dados de vendas simuladas encontrada em kaggle com 2.823 linhas e 25 colunas, contendo informações detalhadas sobre pedidos, clientes, produtos, datas e valores financeiros.
Descobri que a base oferece um retrato bastante completo de cada transação, desde o número do pedido, quantidade encomendada e preço unitário, até dados do cliente como nome, cidade e etc. Segue abaixo um Markdown sobre cada passo.

# 1. Visão Geral da Base
Ao rodar o `df.head()`, já foi possível perceber que essa base traz um retrato completo de cada pedido: desde o número do pedido, quantidade encomendada e preço unitário, até o total da venda, data do pedido, status de envio e dados detalhados do cliente, como nome, cidade, país e até o tamanho do negócio.

A análise dos tipos de dados (`df.dtypes`) mostrou que as informações estão organizadas em três tipos principais:
- **Números inteiros:** identificam e quantificam elementos, como número do pedido, quantidade de itens, trimestre ou ano do pedido.
- **Ponto flutuante:** valores com casas decimais, usados para preços unitários, sugeridos e totais.
- **Strings:** textos, como nome do cliente, cidade, país e data do pedido (ainda em formato texto).

# 2. Perfil dos Clientes e Produtos

Ao listar os cinco primeiros clientes, notei que são empresas variadas, desde lojas de brinquedos até ideias para presentes corporativos, mostrando diversidade no público atendido. 
O dicionário produto-categoria indicou que o produto com código 'S10_1678' pertence à categoria **Motorcycles**, o que sugere que a base contém produtos especializados.
Na tupla da primeira linha, o pedido número 10107 feito pela empresa “Land of Toys Inc.” teve um valor de venda total de R$ 2.871,00, evidenciando a relevância financeira das transações individuais.

# 3. Análise Condicional e Laços

Ao aplicar uma condição sobre o primeiro valor da coluna SALES, identifiquei que a venda foi classificada como “intermediária” (valor > 2000), indicando transações financeiras consideráveis já no início da base.
A soma dos cinco primeiros valores de vendas totalizou R$ 18.473,21, reforçando que os registros iniciais representam negócios de impacto financeiro significativo.
O laço while indicou que somente na quinta transação foi registrada uma venda superior a R$ 4.000, demonstrando que valores muito altos são menos frequentes no começo do conjunto.


# 4. Consistência e Simulação de Descontos

Comparando a coluna SALES com o produto QUANTITYORDERED * PRICEEACH, percebi que a maioria das transações apresentou diferença zero ou próxima disso, confirmando a consistência dos dados. 
Porém, uma transação específica apresentou uma diferença de R$ 305,27, indicando possíveis custos adicionais (taxas, frete) ou inconsistência.
A coluna simulada **Desconto** (10% sobre SALES) evidenciou uma economia potencial entre R$ 258 e R$ 520 nas primeiras transações, o que pode representar ganho considerável para o consumidor.


# 5. Operações com Arrays NumPy

Um array criado a partir da coluna QUANTITYORDERED revelou que a soma dos cinco primeiros registros é 199, com média de aproximadamente 35 unidades por pedido, indicando pedidos de porte médio a grande no início do período.


# 6. Filtragem e Agrupamento

Filtrando por pedidos com QUANTITYORDERED > 40, percebi que estes correspondem principalmente a compras em grande volume feitas por clientes corporativos, revendedores e compradores estratégicos, possivelmente em datas promocionais ou para reposição de estoque.
A análise de frequência na coluna PRODUCTLINE mostrou que as categorias **Motorcycles** e **Classic Cars** são as mais frequentes nesses pedidos, reforçando o foco do negócio nesses segmentos.


# 7. Visualizações

- O gráfico de vendas mensais mostrou menor volume nos meses de junho a setembro de 2003, com picos de vendas em novembro de 2003 e 2004.

- No gráfico de barras, a categoria **Classic Cars** lidera as vendas, seguida por **Vintage Cars** e **Motorcycles**, respectivamente.

- O gráfico de dispersão indicou maior concentração de vendas para quantidades entre 20 e 50 unidades, com baixa recorrência para pedidos menores que 20, mas dispersões significativas entre 50 e 100 unidades.



# Conclusão

A análise evidenciou que a base possui dados completos e coerentes, com clientes e produtos diversificados. As vendas apresentam uma variação significativa, com pedidos médios a grandes predominando, especialmente nas categorias de veículos clássicos e motocicletas. A sazonalidade é clara, com picos de vendas no final do ano, e há potencial para aplicação de descontos que beneficiem os consumidores.

Confira essa análise em: https://colab.research.google.com/drive/1F8kS6rWzyRr6xRG7b_kcUwnDAj-N-3YT?usp=sharing
