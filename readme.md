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

### 1- Faça um ranking para o número total de PAX por dia da semana.

The file explorer is accessible using the button in left corner of the navigation bar. You can create a new file by clicking the **New file** button in the file explorer. You can also create folders by clicking the **New folder** button.

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


# To be continued...