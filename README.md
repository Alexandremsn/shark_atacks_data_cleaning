<div align="center">
<img src="images/logo.jpg">

# shark_atacks_data_cleaning
<div align="left">
Limpeza de uma base de dados para realizar inferências sobre a existência ou não de correlação entre ataques de tubarão e fase lunar.

## Tecnologia

O software  usado neste projeto foi:

* Python version  3.9.5

## Serviços Usados

* Github


## Bibliotecas Python

* Re
* Pandas
* Numpy
* Datetime
* Ephem
* Matplotlib
* Dython


## Como foi feito

Será descrito abaixo atravé de textos e imagens.



Ao importar a base verificamos que existiam colunas com informação repetidas e colunas sem informação:

<img src="images/head inicial.png">


Realizando a checagem de tipo e valores nulos verificamos que o arquivo era muito irregular com muitas linhas sem informação:

<img src="images/inconsistencias iniciais.png">

Já convertemos a coluna Date para tipo data pois vai ser usada em equações que demandam este tipo.
Também verificamos o final do arquivo e verificamos que boa partes dos valores vazios vinham da parte final do arquivo:

<img src="images/tail inicial.png">

Realizamos a exclusão do final do arquivo que continham valores vazios e das linhas repetidas.
As linhas Unamed eram meras informações de até aonde algum usuário anterior havia analisado, então também foram excluídas.
foi feita a checagem de outra coluna que vamos usar a 'Fatal (Y/N)' , foram verificadas as inconsistências e corrigindo-as:

<img src="images/arrumando dados fatal.png">


Por fim ao checar novamente os dados podemos ver que as linhas estão mais consistentes e uniformes:

<img src="images/dados consistente.png">

Agora era a hora de começar a análise para usar os dados da fase da lua recorri a biblioteca de dados astronômicos EPHEM
e o algorítimo abaixo foi desenvolvido modificando um algorítimo que gerava uma listagem de todas as datas iniciais das 4 fases principais e 4 intermediárias para o ano informado.
Assim modificamos para receber uma data e devolver a fase principal da lua correspondente a data informada.

<img src="images/def get lunar phase.png">

Assim rodamos usando o método map na coluna Date e criamos a coluna Lunar Phase com as fases da lua da data correspondente.
e geramos o percentual de cada fase, haviam diferenças e pareciam promissores os dados para indicar alguma correlação: 

<img src="images/percentual.png">

Geramos dois histogramas para verificar visualmente a correlação da variáveis.

<img src="images/faselunar fatal nao (1).png" alt="drawing" width="500">

<img src="images/faselunar fatal sim (1).png" alt="drawing" width="500">

não possuem diferenças substanciais quanto ao seu formato, assim visualmente não parece ter correlação as variáveis.


Criamos um segundo dataframe apenas com os dados essenciais a análise, e geramos este gráfico de correlação e no final verificamos uma correlação muito fraca quase inexistente.
assim podemos concluir que as fases da lua não tem relação com a fatalidade e com a quantidade de ataques.


## Recursos Usados

  - Importação de Database
  - Limpeza de dados
  - Desenvolvimento de Aplicação
  - Plotagem de Gáficos
  - Análise de dados
  - Criação de arquivo .csv
  

## Links

  - Repositório: https://github.com/Alexandremsn/shark_atacks_data_cleaning
  - Se for econtrado um bug, favor entrar em contato alexandremsneto1986@gmail.com


## Versioning

1.0.0.0


## Autor

* **Alexandre Machado da Silva Neto**: @alexandremsn (https://github.com/alexandremsn)
