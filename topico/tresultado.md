## Resultado

Clique [AQUI](../media/bd-2023-2-bes-resumo.pdf) para ver as notas.

#### Avaliação em 05/10/2023
1. Conforme enunciado da questão, a definição de banco de dados ser tal que "englobe o conteúdo das seis definições apresentadas". Nesse sentido, a definição deve mencionar: (1) conjunto de dados; (2) dados relacionados entre si; (3) dados operacionais (reflete a dinâmica de algum domínio); (4) dados armazenados (os dados são retidos/guardados, pois possuem valor); (5) dados usados (há audiência, o que inclui o uso de sistemas/aplicações).
2. Apresentar exemplos de metadados, em vez de classificação de metadados. Os exemplos devem ser contextualizados, evitando respostas curtas que dão margem a abstração e ambiguidade (dado ou metadado?). Por exemplo: 'título de um livro', em vez de 'título'.

#### Avaliação em 19/10/2023
- Sobre definição, construção, manipulação e compartilhamento de banco de dados -> a construção denota a armazenagem de dados em meio controlado pelo SGBD.
- Quantas cópias do livro intitulado “Tribo Perdida” existem na unidade da biblioteca cujo nome é “Central”? -> LIVRO; LIVRO_COPIAS; UNIDADE_BIBLIOTECA.
- Recupere o nome de todos os usuários que não possuem livros emprestados em seu nome. -> LIVROS_EMPRESTIMOS; USUARIO
- Para cada livro que é emprestado da unidade da biblioteca cujo nome é “Central” e cuja data de devolução é hoje, recupere o título do livro, o nome e o endereço do usuário que pegou o livro emprestado.	-> LIVRO; LIVROS_EMPRESTIMOS; UNIDADE_BIBLIOTECA; USUARIO
- Para cada unidade da biblioteca, recupere o nome da unidade e o número total de livros emprestados pela unidade.	-> LIVROS_EMPRESTIMOS; UNIDADE_BIBLIOTECA
- Recupere o nome, endereço e número de livros emprestados para todos os usuários que possuem mais de cinco livros emprestados.	-> LIVROS_EMPRESTIMOS; USUARIO
- Para livro cujo autor (ou coautor) é “Stephen King”, recupere o título e o número de cópias pertencentes à unidade da biblioteca cujo nome é “Central”.	-> LIVRO; LIVRO_AUTOR; LIVRO_COPIAS; UNIDADE_BIBLIOTECA

#### Avaliação em 26/10/2023

1. RESULT ← π <sub>Pnome</sub> ( FUNCIONARIO ⋈ <sub>Cpf = Fcpf</sub> DEPENDENTE )
1. AUX ← π <sub>Cpf_gerente</sub> ( FUNCIONARIO ⋈ <sub>Cpf_supervisor = Cpf_gerente</sub> DEPARTAMENTO )<br>RESULT ← π<sub>Pnome</sub> ( FUNCIONARIO ⋈ <sub>Cpf = Cpf_gerente</sub> AUX )
1. RESULT ← π <sub>T1.Fcpf</sub> ( ρ <sub>T1</sub> (TRABALHA_EM) ⋈ <sub>T1.Fcpf = T2.Fcpf</sub> &#8743; <sub>T1.Pnr &#8800; T2.Pnr</sub> ρ <sub>T2</sub> (TRABALHA_EM) )

#### Avaliação em 09/11/2023

1. PRODUTO_CENTRAL ← π <sub>Produto</sub> ( σ <sub>Unidade="Central"</sub> ( FABRICA ) )<br>
RESULT ← π <sub>Cliente</sub> ( PRODUTO_CENTRAL ⋈ <sub>PRODUTO_CENTRAL.Produto = USA.Produto</sub> USA )
1. PRODUTO_CENTRAL ← π <sub>Produto</sub> ( σ <sub>Unidade="Central"</sub> ( FABRICA ) )<br>
CLIENTE_CENTRAL ← π <sub>Cliente</sub> ( PRODUTO_CENTRAL ⋈ <sub>PRODUTO_CENTRAL.Produto = USA.Produto</sub> USA )<br>
RESULT ← π <sub>Cliente</sub> ( USA )  &#8213; CLIENTE_CENTRAL
1. PRODUTO_CENTRAL ← π <sub>Produto</sub> ( σ <sub>Unidade="Central"</sub> ( FABRICA ) )<br>
PRODUTO_NAO_CENTRAL ← π <sub>Produto</sub> ( FABRICA ) &#8213; PRODUTO_CENTRAL<br>
CLIENTE_NAO_CENTRAL ← π <sub>Cliente</sub> ( PRODUTO_NAO_CENTRAL ⋈ <sub>PRODUTO_NAO_CENTRAL.Produto = USA.Produto</sub> USA )<br>
RESULT ← π <sub>Cliente</sub> ( USA )  &#8213; CLIENTE_NAO_CENTRAL

