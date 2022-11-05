# Cyclistic - Insight Project


## Conhecendo o Negócio:

A CYCLISTIC é uma empresa fictícia de compartilhamento de bicicletas em Chicago. O diretor de marketing acredita que o sucesso futuro da empresa depende da maximização do número de planos anuais contratados. Portanto, sua equipe quer entender como os ciclistas casuais e os membros anuais usam as bicicletas da Cyclistic de forma diferente. A partir desses insights, sua equipe criará uma nova estratégia de marketing para converter passageiros casuais em membros anuais.

#### Acesse o Link e faça sua própria análise:
<  https://public.tableau.com/views/DashboardCyclistic_16673119130170/Painel1?:language=pt-BR&:display_count=n&:origin=viz_share_link>

(*aplicação web para visualização dos dados, contém : gráficos e mapa interartivo*.)
________________________________________________________________________________________________

## 1. Questão de negócio

Criar estratégias de marketing destinadas a converter passageiros casuais em membros anuais.

Perguntas a serem respondidas:

1.Como os membros anuais e os ciclistas casuais usam as bicicletas da Cyclistic de forma diferente?

2.Por que os passageiros casuais iriam querer adquirir planos anuais da Cyclistic?

3.Como a Cyclistic pode usar a mídia digital para influenciar os passageiros casuais a se tornarem membros?

## 1.1. Entendendo os dados

A base de dados é referente as viagens realizadas no ano de 2020 entre Janeiro e Novembro ( o mês de abril não estava disponível) na cidade de Chicago

| Atributo    |    Definição      |
|-----|----------|
| ride_id    | Número de identificação único da viagem.         |
| rideable_type| Tipo da bicicleta |
|  started_at| 	início da viagem |
|  ended_at| 	termino da viagem |
|   start_station_name|  Nome da estação onde iniciou a viagem |
| end_station_name| 	Nome da estação onde finalizou a viagem |
| start_station_id|	id da estação onde iniciou a viagem|
|end_station_id| id da estação onde finalizou a viagem |
|start_lat|Latitude da viagem inicial|
|start_lng|Longitude da viagem inicial |
|end_lat|Latitude da viagem final|
|end_lng|Longitude da viagem final|

## 1.2. Novas Features
Essas colunas foram criadas para a base de dados original.

| Feature |    Definição      |
|-----|----------|
|ride_distance_km| Distância percorrida na viagem|
|year|Ano da viagem|
|month| Mês da viagem|
|day| Dia da viagem|
|type_week_numeric| Tipo da semana numerico|
|type_week_categoric|Tipo da semana (Semana e Fim de semana|
|trip_duration|Duração da viagem|
|trip_start_hour| Horaque iníciou a viagem|
|season|Estação do ano|
|start_user_total| Total de usuários que iniciaram a viagem em determinado ponto da cidade|
|end_user_total|Total de usuários que terminaram a viagem em determinado ponto da cidade|


## 2. Premissas de negócio

- Haviam muitos dados faltantes, as estações de bike onde não tinha nomes definidos foi alterado para UNKNOWN.
- A classificação da coluna type_week_numeric foi definida como: 0 = Segunda-feira até 6 = Domingo.
- Os valores iguais a 0 na coluna start_station_id e end_station_id são estações que não foram identificadas.
- Localização, distancia e pontos turísticos são os principais fatores nas viagens.
- A sazonalidade tem grande impacto nas viagens, onde as estações mais quentes apresentam maiores viagens.

## 3. Planejamento da solução
O planejamento foi dividido em três etapas:

### 3.1. Produto Final
- Relátorio com os lugares de maiores retiradas e depositos de bikes por usuários casuais.  
- Dashboard em nuvem com gráficos e mapa interativo.     

### 3.2. Ferramentas
- Python 3.10.4     
- Jupyter Notebook  
- Tableau 

### 3.3. Processo
Para responder as perguntas de negócio, após a coleta dos dados, foi realizado o processamento e transformação, limpezas necessárias e análise exploratória.

#### 1. Como os membros anuais e os ciclistas casuais usam as bicicletas da Cyclistic de forma diferente?

 - Os membros Anuais preferem frequentar centros urbanos onde possuem bares e lojas.
 - Os Casuais preferem visitar Parques , Praças e Lagos.
 - Em média os usuários casuais passam mais tempo pedalando, cerca de 66% a mais.
 - Em média a distância percorrida entre os usuários casuais é 23% maior que os membros anuais.
 - Houve um aumento de 20% dos usuários casuais usanso as bikes no fim de semana.
 - Os membros Anuais usam a bike mais cedo as 8:00am enquanto casuais começam usar as 10:00am, enquanto no período da tarde e noite há um fluxo maior de usabilidade entre os dois usuários durante as 17h e 19h.
 - Durante esses 10 meses mais de 2500 usuários usaram as bicicletas durante a madrugada, entre 00:00 e 5:00 hrs. Os membros Anuais são 30% maior que casuais.
 - Usuários casuais usam mais bikes no final de semana, cerca de 2% ou 13.500 a mais que anuais.
 - Comparando os Casuais entre a semana e fim de semana, cerca de 27% ou 200 mil usam durante a semana.
 - Verão e Outono são as estações mais frequentadas por Casuais e Membros Anuais.
 - No inverno os usuários casuais representam 0,61% do total de 100% dividido por estações e tipo de usuário, parece pouco, mas são 20.000 viagens.
 ----------
 - Principais insights do relatório dos lugares mais frequentados por casuais:
   - A principal estação do ano é o inverno.
   - O principal foco é ir patinar no gelo.
   - Todos vão no mês de Janeiro.
   - A segundas maiores atrações são Teatro, Restaurante e Museu.

#### 2. Por que os passageiros casuais iriam querer adquirir planos anuais da Cyclistic?  

- RECOMENDAÇÔES:
    - Um plano Anual apenas para o finais de semana.
    - Um plano Anual Familia.
    - Programa de pontos acumulados em km, ganhando cupons de desconto para trocar com parceiros nos pontos mais frequentados.
    - Descontos para Usuários novos.
    - Descontos parceria em teatros, cinemas e Museus.
    - cashback por completar desafios anuais.

#### 3. Como a Cyclistic pode usar a mídia digital para influenciar os passageiros casuais a se tornarem membros?

- A Cyclistic pode utilizar os meios digitais para influenciar os ciclistas casuais a tornarem-se membros ao falar sobre os impactos positivos na saúde pessoal e na saúde do planeta que o programa de partilha de bicicletas proporciona. 

- Os clientes podem ser atraídos por ideias de ajudar a apoiar um estilo de vida saudável, melhorar a qualidade do ar, reduzir o tráfego e o congestionamento.

- Geração de Leads usando cookies visitas no app/site.

- Fazer parcerias com digitais influencers e lançar cupom de desconto para novos usuários.

- Propaganda em podcast de saude e bem estar.

- Publicidade em todas as redes sociais.

- Publicidade atrás dos onibus da prefeitura.

- Divulgações de eventos e dicas pelo app.


## 4. Os 10 principais insights dos dados

#### H1. No verão a frequencia de usuarios aumentam 30% em relação ao inverno    
**Verdadeiro:**  A porcentagem no verão é de 80% maior em relação ao inverno. 
_______________
#### H2. Em agosto o numero de usuarios caiu 20% em relação a julho.  
**Falso.** O numero de usuarios aumentou em quase 11%.
_______________

#### H3. No feriado de São Patricio o volume de usuarios aumentaram  
**Falso.**  O Numero de usuários caiu mais de 60% comparando com o melhor dia sem feriado. 
Nesse mês de março o dia 8 teve um pico de usuários atipico, onde ocorreu uma carreata sobre o dia internacional da mulher.
_______________

#### H4. No inverno os depositos de bikes no centro são mais frequentes por usuarios anuais.
**Verdade.**  Maior parte dos dados está desconhecido. Mas a maioria prefere depositar as bikes na Canal St & Adams St, localização de vários restaurantes e do principal metrô (chicago Union Station).
_______________
#### H5. Nos finais de semana a porcentagem de usuários casuais aumentaram em 20%. 
**Verdadeiro.** A porcentangem de usuários aumentou 27% nos finais de semana.
_______________
#### H6.A cada mês há um aumento de 10% de usuários casuais.  
**Falso.**  A porcentagem de clientes por mês é muito váriavel e não possui padrões.
_______________
#### H7. Qual a diferenca de horarios entre usuarios, considerando dia, tarde e noite.  
O horário de pico dos membros anuais é as 8h, 17h e 19h. 
O horário de pico dos casuais é as 10h , 17hr e 19h.
______________

## 5. Conclusão e próximos passos

Todas as perguntas do diretor de marketing foram respondidas, trazendo insights através de hipóteses e gerando novas ideias estratégicas para conversão de membros casuais para anuais.

