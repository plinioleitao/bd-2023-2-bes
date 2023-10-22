## Resultado

Clique [AQUI](../media/bd-2023-2-bes-resumo.pdf) para ver as notas.

#### Avaliação em 05/10/2023
1. Conforme enunciado da questão, a definição de banco de dados ser tal que "englobe o conteúdo das seis definições apresentadas". Nesse sentido, a definição deve mencionar: (1) conjunto de dados; (2) dados relacionados entre si; (3) dados operacionais (reflete a dinâmica de algum domínio); (4) dados armazenados (os dados são retidos/guardados, pois possuem valor); (5) dados usados (há audiência, o que inclui o uso de sistemas/aplicações).
2. Apresentar exemplos de metadados, em vez de classificação de metadados. Os exemplos devem ser contextualizados, evitando respostas curtas que dão margem a abstração e ambiguidade (dado ou metadado?). Por exemplo: 'título de um livro', em vez de 'título'.

#### Avaliação em 19/10/2023
- Sobre definição, construção, manipulação e compartilhamento de banco de dados: a construção denota a armazenagem de dados em meio controlado pelo SGBD.
- Quantas cópias do livro intitulado “Tribo Perdida” existem na unidade da biblioteca cujo nome é “Central”? -> LIVRO; LIVRO_COPIAS; UNIDADE_BIBLIOTECA.
- Recupere o nome de todos os usuários que não possuem livros emprestados em seu nome. -> LIVROS_EMPRESTIMOS; USUARIO
- Para cada livro que é emprestado da unidade da biblioteca cujo nome é “Central” e cuja data de devolução é hoje, recupere o título do livro, o nome e o endereço do usuário que pegou o livro emprestado.	-> LIVRO; LIVROS_EMPRESTIMOS; UNIDADE_BIBLIOTECA; USUARIO
- Para cada unidade da biblioteca, recupere o nome da unidade e o número total de livros emprestados pela unidade.	-> LIVROS_EMPRESTIMOS; UNIDADE_BIBLIOTECA
- Recupere o nome, endereço e número de livros emprestados para todos os usuários que possuem mais de cinco livros emprestados.	-> LIVROS_EMPRESTIMOS; USUARIO
- Para livro cujo autor (ou coautor) é “Stephen King”, recupere o título e o número de cópias pertencentes à unidade da biblioteca cujo nome é “Central”.	-> LIVRO; LIVRO_AUTOR; LIVRO_COPIAS; UNIDADE_BIBLIOTECA
