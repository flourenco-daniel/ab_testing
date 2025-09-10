Teste Técnico: Análise de Teste ABC

Imagine que estamos realizando um Teste ABC para avaliar o impacto de uma nova
funcionalidade na nossa base de clientes. Os clientes foram aleatoriamente
designados a um dos seguintes grupos:

● Grupo A (Controle): Clientes que não foram expostos à nova funcionalidade
● Grupo B (Variante): Clientes que foram expostos à nova funcionalidade.
● Grupo C (Variante): Clientes que foram expostos à outra nova
funcionalidade.

E o objetivo deste teste é entender o desempenho de cada grupo e selecionar o que
teve a melhor performance para ser nossa funcionalidade de hoje em diante.
Utilizando os dados genéricos do teste_tecnico.zip que está neste link responda
algumas perguntas:

1. Qual grupo você escolheria para ser a nossa funcionalidade? Por que?
2. De acordo com suas análises, o estado do usuário influencia no valor das
vendas?
3. Quais são os estados e cidades com maior valor em vendas? Liste-os em
ordem decrescente.
4. A categoria do produto ou quantidade de itens do pedido influencia no status
no pedido?
5. Sinta-se à vontade para explorar outras métricas que julgar relevantes para
avaliar o sucesso da funcionalidade nova.
Você poderá utilizar a ferramenta você tem mais familiaridade para fazer as análises
e criar os gráficos. Mas será um diferencial se você utilizar SQL para gerar os
resultados, usando a biblioteca Python pandasql, por exemplo. A forma de
apresentar o resultado deste teste cabe a você, mas lembre-se de deixar a memória
de cálculo/códigos expostos para a nossa avaliação.

Documentação dos dados de Vendas Online

1. clientes.csv
Este arquivo contém informações detalhadas sobre os clientes cadastrados na
plataforma.
● cliente_id: Identificador único de cada cliente. INTEGER.
● nome: O nome completo do cliente. STRING.
● email: O endereço de e-mail único do cliente. STRING.
● data_cadastro: A data em que o cliente se registrou na plataforma. DATE.
● cidade: A cidade de residência do cliente. STRING.
● estado: A sigla do estado de residência do cliente (por exemplo, SP, RJ).
STRING.
● grupo: Esta coluna indica o grupo de um Teste A/B ao qual o cliente foi
designado (A para o grupo de controle e B para a variante). STRING.

2. produtos.csv
Este arquivo armazena os detalhes de todos os produtos que estão disponíveis para
venda.
● produto_id: Identificador único de cada produto. INTEGER.
● nome_produto: O nome completo do produto. STRING.
● descricao: Uma breve descrição do produto. STRING.
● preco: O preço unitário de venda do produto. NUMERIC ou BIGNUMERIC.
● categoria: A categoria à qual o produto pertence (por exemplo, Eletrônicos,
Roupas, Alimentos). STRING.

3. pedidos.csv
Este arquivo registra as informações principais de cada pedido realizado pelos
clientes.
● pedido_id: Identificador único de cada pedido. INTEGER.
● cliente_id: O identificador do cliente que fez o pedido. Este campo serve
como uma chave estrangeira, ligando ao cliente_id na tabela clientes.csv.
INTEGER.
● data_pedido: A data e a hora exatas em que o pedido foi efetuado.
TIMESTAMP.
● status: O status atual do pedido (por exemplo, Pendente, Processando,
Enviado, Entregue, Cancelado). STRING.
● valor_total: O valor monetário total do pedido, incluindo todos os itens.
NUMERIC ou BIGNUMERIC.

4. itens_pedido.csv
Este arquivo detalha cada item individual que compõe um pedido. Um único pedido
pode ter um ou mais itens.
● item_id: Identificador único de cada item dentro de um pedido específico.
INTEGER.
● pedido_id: O identificador do pedido ao qual este item pertence. Este campo
serve como uma chave estrangeira, ligando ao pedido_id na tabela
pedidos.csv. INTEGER.
● produto_id: O identificador do produto que foi comprado. Este campo serve
como uma chave estrangeira, ligando ao produto_id na tabela produtos.csv.
INTEGER.
● quantidade: A quantidade do produto específico incluída neste item do
pedido. INTEGER.
● preco_unitario: O preço unitário do produto no momento em que a compra
foi realizada. Este valor pode ser diferente do preco atual na tabela
produtos.csv, caso o preço do produto tenha sido alterado após a compra.
NUMERIC ou BIGNUMERIC.
● subtotal: O subtotal monetário para este item específico do pedido
(calculado como quantidade * preco_unitario). NUMERIC ou BIGNUMERIC