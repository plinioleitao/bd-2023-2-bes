## [Tópico 29] - Tempo para convergir ...
###### *by Prof. Plinio Sa Leitao-Junior (INF/UFG)*

```diff
+ Vários foram os conceitos estudados até o momento, conforme a nossa ementa.
- Tenhamos, em tal caso, uma oportunidade para 'exercícios de revisão'.
@@ Enfim, um breve momento para convergir nossas percepções. @@
```

<hr style="border:2px solid blue">

### Exercício 01

Considere o esquema de banco de dados sobre uma biblioteca descrito a seguir. Os atributos em negrito referem-se à chave primária de cada relação. 

A relação ENDERECO (**Identificador**, Logradouro, CEP, Cidade, UF) representa os endereços de pessoas e editoras. 

A relação PESSOA (**CPF**, Nome, Sexo, DataNascimento, Identificador) refere-se às pessoas que solicitam empréstimos de livros: o atributo Identificador é uma chave estrangeira que referencia ENDERECO; duas ou mais pessoas podem compartilhar um mesmo endereço; o endereço de uma pessoa não é obrigatório no banco de dados. 

A relação EDITORA (**Codigo**, Nome, Identificador) relaciona-se às editoras de livros: o atributo Identificador é uma chave estrangeira que referencia ENDERECO; duas ou mais editoras não podem compartilhar um mesmo endereço; o endereço de qualquer editora é obrigatório no banco de dados. 

A relação LIVRO (**ISBN**, Titulo, AnoDeEdicao, Codigo) refere-se aos livros que podem ser emprestados: o atributo Codigo é uma chave estrangeira que referencia à relação EDITORA; todos os atributos devem ter algum valor em cada tupla da relação; dois ou mais livros podem compartilhar uma mesma editora. 

A relação AUTOR (**Numero**, Nome) denota os autores de livros. 

A relação AUTORIA (**ISBN, Numero**) associa autores a livros: ISBN e Numero são chaves estrangeiras que referenciam LIVRO e AUTOR, respectivamente; um livro pode ter vários autores, e um autor pode estar associado a vários livros. 

A relação EMPRESTIMO (**CPF, ISBN, DataInicio**, DataFinalPrevista, DataFinalReal) é pertinente aos empréstimos de livros: CPF é uma chave estrangeira que referencia PESSOA; ISBN é uma chave estrangeira que referencia LIVRO; os atributos DataInicio e DataFinalPrevista referem-se à data de retirada do livro e à data prevista de devolução, respectivamente, ambos com valores obrigatórios no banco de dados; o atributo DataFinalReal denota a data efetiva de devolução do livro, e somente possuirá algum valor quando o livro em questão tiver sido devolvido pela pessoa; uma pessoa pode tomar emprestado vários livros e um livro pode ser emprestado várias vezes. 

1. De acordo com as restrições de integridade no banco de dados,<br>
(a) uma editora pode ter mais de um endereço.<br>
(b) uma pessoa pode ter mais de um endereço.<br>
(c) um livro pode ser emprestado várias vezes para uma mesma pessoa.<br> 
(d) um livro pode ser editado por várias editoras e pode ter vários autores distintos.<br>
(e) Nenhum das alternativas anteriores.<br>

2. Valores nulos são permitidos para alguns atributos do banco de dados. Um atributo que pode ter valor nulo é:<br>
(a) Codigo em LIVRO.<br>
(b) Identificador em PESSOA.<br>
(c) Identificador em EDITORA.<br>
(d) DataFinalPrevista em EMPRESTIMO.<br>
(e) Nenhum das alternativas anteriores.<br>

3. Valores de alguns atributos devem ser únicos entre as tuplas de uma relação, tal como o atributo<br>
(a) Numero em AUTOR.<br>
(b) ISBN em AUTORIA.<br>
(c) ISBN em EMPRESTIMO.<br>
(d) Numero em AUTORIA.<br>
(e) Nenhum das alternativas anteriores.<br>

4. Uma informação obtida a partir do banco de dados é:<br>
(a) a idade de cada autor.<br>
(b) os livros comprados no último mês.<br>
(c) a quantidade de dias de atraso dos empréstimos devolvidos com atraso.<br>
(d) o nome das editoras que mudaram de endereço mais de uma vez no último ano.<br>
(e) Nenhum das alternativas anteriores.<br>

<hr style="border:2px solid blue">

### Exercício 02

Escreva em SQL as operações (1), (2) e (3).

|(1)|
|-|
|π <sub>Pnome, **F.Sexo**, Nome_dependente, **D.Sexo**</sub><br>&nbsp;&nbsp;&nbsp;&nbsp;(**ρ <sub>F</sub>** (FUNCIONARIO) ⨝ <sub>Cpf = Fcpf</sub> **ρ <sub>D</sub>** (DEPENDENTE))|

|(2)|
|-|
|D(Cpf, Nome_dependente, Sexo_dependente) ←<br>&nbsp;&nbsp;&nbsp;&nbsp;π <sub>Fcpf, Nome_dependente, Sexo</sub> (DEPENDENTE)<br>RESULT ← π <sub>Pnome, Sexo, Nome_dependente, Sexo_dependente</sub> (FUNCIONARIO * D)|

|(3)|
|-|
|FUNC(**Cpf**, Pnome_func, Unome_func) ← <br>&nbsp;&nbsp;&nbsp;&nbsp;π <sub>**Cpf_supervisor**, Pnome, Unome</sub> (FUNCIONARIO)<br>SUPER ← π <sub>Cpf, Pnome, Unome</sub> (FUNCIONARIO)<br>RESULT ← π <sub>Pnome_func, Unome_func, Pnome, Unome (FUNC * SUPER)|

<hr style="border:2px solid blue">

### Exercício 03

Sobre os Requisitos de Dados para o BD e-cred no [Tópico 04b](./topico-04b.md), elabore um trecho do Diagrama Entidade Relacionamento (DER), conforme descrito abaixo. Faça um rascunho à mão, ou use a Ferramenta EERCASE.

|Requisitos de Dados|
|-|
|**INDICADOR DE CRÉDITO**<br>Um <ins>indicador de crédito</ins> é um  <ins>componente para a tomada de decisão </ins> sobre a concessão de crédito.<br>&#x267B; Vários são os indicadores de crédito disponibilizados pelo **e-cred**, tais como:<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ... _qualidade de cadastro_,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ... _carteira elegível para cobrança_,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ... dentre outros &#8252;<br>Se um associado solicitar:<br>&#x267B; <ins>Um indicador de crédito é calculado</ins> com relação a um cliente, para produzir um <ins>número decimal</ins>:<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ... qual o valor para o indicador _qualidade de cadastro_ daquela pessoa?<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ... qual o valor para o indicador _carteira elegível para cobrança_ daquela pessoa?<br><br>**CONTRATAÇÃO DE INDICADOR DE CRÉDITO**<br>Se o associado <ins>contratar o direito de uso</ins> de um indicador de crédito:<br>&#x267B; O associado poderá fornecer [e usar] a sua <ins>fórmula específica</ins> de cálculo para esse indicador,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ... ou poderá utilizar a <ins>fórmula genérica</ins> (fórmula _default_) do indicador.<br>&#x267B; O <ins>cálculo do indicador de crédito</ins> referente a um cliente poderá ser solicitado pelo associado,<br>a qualquer tempo, para produzir um número decimal desse indicador em relação ao cliente.<br>&#x267B; O associado irá <ins>pagar um valor</ins> por cada cálculo solicitado de indicador.<br>&#x267B; Se um associado contratar um indicador, então há:<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ... um valor a ser pago por solicitação; e<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ... uma quantidade mínima mensal de solicitações – uma franquia.|

<hr style="border:2px solid blue">

### Exercício 04

Foi solicitada a implementação de uma nova cláusula (função) para a SQL, denominada **UNIQUE**, que é avaliada como **True** quando a subconsulta não retornar _tuplas_ repetidas. Como esta cláusula ainda não foi implementada pelo SGBD, você poderia escrever uma **Consulta SQL Alternativa** para o exemplo abaixo?<br>(para melhor entendimento, veja a _Consulta SQL Alternativa_ do exemplo com a cláusula EXISTS): 

|Consulta SQL Original|Consulta SQL Alternativa|Significado|
|-|-|-|
|SELECT Pnome, Unome<br>FROM FUNCIONARIO AS F<br>WHERE **EXISTS** (<br>&nbsp;&nbsp;SELECT Nome_dependente<br>&nbsp;&nbsp;FROM DEPENDENTE AS D<br>&nbsp;&nbsp;WHERE F.Cpf = D.Fcpf )|SELECT Pnome, Unome<br>FROM FUNCIONARIO AS F<br>WHERE 0 < (<br>&nbsp;&nbsp;SELECT COUNT(\*)<br>&nbsp;&nbsp;FROM DEPENDENTE AS D<br>&nbsp;&nbsp;WHERE F.Cpf = D.Fcpf )|Qual o primeiro e último nomes dos funcionários<br>que possuem algum dependente?|
|SELECT Pnome, Unome<br>FROM FUNCIONARIO AS F<br>WHERE **UNIQUE** (<br>&nbsp;&nbsp;SELECT Nome_dependente<br>&nbsp;&nbsp;FROM DEPENDENTE AS D<br>&nbsp;&nbsp;WHERE F.Cpf = D.Fcpf )|    ???????????????|Qual o primeiro e último nomes dos funcionários<br>cujos dependentes não têm nomes repetidos?|

<hr style="border:2px solid blue">

### Exercício 05

A atividade considera os requisitos de dados do **BD Passagens Aéreas**, conforme descrito a seguir.

O _Sistema de Informação de Passagens Aéreas_ visa ao acompanhamento e ao controle dos vôos domésticos e seus passageiros.<br>
O conceito primeiro a ser considerado é o _**voo**_:
- Tipicamente, há um conjunto de voos, cada qual é realizado (executado) periodicamente.
- Um voo é tipicamente composto por uma **sequência** de trechos [de voos]:
  - por exemplo, um voo particular de Brasília para Porto Alegre é composto pela sequência de trechos: Brasília-São Paulo, São Paulo-Belo Horizonte e Belo Horizonte-Porto Alegre;
  - sobre _voos realizados periodicamente_, se o voo for executado diariamente, todos os dias há a realização dos três trechos deste voo.

Sobre as execuções de trecho de voo:
- Cada execução de trecho possui uma **data/hora de partida _prevista_** e uma **data/hora de partida _efetivamente realizada_**:
  - o realizado pode diferir do previsto; por exemplo, quando há atraso na execução do trecho de voo.
- Cada execução de trecho possui uma **data/hora de chegada _prevista_** e uma **data/hora de chegada _efetivamente realizada_**.
- Cada execução de trecho possui **aeroporto de partida _previsto_** e **aeroporto de partida _realizado_**.
- Cada execução de trecho possui **aeroporto de chegada _previsto_** e **aeroporto de chegada _realizado_**.
- Cada execução de trecho ocorre por meio de uma **aeronave**.
- Uma aeronave possui um **mapa de assentos**:
  - o mapa de assentos de uma areonave se refere a todos os assentos ocupáveis por passageiros:
    - cada assento de uma aeronave é identificado pela fileira (por exemplo: 1, 2, 3, etc.) e pela posição na fileira (por exemplo: A, B, C, etc.);
    - cada assento está na **_primeira classe_** ou na **_classe executiva_**;
    - na execução de um trecho de voo, tipicamente há **assentos _ocupados_** e **assentos _não ocupados_**;
  - duas aeronaves distintas podem ter mapas de assentos distintos.

Ao adquirir uma passagem aérea, o passageiro (CPF, Nome, Data de Nascimento, etc.) contrata uma **sequência** de trechos de voos (não necessariamente do mesmo voo), cada trecho com execução (realização) prevista para determinada data/hora:
- Por exemplo, se um passageiro pretende ir de Brasília para Macapá com partida em uma data/hora, pode utilizar:
  - a sequência de trechos Brasília-São Paulo e São Paulo-Belo Horizonte de um voo; e
  - a sequência de trechos Belo Horizonte-Belém e Belém-Macapá de outro voo;
  - obviamente, a primeira sequência deve anteceder a segunda no tempo.
- Em cada trecho de voo, o passageiro ocupará um assento da aeronave pertinente à execução do trecho na data/hora prevista.

Algumas demandas informacionais são:
1. Quais os trechos por voo? Qual a cidade que participa (partida ou chegada) de mais trechos de voo?
1. Quantos são os trechos cujo destino é cidade X?
1. Quais as cidades que são origem de pelo menos um trecho, mas não são destino de qualquer trecho, e vice-versa?
1. Qual o grafo diário, em relação ao mês X, dos trechos com execução prevista?
1. Quais os passageiros que mais repetiram assentos, dentre todos os trechos de voo executados?
1. Qual o mapa de assentos da aeronave X?
1. Quais os voos com menor ocupação de passageiros no período X? Considere a média de ocupação de todos os trechos de cada voo executados no período. Em cada trecho de voo executado, a ocupação é a razão entre o número de assentos ocupados e o número de assentos da aeronave em questão.
1. Quais os passageiros com mais trechos voados no último mês?
1. Quais os destinos mais voados no último mês? Se refere ao destino do último trecho de cada passagem aérea.
1. Quais as passagens de maior realização no último mês? Se refere às passagens que compartilham a origem do primeiro trecho e o destino do último trecho.

Desenhe um DER capaz de atender todas as demandas informacionais acima:<br>
&#9786; É necessário 'desenhar' o DER completo.
