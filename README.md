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

# Fazendo a limpeza

Iremos começar a manipular os dados, ou seja, tirar o que não for necessário, agrupar, atribuir novas informações, etc. Claro, os dados precisam fazer sentido e estar preparados para o contexto da análise a ser realizada. Por isso, a “limpeza” dos dados é uma parte essencial em um projeto de ciência de dados.

Iniciaremos a limpeza, atribuindo mais contexto aos seus dados para depois aprofundar-se nas análises.

