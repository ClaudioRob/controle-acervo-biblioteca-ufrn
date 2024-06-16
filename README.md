# Projeto da Alura Por Francisco Froz

Esste projeto faz parte da Jornada #7DaysOfCode onde iremos explorar os dados de empréstimos dos acervos do sistema de bibliotecas da UFRN. Um dos objetivos de uma biblioteca é garantir que os materiais informacionais estejam sendo utilizados. Os empréstimos realizados podem ser um indicador, mesmo que de forma básica (pois você não consegue garantir que haja uma leitura ou utilização real).

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

# Chegamos ao terceiro do #7DaysOfCode de Python Pandas!

Chegou a hora de começar a explorar os seus dados!

Um dos objetivos de uma biblioteca é promover o uso da informação.

Por isso, o empréstimo dos materiais em uma biblioteca é uma das formas de se indicar o uso daquela informação. Entender a quantidade e quando se emprestaram os livros é uma das primeiras formas de fazer uma análise desse tipo. 

A diretoria da biblioteca gostaria de entender se a quantidade de empréstimos está diminuindo, aumentando ou permanecendo igual ao decorrer dos últimos anos. Para isso, verifique qual é a quantidade total de exemplares emprestados por cada ano e plote um gráfico de linhas. Depois, faça uma análise em relação à visualização gerada.

Atente-se para a quantidade de exemplares emprestados, e não de empréstimos realizados.

A diretoria também gostaria de gerenciar melhor os recursos humanos da biblioteca de acordo com a demanda de trabalho existente.
