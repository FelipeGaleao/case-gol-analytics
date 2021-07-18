# Case <i> DS Analytics </i> da Gol Linhas Aéreas
![enter image description here](https://upload.wikimedia.org/wikipedia/commons/thumb/6/6b/LogoGOL-Pref-FundoClaro-RGB.svg/1200px-LogoGOL-Pref-FundoClaro-RGB.svg.png)
Com a paixão pela aviação, cheguei até a paixão pelos dados! Esse repositório contém as respostas para o case analítico de Data Science da Gol Linhas Aéreas. Para o desenvolvimento das respostas, utilizei Python (Pandas, Scipy e a biblioteca Prophet) para fazer forecast e manipulações dos datasets. Você pode acompanhar o vídeo da apresentação neste link: https://youtu.be/ks8rE8wW5-Y


# Perguntas e respostas

### 1- Faça um ranking para o número total de PAX por dia da semana.
|Dia_Semana_Venda|PAX   |RPK     |rank|
|----------------|------|--------|----|
|Quarta-feira    |293025|26263705|1.0 |
|Quinta-feira    |258488|23501102|2.0 |
|Sexta-feira     |255625|23309936|3.0 |
|Sábado          |253467|23201577|4.0 |
|Domingo         |241620|22388695|5.0 |
|Segunda-feira   |236316|23275908|6.0 |
|Terça-feira     |219802|20366840|7.0 |


### 2 - Qual a correlação de sábado e domingo somados com o total de RPK?

A questão não apresenta informações concretas para que seja possível criar uma correlação, uma vez que para que seja possível fazer correlações deve-se, ao mínimo, utilizar duas medidas sendo X e Y em uma escala contínua para que seja possível obter o coeficiente de correlação. Mas, entendo que o enunciado possa ser "Qual a relação de sábado e domingo somados com o Total de RPK", portanto, expressei em porcentagem a soma de RPKs dos dias da semana em relação ao total de RPK.
|Índice       |Dia_Semana_Venda|PAX     |RPK|pct_total         |
|-------------|----------------|--------|---|------------------|
|0            |Quarta-feira    |293025  |26263705|16.181422573115004|
|1            |Quinta-feira    |258488  |23501102|14.479345636721025|
|2            |Sexta-feira     |255625  |23309936|14.361565688019496|
|5            |Segunda-feira   |236316  |23275908|14.340600578667331|
|6            |Terça-feira     |219802  |20366840|12.548284582050458|
|7            |SábadoDomingo   |495087  |45590272|28.088780941426688|


### 3 - Qual a média de ‘Monetário’ por mês por Canal? E a mediana?

|Canal de Venda|Mes_Ano|Média             |Mediana           |
|--------------|-------|------------------|------------------|
|Porta a Porta |01/2017|31320.569487223205|28823.025304702787|
|Porta a Porta |02/2017|31710.148886151375|29711.580145925567|
|Porta a Porta |03/2017|31055.939762396734|30488.191027232337|
|Porta a Porta |04/2017|33319.496262543136|32421.609417997162|
|Porta a Porta |11/2016|34638.07179648989 |30262.9779680581  |
|Porta a Porta |12/2016|28615.452500146082|25527.519294582755|
|TeleVenda     |01/2017|32868.88142893844 |19085.123237539552|
|TeleVenda     |02/2017|32208.445818350272|18926.69023166578 |
|TeleVenda     |03/2017|32132.246712118333|18666.87996923318 |
|TeleVenda     |04/2017|35795.781915059895|28091.885619205026|
|TeleVenda     |11/2016|30963.459348900647|18757.707785280276|
|TeleVenda     |12/2016|28045.721461471967|17567.600937751726|
|Telégrafo     |01/2017|4234.022566694851 |3782.248867662558 |
|Telégrafo     |02/2017|4307.626272827682 |4045.8931311515526|
|Telégrafo     |03/2017|4568.148530922108 |4345.559552216315 |
|Telégrafo     |04/2017|3778.5918347312363|3458.8846660540144|
|Telégrafo     |11/2016|4614.310075629995 |4029.1321305130978|
|Telégrafo     |12/2016|5212.6480551230825|4227.5779481237205|

## 4 - Crie um forecast de PAX por ‘Local de Venda’ para os próximos 15 dias a contar da última data de venda. (Aqui a técnica é livre) 

Para o desenvolvimento do forecast, utilizei o Prophet. Uma biblioteca que consegue  analisar séries temporais onde há sazonalidade não-linear anualmente, semanalmente e até diariamente. Possui um bom comportamento quando envolve dados históricos ou eventos sazonais. Uma dos objetivos da biblioteca é automatizar o maior números de passos para criar um modelo, isso é, ele realiza o tratamento automático de outliers, dados faltantes e mudanças drásticas na série temporal.
![enter image description here](https://i.imgur.com/TwltXMX.png)
Para o canal **Arena**:
|Índice| |Data|realizado|previsto          |Local_Venda|diff|
|------|---|----------|---------|------------------|-----------|----|
|152   |   |2017-04-02|         |3613.2289003886117|Arena      |    |
|153   |   |2017-04-03|         |4428.339130700197 |Arena      |    |
|154   |   |2017-04-04|         |3834.4470673177884|Arena      |    |
|155   |   |2017-04-05|         |4751.662103256286 |Arena      |    |
|156   |   |2017-04-06|         |4275.1955716732755|Arena      |    |
|157   |   |2017-04-07|         |4762.741606399576 |Arena      |    |
|158   |   |2017-04-08|         |5476.285136475091 |Arena      |    |
|159   |   |2017-04-09|         |5052.645419568884 |Arena      |    |
|160   |   |2017-04-10|         |5475.031579675554 |Arena      |    |
|161   |   |2017-04-11|         |4568.213578355617 |Arena      |    |
|162   |   |2017-04-12|         |5016.758763097043 |Arena      |    |
|163   |   |2017-04-13|         |4612.519903920866 |Arena      |    |
|164   |   |2017-04-14|         |3770.168612073834 |Arena      |    |
|165   |   |2017-04-15|         |4057.712330502396 |Arena      |    |
|166   |   |2017-04-16|         |4023.362296146548 |Arena      |    |

Para o canal **Ellipse**: 
|Índice||Data|realizado|previsto          |Local_Venda|diff|
|------|---|----------|---------|------------------|-----------|----|
|152   |   |2017-04-02|         |2838.6496397217406|Ellipsis   |    |
|153   |   |2017-04-03|         |2812.2813283267255|Ellipsis   |    |
|154   |   |2017-04-04|         |3096.344877449639 |Ellipsis   |    |
|155   |   |2017-04-05|         |4048.393451513197 |Ellipsis   |    |
|156   |   |2017-04-06|         |3415.487506259278 |Ellipsis   |    |
|157   |   |2017-04-07|         |3667.1916323117803|Ellipsis   |    |
|158   |   |2017-04-08|         |4005.0673557093796|Ellipsis   |    |
|159   |   |2017-04-09|         |3834.256027813526 |Ellipsis   |    |
|160   |   |2017-04-10|         |3604.444059393158 |Ellipsis   |    |
|161   |   |2017-04-11|         |3544.3568898720932|Ellipsis   |    |
|162   |   |2017-04-12|         |4297.477893174918 |Ellipsis   |    |
|163   |   |2017-04-13|         |3600.3716107880464|Ellipsis   |    |
|164   |   |2017-04-14|         |3223.4286136151263|Ellipsis   |    |
|165   |   |2017-04-15|         |3105.5823668482008|Ellipsis   |    |
|166   |   |2017-04-16|         |2781.9522495041792|Ellipsis   |    |

Para o local **General**:
|||Data|realizado|previsto          |Local_Venda|diff|
|------|---|----------|---------|------------------|-----------|----|
|152   |   |2017-04-02|         |13101.186362377186|           |    |
|153   |   |2017-04-03|         |14109.684601003151|           |    |
|154   |   |2017-04-04|         |13776.868678462655|           |    |
|155   |   |2017-04-05|         |18091.758306906246|           |    |
|156   |   |2017-04-06|         |15598.863024164026|           |    |
|157   |   |2017-04-07|         |17101.6367353117  |           |    |
|158   |   |2017-04-08|         |19567.49666935404 |           |    |
|159   |   |2017-04-09|         |18649.254593392918|           |    |
|160   |   |2017-04-10|         |18442.722191377805|           |    |
|161   |   |2017-04-11|         |16743.65952608422 |           |    |
|162   |   |2017-04-12|         |19671.272664267268|           |    |
|163   |   |2017-04-13|         |16734.69080308465 |           |    |
|164   |   |2017-04-14|         |14145.961004678622|           |    |
|165   |   |2017-04-15|         |14713.330957421786|           |    |
|166   |   |2017-04-16|         |13610.116506964316|           |    |

Para o local **Mindscape**:
|||data|realizado|previsto          |Local_Venda|diff|
|------|---|----------|---------|------------------|-----------|----|
|152   |   |2017-04-02|         |2782.0008234828247|Mindscape  |    |
|153   |   |2017-04-03|         |3192.4404899211586|Mindscape  |    |
|154   |   |2017-04-04|         |3030.758825826591 |Mindscape  |    |
|155   |   |2017-04-05|         |4030.7102901660564|Mindscape  |    |
|156   |   |2017-04-06|         |3357.6749333454636|Mindscape  |    |
|157   |   |2017-04-07|         |3736.4382962497148|Mindscape  |    |
|158   |   |2017-04-08|         |4549.860839679086 |Mindscape  |    |
|159   |   |2017-04-09|         |4347.859705278586 |Mindscape  |    |
|160   |   |2017-04-10|         |4322.596615405706 |Mindscape  |    |
|161   |   |2017-04-11|         |3719.8566687657926|Mindscape  |    |
|162   |   |2017-04-12|         |4345.064705614284 |Mindscape  |    |
|163   |   |2017-04-13|         |3550.157079240933 |Mindscape  |    |
|164   |   |2017-04-14|         |2886.764186209401 |Mindscape  |    |
|165   |   |2017-04-15|         |3243.9930848544163|Mindscape  |    |
|166   |   |2017-04-16|         |2888.825930446255 |Mindscape  |    |

Para o local **Vast**:
|||Data|realizado|previsto          |Local_Venda|diff|
|------|---|----------|---------|------------------|-----------|----|
|152   |   |2017-04-02|         |3880.757307400686 |Vast       |    |
|153   |   |2017-04-03|         |3692.968874739273 |Vast       |    |
|154   |   |2017-04-04|         |3834.2238263064964|Vast       |    |
|155   |   |2017-04-05|         |5283.3667974966675|Vast       |    |
|156   |   |2017-04-06|         |4574.697965022653 |Vast       |    |
|157   |   |2017-04-07|         |4958.4702153908165|Vast       |    |
|158   |   |2017-04-08|         |5558.963569033974 |Vast       |    |
|159   |   |2017-04-09|         |5430.895821552469 |Vast       |    |
|160   |   |2017-04-10|         |5054.004225857698 |Vast       |    |
|161   |   |2017-04-11|         |4923.140485310361 |Vast       |    |
|162   |   |2017-04-12|         |6009.405697721835 |Vast       |    |
|163   |   |2017-04-13|         |4958.060094505757 |Vast       |    |
|164   |   |2017-04-14|         |4234.061704898901 |Vast       |    |
|165   |   |2017-04-15|         |4256.984038222458 |Vast       |    |
|166   |   |2017-04-16|         |3857.2339893979956|Vast       |    |
|162   |   |2017-04-12|         |4345.064705614284 |Mindscape  |    |
|163   |   |2017-04-13|         |3550.157079240933 |Mindscape  |    |
|164   |   |2017-04-14|         |2886.764186209401 |Mindscape  |    |
|165   |   |2017-04-15|         |3243.9930848544163|Mindscape  |    |
|166   |   |2017-04-16|         |2888.825930446255 |Mindscape  |    |

Com base no dataset, o modelo sugeriu que nos próximos 15 dias, teremos um novo pico de vendas. Atingindo seu ápice entre 10 a 14 de Abril. 

## 5 - Supondo que você precisa gerar um estudo para a área responsável, com base em qualquer modelo ou premissa, qual ‘Local de Venda’ você considera mais crítico. Por quê?
Através do modelo gerado, foi gerado uma previsão aos próximos 15 dias. Após dia 02 de Abril, a companhia terá uma ascensão, onde entre dia 06 a 16 de Abril atingirá um pico de passageiros transportados. A empresa deve se preparar com maior número de recursos nos locais de vendas, sobretudo no Vast e Arena, onde aponta o maior pico de passageiros.
## 6- Criar modelo relacionando o comporatamento de venda com variaveis não apresentada nos dados (Ex : PIB, Dolar, e etc)
Para a resolução desta questão,  utilizei o conjunto de dados disponibilizados pela br.investing.com. Para realizar a correlação, utilizei uma janela de tempo de uma semana entre os dois conjuntos de dados. A correlação encontrada entre o número de RPK e ASK durante essa semana foi desprezível conforte  1Vieira (2011). 

## Análise Exploratória do dataset da ANAC

**Quantidade de voos realizados pelas empresas aéreas em Maio de 2021.**
|Empresa|Quantidade de voos|
|----------|------------------|
|AZUL LINHAS AÉREAS BRASILEIRAS S/A|14943             |
|TAM LINHAS AÉREAS S.A.|8144              |
|GOL LINHAS AÉREAS S.A. (EX- VRG LINHAS AÉREAS S.A.)|6892              |
|SIDERAL LINHAS AÉREAS LTDA.|709               |
|PASSAREDO TRANSPORTES AÉREOS S.A.|616               |
|TWO TÁXI AÉREO LTDA.|546               |
|ABSA - AEROLINHAS BRASILEIRAS S.A.|355               |
|MAP TRANSPORTES AÉREOS LTDA.|319               |
|TAP - TRANSPORTES AÉREOS PORTUGUESES S/A|299               |
|COMPAÑIA PANAMEÑA DE AVIACION S.A. (COPA AIRLINES)|276               |

**Análise do RPK e ASK para as 3 empresas aéreas que mais voaram em Maio de 2021.**
|Empresa Aérea                                            |RPK|RPK|RPK|
|---------------------------------------------------|------|----------|------------------|
||Quantidade de registros|Soma|Média|
|AZUL LINHAS AÉREAS BRASILEIRAS S/A                 |14943 |1531705713|102503.2264605501 |
|GOL LINHAS AÉREAS S.A. (EX- VRG LINHAS AÉREAS S.A.)|6892  |1219640321|176964.64320951828|
|TAM LINHAS AÉREAS S.A.                             |8144  |1445463066|177488.0974950884 |

|Empresa Aérea                                            |ASK|ASK|ASK|
|---------------------------------------------------|------|----------|------------------|
||Quantidade de registros|Soma|Média|
|AZUL LINHAS AÉREAS BRASILEIRAS S/A                 |14943 |2020426449|135208.89038345712|
|GOL LINHAS AÉREAS S.A. (EX- VRG LINHAS AÉREAS S.A.)|6892  |1385225282|200990.31950087057|
|TAM LINHAS AÉREAS S.A.                             |8144  |2029668313|249222.533521611  |


**Análise dos TOP 15 trechos da Azul Linhas 	Aéreas, que detém a maior soma de RPK em Maio de 2021.**
|nm_empresa                        |sg_iata_origem|nm_municipio_origem |sg_iata_destino|nm_municipio_destino|Quantidade de Voos|
|----------------------------------|--------------|--------------------|---------------|--------------------|------------------|
|AZUL LINHAS AÉREAS BRASILEIRAS S/A|CNF           |CONFINS             |VCP            |CAMPINAS            |224               |
|AZUL LINHAS AÉREAS BRASILEIRAS S/A|VCP           |CAMPINAS            |CNF            |CONFINS             |219               |
|AZUL LINHAS AÉREAS BRASILEIRAS S/A|POA           |PORTO ALEGRE        |VCP            |CAMPINAS            |216               |
|AZUL LINHAS AÉREAS BRASILEIRAS S/A|VCP           |CAMPINAS            |POA            |PORTO ALEGRE        |215               |
|AZUL LINHAS AÉREAS BRASILEIRAS S/A|VCP           |CAMPINAS            |SDU            |RIO DE JANEIRO      |209               |
|AZUL LINHAS AÉREAS BRASILEIRAS S/A|SDU           |RIO DE JANEIRO      |VCP            |CAMPINAS            |206               |
|AZUL LINHAS AÉREAS BRASILEIRAS S/A|SDU           |RIO DE JANEIRO      |CGH            |SÃO PAULO           |185               |
|AZUL LINHAS AÉREAS BRASILEIRAS S/A|CGH           |SÃO PAULO           |SDU            |RIO DE JANEIRO      |183               |
|AZUL LINHAS AÉREAS BRASILEIRAS S/A|VCP           |CAMPINAS            |CWB            |SÃO JOSÉ DOS PINHAIS|168               |
|AZUL LINHAS AÉREAS BRASILEIRAS S/A|CWB           |SÃO JOSÉ DOS PINHAIS|VCP            |CAMPINAS            |168               |
|AZUL LINHAS AÉREAS BRASILEIRAS S/A|SDU           |RIO DE JANEIRO      |CNF            |CONFINS             |157               |
|AZUL LINHAS AÉREAS BRASILEIRAS S/A|CNF           |CONFINS             |SDU            |RIO DE JANEIRO      |155               |
|AZUL LINHAS AÉREAS BRASILEIRAS S/A|VCP           |CAMPINAS            |BSB            |BRASÍLIA            |150               |
|AZUL LINHAS AÉREAS BRASILEIRAS S/A|BSB           |BRASÍLIA            |VCP            |CAMPINAS            |148               |
|AZUL LINHAS AÉREAS BRASILEIRAS S/A|MAO           |MANAUS              |VCP            |CAMPINAS            |146               |

**Análise dos TOP 15 trechos da GOL Linhas Aéreas que detém a maior soma de RPK em Maio de 2021.**
|nm_empresa                        |sg_iata_origem|nm_municipio_origem |sg_iata_destino|nm_municipio_destino|Quantidade de Voos|
|----------------------------------|--------------|--------------------|---------------|--------------------|------------------|
|GOL LINHAS AÉREAS S.A. (EX- VRG LINHAS AÉREAS S.A.)|SDU           |RIO DE JANEIRO      |CGH            |SÃO PAULO           |168               |
|GOL LINHAS AÉREAS S.A. (EX- VRG LINHAS AÉREAS S.A.)|CGH           |SÃO PAULO           |SDU            |RIO DE JANEIRO      |166               |
|GOL LINHAS AÉREAS S.A. (EX- VRG LINHAS AÉREAS S.A.)|GRU           |GUARULHOS           |BSB            |BRASÍLIA            |102               |
|GOL LINHAS AÉREAS S.A. (EX- VRG LINHAS AÉREAS S.A.)|BSB           |BRASÍLIA            |GRU            |GUARULHOS           |100               |
|GOL LINHAS AÉREAS S.A. (EX- VRG LINHAS AÉREAS S.A.)|CNF           |CONFINS             |GRU            |GUARULHOS           |98                |
|GOL LINHAS AÉREAS S.A. (EX- VRG LINHAS AÉREAS S.A.)|REC           |RECIFE              |GRU            |GUARULHOS           |98                |
|GOL LINHAS AÉREAS S.A. (EX- VRG LINHAS AÉREAS S.A.)|GRU           |GUARULHOS           |REC            |RECIFE              |97                |
|GOL LINHAS AÉREAS S.A. (EX- VRG LINHAS AÉREAS S.A.)|POA           |PORTO ALEGRE        |GRU            |GUARULHOS           |97                |
|GOL LINHAS AÉREAS S.A. (EX- VRG LINHAS AÉREAS S.A.)|GRU           |GUARULHOS           |CNF            |CONFINS             |97                |
|GOL LINHAS AÉREAS S.A. (EX- VRG LINHAS AÉREAS S.A.)|FLN           |FLORIANÓPOLIS       |GRU            |GUARULHOS           |96                |
|GOL LINHAS AÉREAS S.A. (EX- VRG LINHAS AÉREAS S.A.)|GRU           |GUARULHOS           |FLN            |FLORIANÓPOLIS       |96                |
|GOL LINHAS AÉREAS S.A. (EX- VRG LINHAS AÉREAS S.A.)|GRU           |GUARULHOS           |POA            |PORTO ALEGRE        |96                |
|GOL LINHAS AÉREAS S.A. (EX- VRG LINHAS AÉREAS S.A.)|GRU           |GUARULHOS           |FOR            |FORTALEZA           |95                |
|GOL LINHAS AÉREAS S.A. (EX- VRG LINHAS AÉREAS S.A.)|FOR           |FORTALEZA           |GRU            |GUARULHOS           |95                |
|GOL LINHAS AÉREAS S.A. (EX- VRG LINHAS AÉREAS S.A.)|CWB           |SÃO JOSÉ DOS PINHAIS|GRU            |GUARULHOS           |94                |

Tanto a Azul Linhas Aéreas quanto a Gol linhas Aéreas, utilizam o paradigma spoke-hub de distribuição de voos. O paradigma consiste em centralizar os voos em Aeroportos onde há maior número de voos saindo para atender outras cidades, então, os aeroportos onde a movimentação não é tão expressiva deve ser ligados em um Aeroporto onde há o maior número de voos. O spoke-hub está mais presente na Azul, uma vez que seu HUB principal é VCP. Enquanto na Gol, o HUB é GRU e CGH. Diferente da Gol, a Azul teve um número mais expressivo em trechos comuns entre o HUB ao Aeroporto de Confins (CNF). Isso é devido a Azul ter um expressivo número de voos regionais interligado o interior de Minas Gerais a capital e também ser um HUB estratégico da empresa. </p>  <br> <p>Uma outra análise é do trecho mais comum do Brasil: a ponte aérea. A Azul Linhas Aéreas realizou mais de 185 voos entre Santos Dumont (RJ) para Congonhas (SP), enquanto a Gol realizou 168. 

|nm_empresa|Quantidade de voos                       |
|----------|----------------------------------|
|AZUL LINHAS AÉREAS BRASILEIRAS S/A|185                               |
|GOL LINHAS AÉREAS S.A. (EX- VRG LINHAS AÉREAS S.A.)|168                               |

Analisando a fundo a taxa de ocupação, dada pelo RPK dividido pelo ASK, teremos a distribuição da ocupação no trecho SDU-CGH entre a Azul Linhas Aéreas e a GOL Linhas Aéreas.


**Estatística descritiva da distribuição de ocupação (RPK dividido pelo ASK) entre SDU e CGH.**

|Medida|AZUL Linhas Aéreas|GOL Linhas Aéreas|
|------|------------------|-----------------|
|Quantidade de voos|185.0             |166.0            |
|Média|70.57 |83.19|
|Desvio Padrão   |19.43|11.13|
|Ocupação Mínima|33.05             |53.45            |
|Percentil 25%   |52.54             |76.605           |
|Percentil 50%   |72.03             |85.38499999999999|
|Percentil 75%   |88.98             |92.385           |
|Ocupação Máxima |100.0             |99.44            |
Apesar de maior número de voos no trecho SDU-CGH, a Gol Linhas Aéreas apresentou maior média de ocupação, 83.19% de ocupação em seus voos (RPK/ASK), contra 70.57% da Azul Linhas Aéreas.

**Estatística descritiva da distribuição de ocupação (RPK dividido pelo ASK) entre SDU e CGH durante a semana.**

|Empresa|AZUL LINHAS AÉREAS BRASILEIRAS S/A|AZUL LINHAS AÉREAS BRASILEIRAS S/A|AZUL LINHAS AÉREAS BRASILEIRAS S/A|AZUL LINHAS AÉREAS BRASILEIRAS S/A|AZUL LINHAS AÉREAS BRASILEIRAS S/A|AZUL LINHAS AÉREAS BRASILEIRAS S/A|AZUL LINHAS AÉREAS BRASILEIRAS S/A|GOL LINHAS AÉREAS S.A. (EX- VRG LINHAS AÉREAS S.A.)|GOL LINHAS AÉREAS S.A. (EX- VRG LINHAS AÉREAS S.A.)|GOL LINHAS AÉREAS S.A. (EX- VRG LINHAS AÉREAS S.A.)|GOL LINHAS AÉREAS S.A. (EX- VRG LINHAS AÉREAS S.A.)|GOL LINHAS AÉREAS S.A. (EX- VRG LINHAS AÉREAS S.A.)|GOL LINHAS AÉREAS S.A. (EX- VRG LINHAS AÉREAS S.A.)|GOL LINHAS AÉREAS S.A. (EX- VRG LINHAS AÉREAS S.A.)|
|----------|----------------------------------|----------------------------------|----------------------------------|----------------------------------|----------------------------------|----------------------------------|----------------------------------|---------------------------------------------------|---------------------------------------------------|---------------------------------------------------|---------------------------------------------------|---------------------------------------------------|---------------------------------------------------|---------------------------------------------------|
|Dia da semana|Domingo                           |Quarta-feira                      |Quinta-feira                      |Segunda-feira                     |Sexta-feira                       |Sábado                            |Terça-feira                       |Domingo                                            |Quarta-feira                                       |Quinta-feira                                       |Segunda-feira                                      |Sexta-feira                                        |Sábado                                             |Terça-feira                                        |
|Quantidade de voos|28.0                              |22.0                              |28.0                              |35.0                              |30.0                              |19.0                              |23.0                              |26.0                                               |19.0                                               |21.0                                               |33.0                                               |28.0                                               |21.0                                               |18.0                                               |
|Média|89.5892857142857                  |63.51818181818183                 |55.503571428571426                |82.82571428571427                 |65.22666666666666                 |61.057894736842115                |68.68260869565219                 |89.2346153846154                                   |77.07894736842105                                  |83.64285714285715                                  |86.13333333333334                                  |80.11071428571427                                  |79.65714285714286                                  |83.95555555555558                                  |
|Desvio padrão     |7.194150879590091                 |20.006894915399645                |13.450223243166091                |13.465387936071787                |17.478004567975173                |19.81568727014796                 |18.09828349906831                 |8.939482862344658                                  |12.089875421992495                                 |9.503345275668535                                  |11.998090125793633                                 |12.122594126662344                                 |10.35159753026418                                  |6.858761869250525                                  |
|Ocupação Mínima|69.5                              |33.1                              |35.6                              |52.5                              |34.7                              |34.7                              |41.5                              |61.6                                               |55.2                                               |58.2                                               |53.4                                               |53.8                                               |60.1                                               |69.0                                               |
|25%       |86.875                            |45.324999999999996                |44.9                              |70.3                              |47.5                              |44.1                              |54.2                              |86.75                                              |67.1                                               |79.7                                               |82.3                                               |73.52499999999999                                  |71.3                                               |80.275                                             |
|50%       |91.5                              |63.150000000000006                |52.5                              |89.0                              |67.35                             |57.6                              |72.0                              |91.95                                              |80.5                                               |85.3                                               |90.6                                               |81.5                                               |83.7                                               |84.6                                               |
|75%       |94.29999999999998                 |80.75                             |59.55                             |91.95                             |78.6                              |76.25                             |83.9                              |94.475                                             |85.75                                              |91.3                                               |95.3                                               |89.925                                             |87.6                                               |88.94999999999999                                  |
|Ocupação Máxima|100.0                             |96.6                              |92.4                              |97.5                              |94.9                              |93.2                              |97.5                              |98.9                                               |96.6                                               |96.7                                               |99.4                                               |95.4                                               |93.0                                               |95.0                                               |

Em uma análise a média de ocupação nos voos entre SDU e CGH é possível identificar que Domingo e Segunda são os dias mais críticos para a operação da ponte aérea para as duas empresas, sendo que a Gol tem obtido maior ocupação na Segunda-Feira, com 86.14, ao contrário da Azul, que teve 82.23%.

**Destinos GOL que registraram ocupação menor que 50%.**
|IATA Origem|Origem|IATA Destino|Destino|Ocupação (em porcentagem)|
|--------------|-------------------|---------------|--------------------|--------|
|FOR           |FORTALEZA          |BVB            |BOA VISTA           |0.0     |
|BAQ           |BARRANQUILLA       |GYE            |GUAYAQUIL           |0.5376344086021506|
|CKS           |PARAUAPEBAS        |SLZ            |SÃO LUÍS            |27.1505376344086|
|SLZ           |SÃO LUÍS           |CKS            |PARAUAPEBAS         |28.225806451612904|
|GIG           |RIO DE JANEIRO     |EZE            |EZEIZA, BUENOS AIRES PROVINCE|29.03225806451613|
|GYE           |GUAYAQUIL          |GIG            |RIO DE JANEIRO      |29.03225806451613|
|GIG           |RIO DE JANEIRO     |BAQ            |BARRANQUILLA        |29.56989247311828|
|EZE           |EZEIZA, BUENOS AIRES PROVINCE|GIG            |RIO DE JANEIRO      |29.56989247311828|
|GIG           |RIO DE JANEIRO     |SCL            |SANTIAGO            |30.64516129032258|
|SCL           |SANTIAGO           |GIG            |RIO DE JANEIRO      |30.64516129032258|
|ASU           |ASUNCIÓN           |CNF            |CONFINS             |31.72043010752688|
|CNF           |CONFINS            |ASU            |ASUNCIÓN            |31.72043010752688|
|RBR           |RIO BRANCO         |CZS            |CRUZEIRO DO SUL     |40.90392227931404|
|VCP           |CAMPINAS           |SDU            |RIO DE JANEIRO      |43.95445134575569|
|CNF           |CONFINS            |CKS            |PARAUAPEBAS         |44.17562724014337|
|CZS           |CRUZEIRO DO SUL    |RBR            |RIO BRANCO          |44.32460024190774|
|SDU           |RIO DE JANEIRO     |VCP            |CAMPINAS            |44.98511166253102|
|CKS           |PARAUAPEBAS        |CNF            |CONFINS             |45.878136200716845|
|CKS           |PARAUAPEBAS        |BSB            |BRASÍLIA            |48.757763975155285|

Em uma visão macro em relação aos voos executados pela Gol Linhas Aéreas, destaca-se que as piores ocupações foram em novos destinos inaugurados como Paraupebas (27.15% entre CKS-SLZ; 28.22% entre SLZ-CKS) e destinos internacionais como Ezeiza, Santiago, Guayaquil e Barranquilla. Uma hipótese para a baixa ocupação pode ser as restrições e medidas sanitárias de cada destino.

**Destinos GOL que registraram ocupação maior que 90%.**
|IATA Origem|Origem|IATA Destino|Destino|Ocupação  (em porcentagem)|
|--------------|-------------------|---------------|--------------------|--------|
|SDU           |RIO DE JANEIRO     |CWB            |SÃO JOSÉ DOS PINHAIS|98.18404434386676|
|MAO           |MANAUS             |RBR            |RIO BRANCO          |97.31182795698925|
|NAT           |SÃO GONÇALO DO AMARANTE|CNF            |CONFINS             |97.31182795698925|
|JDO           |JUAZEIRO DO NORTE  |GRU            |GUARULHOS           |96.67818740399386|
|GRU           |GUARULHOS          |JDO            |JUAZEIRO DO NORTE   |96.61489446435687|
|NVT           |NAVEGANTES         |CNF            |CONFINS             |96.23655913978494|
|SDU           |RIO DE JANEIRO     |POA            |PORTO ALEGRE        |96.16782458765496|
|IOS           |ILHÉUS             |GRU            |GUARULHOS           |96.01838442639334|
|PVH           |PORTO VELHO        |BSB            |BRASÍLIA            |95.93413978494624|
|BSB           |BRASÍLIA           |CGR            |CAMPO GRANDE        |95.85798816568047|
|BSB           |BRASÍLIA           |REC            |RECIFE              |95.77684276141498|
|SDU           |RIO DE JANEIRO     |SSA            |SALVADOR            |95.77006141700049|
|CGB           |VÁRZEA GRANDE      |BSB            |BRASÍLIA            |95.72452636968767|
|REC           |RECIFE             |GRU            |GUARULHOS           |95.36056704789712|
|CGB           |VÁRZEA GRANDE      |GRU            |GUARULHOS           |95.21584931307729|
|BPS           |PORTO SEGURO       |CNF            |CONFINS             |95.16129032258065|
|FLN           |FLORIANÓPOLIS      |POA            |PORTO ALEGRE        |95.16129032258065|
|GRU           |GUARULHOS          |CGB            |VÁRZEA GRANDE       |95.07989380885594|
|GRU           |GUARULHOS          |POA            |PORTO ALEGRE        |94.87980020550884|
|SDU           |RIO DE JANEIRO     |FLN            |FLORIANÓPOLIS       |94.6732470577365|
|CNF           |CONFINS            |AJU            |ARACAJU             |94.6236559139785|
|BSB           |BRASÍLIA           |POA            |PORTO ALEGRE        |94.55645161290322|
|REC           |RECIFE             |BSB            |BRASÍLIA            |94.54638720066488|
|GRU           |GUARULHOS          |REC            |RECIFE              |94.5159362453791|
|BSB           |BRASÍLIA           |NAT            |SÃO GONÇALO DO AMARANTE|94.44444444444443|
|GRU           |GUARULHOS          |NVT            |NAVEGANTES          |94.20335689207899|
|REC           |RECIFE             |CGH            |SÃO PAULO           |94.14230007241093|
|BVB           |BOA VISTA          |BSB            |BRASÍLIA            |93.9784946236559|
|MCP           |MACAPÁ             |BSB            |BRASÍLIA            |93.9784946236559|
|JPA           |SANTA RITA         |GRU            |GUARULHOS           |93.9065893320621|
|SSA           |SALVADOR           |CGH            |SÃO PAULO           |93.88371796506439|
|POA           |PORTO ALEGRE       |BSB            |BRASÍLIA            |93.78227325192883|

# Entender a correlação entre horários de voos e soma dos indicadores de RPK e ASK

Para fazer a correção entre a faixa de horários e os indicadores de RPK e ASK foi necessário encontrar qual o que possui um maior números de voos da GOL, em seguida, encontrar qual dia da semana há o maior números de voos.

**TOP Trechos com maiores números de voos da GOL Linhas Aéreas.**

|nm_empresa|sg_icao_origem|sg_icao_destino|nr_voo            |
|----------|--------------|---------------|------------------|
|GOL LINHAS AÉREAS S.A. (EX- VRG LINHAS AÉREAS S.A.)|SBRJ          |SBSP           |168               |
|GOL LINHAS AÉREAS S.A. (EX- VRG LINHAS AÉREAS S.A.)|SBSP          |SBRJ           |166               |
|GOL LINHAS AÉREAS S.A. (EX- VRG LINHAS AÉREAS S.A.)|SBGR          |SBBR           |102               |
|GOL LINHAS AÉREAS S.A. (EX- VRG LINHAS AÉREAS S.A.)|SBBR          |SBGR           |100               |
|GOL LINHAS AÉREAS S.A. (EX- VRG LINHAS AÉREAS S.A.)|SBCF          |SBGR           |98                |
|GOL LINHAS AÉREAS S.A. (EX- VRG LINHAS AÉREAS S.A.)|SBRF          |SBGR           |98                |
|GOL LINHAS AÉREAS S.A. (EX- VRG LINHAS AÉREAS S.A.)|SBGR          |SBRF           |97                |
|GOL LINHAS AÉREAS S.A. (EX- VRG LINHAS AÉREAS S.A.)|SBGR          |SBCF           |97                |

Como Santos Dumont possui horário determinado para operar, removi ele da análise e então, passei a analisar somente o trecho Guarulhos - Brasília.  Em seguida, foi necessário analisar a distribuição semanal dos voos da GOL no trecho GRU-BSB.

|Dia da Semana|Quantidade de voos|
|---------|------|
|Domingo  |16    |
|Quarta-feira|14    |
|Quinta-feira|15    |
|Segunda-feira|18    |
|Sexta-feira|14    |
|Sábado   |11    |
|Terça-feira|14    |

Segunda-Feira possui 18 voos neste trecho, enquanto Domingo possui 16, então, iremos analisara distribuição dos horários e quantidade de voos apenas na Segunda-Feira.
|hr_partida_real|Quantidade de voos|
|---------------|------|
|6              |2     |
|8              |5     |
|13             |2     |
|14             |3     |
|17             |2     |
|22             |4     |

Em seguida, iremos mostrar a soma de RPKs e ASKs realizados nessa data.
|hr_partida_real|Soma de RPK|Soma de ASK|
|---------------|------|------|
|06             |201780|277020|
|08             |639540|795150|
|13             |269325|318060|
|14             |441180|477090|
|17             |269325|318060|
|22             |548910|595935|

O teste de normalidade Shapiro-Will indicará qual o melhor método de correlação iremos usar, vamos analisar:

**Teste de normalidade usando Shapiro-Wil para média de RPK:** 
ShapiroResult(statistic=0.9105069637298584, pvalue=0.4397401213645935) 

Teste de normalidade usando Shapiro-Wil para média de ASK: 
**ShapiroResult(statistic=0.8827252984046936, pvalue=0.28180739283561707**

Como  o valor P < 0.5, usaremos o método Spearman. Veja a tabela de correlação:
|indicador|hr_partida_real|nr_rpk|nr_ask|
|---------|---------------|------|------|
|hr_partida_real|1.0            |0.20570320484322127|0.04570745173382161|
|nr_rpk   |0.20570320484322127|1.0   |0.9819932287820209|
|nr_ask   |0.04570745173382161|0.9819932287820209|1.0   |

Portanto, a correção entre o horário de partida e a soma do número de RPK é relativamente fraca segundo Vieira (2011), 
Valores expressos em p-valor e r-valor. Análise de correlação de Speraman. Para a classificação do R, ultilizou-se a referência de 1Vieira, (2011). Teste de normalidade Shapiro-wilk teste p>0,05.

**Em sequência, iremos fazer a **correlação** para a Média de RPKs e ASKs.**

|medida|hr_partida_real|nr_rpk|nr_ask|
|------|---------------|------|------|
|hr_partida_real|1.0            |0.7826908981308054|0.16903085094570333|
|nr_rpk|0.7826908981308054|1.0   |0.3429971702850177|
|nr_ask|0.16903085094570333|0.3429971702850177|1.0   |


Portanto, podemos dizer que a há uma correlação forte entre o horário de voos e a média de RPKs durante os voos da Segunda-Feira, sendo que quanto mais tarde for, maior podemos ter de assentos ocupados.

# Thanks for the opportunity! ✈🧡
_Uma vez que você tenha experimentado voar, você andará pela terra com seus olhos voltados para céu, pois lá você esteve e para lá você desejará voltar._

