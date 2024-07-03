# Controle do acervo de livros da biblioteca da Universidade Federal do Rio Grande do Norte(UFRN)
* Esse projeto foi criado com a finalidade de estudo em Pyrhon & Pandas. O código original, desenvolvido por Francisco Froz (Alura), encontra-se nesse [Repositório]( https://github.com/FranciscoFoz/7_Days_of_Code_Alura-Python-Pandas/tree/main).

Esste projeto faz parte da Jornada #7DaysOfCodeWithPythonPandas onde iremos explorar os dados de empréstimos dos acervos do sistema de bibliotecas da UFRN. Um dos objetivos de uma biblioteca é garantir que os materiais informacionais estejam sendo utilizados. Os empréstimos realizados podem ser um indicador, mesmo que de forma básica (pois você não consegue garantir que haja uma leitura ou utilização real).

Por este motivo, entender a quantidade de empréstimos se torna importante.

Questões de diferentes perspectivas podem surgir como:

A quantidade de empréstimos está aumentando ou diminuindo ao decorrer dos últimos anos?
Em quais bibliotecas do sistema estão a maior quantidade de empréstimos?
Quais são os temas mais emprestados? E os menos?

Com estas e outras informações será possível entender o cenário e apresentá-lo à diretoria das bibliotecas, para que possam tomar melhores decisões na melhoria da infraestrutura, dos recursos e processos da unidade de informação.

Trabalharemos com dados apenas dos últimos 10 anos.

Temos, então as tabelas: 1.Empréstimos dos acervos das bibliotecas de UFRN e 2.Exemplares do acervo

O primeiro passo é unificar em um único Dataframe todos os dados pertinentes para a análise.

Iremos mesclar os dados da tabela de empréstimos com os dados do acervo, para que possamos entender, por exemplo, de qual biblioteca era o material emprestado ou a qual tema ele se referia. 
Elas se relacionam pela coluna de código de barras de cada material. Devemos ainda fazer a limpeza dos dados nulos ou duplicados.

# Importando os Dados

Optamos por importar os dados diretamente do Git Hub passando o endereço do link “Raw” como origem.

#### URL base do repositório no GitHub: 
"https://api.github.com/repos/FranciscoFoz/7_Days_of_Code_Alura-Python-Pandas/contents/Dia_1-Importando_dados/Datasets/dados_emprestimos"

# As primeiras manipulações

Iremos começar a manipular os dados, ou seja, tirar o que não for necessário, agrupar, atribuir novas informações, etc. Claro, os dados precisam fazer sentido e estar preparados para o contexto da análise a ser realizada. Por isso, a “limpeza” dos dados é uma parte essencial em um projeto de ciência de dados.

Iniciaremos a limpeza, atribuindo mais contexto aos seus dados para depois aprofundar-se nas análises.

Entender o negócio é fundamental para que não se tenha análises sem explicações ou mesmo sem o foco necessário para a resolução dos problemas.

Você deve ter visto que tem uma coluna identificada como “localização” e diversos números nela, mas você sabe o que significam estes números?

"Os itens do acervo em uma biblioteca são organizados por um sistema de classificação de acordo com o respectivo tema. Existem diversos sistemas, mas este conjunto está de acordo com a CDU - Classificação Decimal Universal. Esta classificação é decimal, pois varia de acordo com a classe de cada assunto:

- 000 a 099: Generalidades. Ciência e conhecimento.
- 100 a 199: Filosofia e psicologia.
- 200 a 299: Religião.
- 300 a 399: Ciências sociais.
- 400 a 499: Classe vaga. Provisoriamente não ocupada.
- 500 a 599: Matemática e ciências naturais.
- 600 a 699: Ciências aplicadas.
- 700 a 799: Belas artes.
- 800 a 899: Linguagem. Língua. Linguística.
- 900 a 999: Geografia. Biografia. História."

# Explorando os dados

Chegou a hora de começar a explorar os seus dados!

Um dos objetivos de uma biblioteca é promover o uso da informação.

Por isso, o empréstimo dos materiais em uma biblioteca é uma das formas de se indicar o uso daquela informação. Entender a quantidade e quando se emprestaram os livros é uma das primeiras formas de fazer uma análise desse tipo. 

A diretoria da biblioteca gostaria de entender se a quantidade de empréstimos está diminuindo, aumentando ou permanecendo igual ao decorrer dos últimos anos. Para isso, verifique qual é a quantidade total de exemplares emprestados por cada ano e plote um gráfico de linhas. Depois, faça uma análise em relação à visualização gerada.

Atente-se para a quantidade de exemplares emprestados, e não de empréstimos realizados.

A diretoria também gostaria de gerenciar melhor os recursos humanos da biblioteca de acordo com a demanda de trabalho existente. Há uma suspeita interna de que os meses com maior número de exemplares emprestados sejam março e setembro, mas não foi realizada uma análise real sobre isso.

Portanto, criaremos uma tabela com a quantidade total de exemplares emprestados por mês e descobrir quais meses são os que possuem a maior quantidade de empréstimos realizados. Plote um gráfico de linhas.

| mes_emprestimo  | total_emprestimos |
| ------------- | ------------- |
| Janeiro	| 67514 	|
| Fevereiro     | 210200  	|
| Março		| 252185  	|
| Abril         | 208725  	|
| Maio          | 202530  	|
| Junho         | 138123  	|	|
| Julho         | 123790  	|
| Agosto        | 232793 	|
| Setembro      | 208234  	|
| Outubro       | 188410  	|
| Novembro      | 164222 	|
| Dezembro      | 75796 	|

Além do gerenciamento anual das atividades, a diretoria também necessita que seja planejada uma programação diária das atividades. Por este motivo, verifique quais foram os horários com maior quantidade de empréstimos ao longo de um dia inteiro.

Plote um gráfico de barras e analise quais seriam os melhores horários para alocar as demais atividades que não sejam de atendimento ao usuário.

![image](https://github.com/ClaudioRob/controle-acervo-biblioteca-ufrn/assets/44467803/754d6ca0-0da9-4f17-9cac-2b5f21fb7183)

# Iniciando as análises

Iremos questionar ainda mais os nossos dados para extrair ainda mais informações deles. O objetivo será entender a quantidade de empréstimos a partir das variáveis categóricas. Vamos explorar algumas das variáveis categóricas das quais precisaremos extrair mais informações. Elas são:

* Tipo de vínculo
* Coleção
* Biblioteca
* Classificação geral da CDU

Ao se analisar uma nova variável, é bem interessante verificar cada uma listando quais são os valores únicos dentro delas. Entender quais os temas mais procurados pelos usuários é fundamental para o desenvolvimento de novos planos de marketing do acervo. Para que possam não apenas fortalecer o que está sendo utilizado, mas também promover o que não está.

Gere uma tabela de frequência e com o percentual para cada variável. Como é um trabalho repetitivo, crie uma função que gere a tabela com os valores.

|tipo\_vinculo\_usuario|quantidade|percentual|
|---|---|---|
|ALUNO DE GRADUAÇÃO|1612324|77\.8|
|ALUNO DE PÓS-GRADUAÇÃO|302541|14\.6|
|DOCENTE|70981|3\.4|
|SERVIDOR TÉCNICO-ADMINISTRATIVO|32184|1\.6|
|ALUNO MÉDIO/TÉCNICO|28029|1\.4|
|DOCENTE EXTERNO|23949|1\.2|
|USUÁRIO EXTERNO|2509|0\.1|
|OUTROS|5|0\.0|

# Tipos de visualizações - Conhecendo o Boxplot

O Boxplot é uma das visualizações mais poderosas que existe, pois ele permite que você visualize medidas estatísticas como a mediana, os quartis, os valores mínimos e máximos e os valores atípicos outliers. O gráfico possui uma estrutura formada por uma caixa retangular, uma linha cortando essa caixa e as hastes (ou bigodes) ligadas a caixa.

![image](https://github.com/ClaudioRob/controle-acervo-biblioteca-ufrn/assets/44467803/a4fc370b-096a-4413-bca2-2d0d585088b4)

Os quartis são representados pelos limites da caixa, do quartil inferior (Q1) ao quartil superior (Q3). A mediana (é o Q2) é representada pela linha. Os valores mínimos e máximos são as extremidades das hastes e os outliers são todos os pontos além destes limites.

Desenvolver estratégias para o uso da informação é uma tarefa constante, devido às diversas mudanças que ocorrem o tempo todo: os usuários estão evoluindo seus conhecimentos, novos alunos chegam, alunos que se formam saem e as informações estão sempre em movimento e transformação.

Por este motivo, é importante realizar avaliações constantes do uso da biblioteca e entender em quais cenários (tipos de usuários, estratégias de marketing, atualização de acervo, cenário sócio-político interno e externo) é melhor manter a estratégia atual ou mudá-la.

Você vai fazer dois recortes em seus dados para entender como eles se distribuíram ao decorrer desses anos e, desta forma, possa trazer inferências para levar à diretoria da biblioteca, a fim de que eles possam tomar decisões para o ano atual.

Para isso, você vai avaliar dentre os alunos de graduação e pós graduação a distribuição de empréstimos mensais por ano realizados entre 2010 e 2020 da coleção que tiver a maior frequência de empréstimos.

Distribuição de empréstimos mensais por ano realizados entre 2010 e 2020 dos alunos de graduação
![image](https://github.com/ClaudioRob/controle-acervo-biblioteca-ufrn/assets/44467803/ea5f5490-4d2e-442f-853a-a935155f774e)

É importante ressaltar que esse recorte, reflete grande parte da estrutura geral do conjunto de dados, pois são os tipos de usuários com maior frequência (alunos de graduação) e da coleção mais utilizada por eles (acervo circulante). Com o boxplot é possível observar a oscilação da quantidade de empréstimos realizados mensalmente durante cada ano. 

Além da análise geral realizada (declínio a partir de 2013, forte baixa em 2019), chama atenção os anos de 2014 e 2017. Mas se diferenciam principalmente porque em 2014 houve um declínio e em 2017 houve um aumento, em relação aos anos anteriores. Seria interessante entender com a direção das bibliotecas o que ocorreu nessas datas para que pudéssemos ter um contexto melhor da realidade do negócio.

Distribuição de empréstimos mensais por ano realizados entre 2010 e 2020 dos alunos de pós-graduação
![image](https://github.com/ClaudioRob/controle-acervo-biblioteca-ufrn/assets/44467803/b1315c40-2bdb-4c2a-a267-52d2923e3592)

Já os alunos de pós graduação tiveram um aspecto diferente em relação ao declínio a partir de 2013. A linha mediana foi diminuindo devagar até 2018. Entretanto valores máximos foram superiores, apenas caindo de fato em 2019. Nos dois gráficos podemos observar um grande aumento entre 2010 e 2013, o que nos leva a pensar em quais procedimentos estavam sendo realizados neste período para que houvesse esse crescimento.

Nos dois recortes visualizamos que a partir de 2018 tivemos um forte declínio e é um alerta para que a direção possa entender o que está ocorrendo.

# Vamos enriquecer nossas análises

As instituições de ensino superior (IES) têm a necessidade de passar por avaliações do Ministério da Educação (MEC) para que possam ofertar e continuar ofertando cursos de graduação e pós-graduação.

A biblioteca universitária faz parte de um dos indicadores da avaliação dos cursos, em principalmente três aspectos: acervo, infraestrutura e serviços.

Dentre os serviços, são avaliados se existem recursos de bases referenciais para pesquisa, se há treinamentos para os usuários utilizarem os materiais, e a presença de indicadores sobre o uso dos materiais do acervo (empréstimos, consultas) dentre outros tópicos.

Iremos calcular a quantidade de empréstimos realizados entre 2015 e 2020 por cada curso de graduação que passará pela avaliação.

Os cursos serão:

* Biblioteconomia
* Ciências sociais
* Comunicação social
* Direito
* Filosofia
* Pedagogia

A universidade forneceu os dados dos usuários, mas uma parte deles está em planilhas de [Excel]('https://empresas.alura.com.br/e3t/Ctc/I8+113/d2z6gD04/MWbsSXwSfFwW484Xhg4S3sq5W7lBRbf5gsB2WN56dXgK5kvg0W5BWr2F6lZ3n0W4dHGrH8Js6srW20GGff4-YRM-W74fHT01LQGY9W2Yd-LJ2p5QQDVG15Py93yyD4W60wq3T3vlDfFW3xPldT8Jk_CvW1tK9pq5MJj0WW8BrfGy8ZhxW-V_T15x5B4tdPW13lNd33VXszcW4Dtt5L6b8qlzVnvJL082Q3p5N3hbcyVx9wVfW6sxN1D7QvJJ0W7P_Hhb3f7T0xW71GKBs6jD_4ZF74QPfXmzB0N9b6nkMG7TCgW5-8Fp18hlWmHW7Wvbd82qyP-9W329sJS1sBg7lW6NbVvQ59DsJBN3b7hwd24GnQW4M_1f617v9jYW7RngHv1c-dGTW2s7lfH5Bwf5cW67KzNh2HydHvN2MQntZ-TwgTN3sS5x9CrDB7W8kp5_66LqxsqW5TxPRW4sq79QW5_J0Zl3JZbLCW851qT54lvhVRf8CSzgx04), a outra parte veio através de uma [API](https://empresas.alura.com.br/e3t/Ctc/I8+113/d2z6gD04/MWbsSXwSfFwW484Xhg4S3sq5W7lBRbf5gsB2WN56dXh05kvg0W69t95C6lZ3mBW7tvtvG3jhtR7W7yRMDX87Tx7PW1jmrnw4HdM_9W2Pbxhv3nWlr9W3rRwTw26TT2XVKZh2n365h54W8WlCrm2HzsWgW2TmncV9h24MQN8kncW3T4QNnVw165D9dPsRXW34tB118975SwW6JxSXX3g7vJnW7BHQK95CG_bbW2k2T4Y843q6lVJbytg22JqSXW7Xzg1p30zHttW9dMByv7JYNhNW1Lq83-9gxDv3N90HhMBzQhySW16yvcJ21J0D6W5wQTB86Q1TlSW1bmDF-5QtPc6W4YXHZF942LYbW3yN27x5y52_NW49XLbT5wv_V2W8nnrpx7jN-VtW2xyTBp1gN5YWN6t2NsJcZDpWW90YpJ75c__78W5l38c45Tt_qZW5XdRf6651XX7W7P8T-75tB6BmN2lcphH-s90cW7lcBWf883bNQW62zCx671BzLtW6rKQHK2Jcypgf2ZXNRR04) do sistema em formato JSON.
[exemplo](https://exemplo.com/)

Extraia os dados destes arquivos, agrupe-os em apenas um só, e verifique depois a quantidade de empréstimos.

Gere uma tabela com as seguintes características:

* Índice: Cursos
* Colunas: Ano
* Valores: Quantidade de empréstimos
* Total: Acrescente uma linha e uma coluna de total a tabela

|CURSO|2015|2016|2017|2018|2019|2020|TOTAL|
|---|---|---|---|---|---|---|---|
|BIBLIOTECONOMIA|7784|7044|7307|6378|5889|900|35302|
|CIÊNCIAS SOCIAIS|7489|6978|6918|6181|5788|825|34179|
|COMUNICAÇÃO SOCIAL|7147|7973|8253|6953|5885|796|37007|
|DIREITO|7665|7363|7885|7027|5861|905|36706|
|FILOSOFIA|6950|7576|7389|6296|5572|832|34615|
|PEDAGOGIA|7189|7153|7434|6518|5869|866|35029|
|TOTAL|44224|44087|45186|39353|34864|5124|212838|

# Chegamos ao final do Projeto

A diretoria da biblioteca está montando um plano de ação de marketing focado nos alunos da pós-graduação. Para isso, precisará analisar a diferença percentual de empréstimos realizados nos últimos anos (2017, 2018, 2019) para cada curso. Devido à pandemia do COVID-19, ela não poderá utilizar os dados de 2020 e 2021. Entretanto, seu colega de equipe já realizou uma análise de previsão de empréstimos de 2022 e a disponibilizou para que você também possa realizar o comparativo entre 2019-2022.

Você precisará criar uma tabela com as diferenças percentuais de empréstimos entre 2017-2018, 2018-2019, 2019-2022.

