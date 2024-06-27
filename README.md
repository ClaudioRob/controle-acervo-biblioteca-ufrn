# Controle do acervo de livros da biblioteca da Univeersidade Federal do Rio Grande do Norte(UFRN)  Por Francisco Froz

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

Plote um gráfico para cada tipo de usuário.
Tenha um boxplots para cada ano e analise o que ocorreu.
