![image](https://user-images.githubusercontent.com/44026423/125207967-27f76b80-e266-11eb-9f03-de62c59f6699.png)

A Rossmann é uma das maiores redes de drogarias da Europa, com cerca de 56 mil funcionários e mais de 4 mil unidades. Com o grande sucesso da marca, a empresa planeja uma reforma geral a fim de renovar e padronizar a estética de todas as suas lojas.

Para essa reforma ser possível a equipe de negócios da Rossmann precisaria contar com as previsões de vendas de todas as unidades para as próximas seis semanas, porém, atualmente a previsão de vendas é feita através de uma planilha Excel, considerando apenas a média das vendas, que em muitos casos, resulta em uma previsão muito distante do valor real. Diante disso, a empresa decidiu contratar um cientista de dados para ficar ciente de qual é a melhor solução para o problema.

Durante a reunião de negócios, o cientista de dados explicou os detalhes de uma previsão de vendas, bem como os metódos que poderiam ser utilizados. Ao final da reunião, ficou a cargo do cientista de dados montar um modelo de previsão de vendas para responder a seguinte questão:

**Quanto cada unidade venderá nas próximas seis semanas?**

[![forthebadge made-with-python](http://ForTheBadge.com/images/badges/made-with-python.svg)](https://www.python.org/)

# Dicionário de Dados

As seguintes suposições foram feitas sobre o problema de negócio:
- Os dados estão em formato estruturado e serão disponibilizados em arquivos "csv".
- Os dias em que as unidades estiveram fechadas serão removidos da análise.
- Apenas unidades com valores de vendas maiores que zero serão consideradas.
- Para as unidades que não possuirem a informação da distância do concorrente mais próximo (CompetitionDistance), iremos considerar um valor bem acima dos observados.

Além disso, também foi disponibilizado o dicionário de dados:

| Variáveis                        | Descrição                                                    |
| -------------------------------- | ------------------------------------------------------------ |
| Store                            | código de identificação de cada unidade da drogaria.         |                          |
| DayOfWeek                        | dia da semana do registro.                                   |
| Store                            | Um id único para cada loja                                   |
| Sales                            | O volume de vendas para qualquer dia                         |
| Customers                        | O número de clientes em um determinado dia                       |
| Open                             | Um indicador para saber se a loja estava aberta: 0 = fechada, 1 = aberta |
| StateHoliday                     | Indica um feriado estadual. Normalmente todas as lojas, com poucas exceções, fecham nos feriados estaduais. Observe que todas as escolas fecham nos feriados e finais de semana. a = feriado, b = feriado da Páscoa, c = Natal, 0 = Nenhum |
| SchoolHoliday                    | Indica se (Loja, Data) foi afetado pelo fechamento de escolas públicas |
| StoreType                        | Diferencia entre 4 modelos de loja diferentes: a, b, c, d  |
| Assortment                       | Descreve um nível de estoque: a = básico, b = extra, c = estendido |
| CompetitionDistance              | Distancia em metros do competidor mais proximo           |
| CompetitionOpenSince[Month/Year] | Dá o ano e mês aproximados em que o concorrente mais próximo foi aberto |
| Promo                            | Indica se uma loja está fazendo uma promoção naquele dia         |
| Promo2                           | Promo2 é uma promoção contínua e consecutiva para algumas lojas: 0 = a loja não está participando, 1 = a loja está participando |
| Promo2Since[Year/Week]           | Descreve o ano e a semana em que a loja começou a participar da Promo2 |
| PromoInterval                    | Descreve os intervalos consecutivos de início da promoção 2, nomeando os meses em que a promoção é iniciada novamente. Por exemplo. "Fev, maio, agosto, novembro" significa que cada rodada começa em fevereiro, maio, agosto, novembro de qualquer ano para aquela loja |
