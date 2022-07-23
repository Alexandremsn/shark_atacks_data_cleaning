# shark_atacks_data_cleaning
limpeza de uma base de dados para realizar inferências sobre a existência ou não de correlação entre ataques de tubarão e fase lunar

Foram necessárias as bibliotecas abaixo para esta análise:

<img src="images/biblioteca.png" alt="libs"/>

Ao importar a base verificamos que existiam colunas com informação repetidas e colunas sem informação:

<img src="images/head inicial.png">


Realizando a checagem de tipo e valores nulos verificamos que o arquivo era muito irregular com muitas linhas sem informação:

<img src="images/inconsistencias iniciais.png">

Já convertemos a coluna Date para tipo data pois vai ser usada em equações que demandam este tipo.
Também verificamos o final do arquivo e verificamos que boa partes dos valores vazios vinham da parte final do arquivo:

<img src="images/tail inicial.png">

Realizamos a exclusão do final do arquivo que contimham valores vazios e das linhas repetidas.
As linhas Unamed eram meras informaçoes de até aonde algum usuário anterior havia analisado, então também foram excluidas.
foi feita a checagem de outra coluna que iamos usar a 'Fatal (Y/N)' , foram verficadas as inconsistêcnias e corrigidas:

<img src="images/arrumando dados fatal.png">


Por fim ao checar novamente os dados podemos ver que as linhas estão mais consistentes e uniformes:

<img src="images/dados consistente.png">

Agora era a hora de começar a análise para usar os dados da fase da lua recori a biblioteca de dados astronômicos EPHEM
e o algorítimo abaixo foi desenvolvido modificando um algorítimo que gerava uma listagem de todas as datas iniciais das 4 fases principais e 4 intermediárias para o ano informado.
Assim modificamos para receber uma data e devolver a fase principal da lua correspondente a data informada.

<img src="images/def get lunar phase.png">

Assim rodamos unando um map na coluna Date e criamos a coluna Lunar Phase com as fases da lua da data correspondente.
e geramos o percentual de cada fase, haviam diferenças e pareciam promissores os dados para indicar alguma correlação: 

<img src="images/percentual.png">

Geramos dois histogramas para verificar visualmente a correlação da variáveis.

<img src="images/primeirohistograma.png">

<img src="images/segundohistograma.png">

não possuiem diferenças substanciais quanto ao seu formato, assim visualmente não parece ter correlação as variáveis.


Criamos um segundo dataframe apenas com os dados esseciais a análise, e geramos este gáfico de correlação
e no final verificamos uma correlação muito fraca quase inexistente.
assim podemos concluir que as fases da lua não tem relação com a fatalidade e com a quantidade de ataques.

<img src="images/sem correlacao.png">
