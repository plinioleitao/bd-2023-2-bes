## [Tópico T16b] - Álgebra Relacional - Exercícios
###### *by Prof. Plinio Sa Leitao-Junior (INF/UFG)*

Para apoiar os exercícios e exemplo sobre as operações da Álgebra Relacional, considere a ilustração abaixo do **BD Empresa**.

<img src="../media/fig-mr-2.jpg" width="450">

Escreva em álgebra relacional as seguintes consultas:

1. Qual o nome dos projetos que o funcionário "João Silva" trabalha em?<br>
CPF_SILVA ← π <sub>CPF</sub> ( σ <sub>Pnome="João" AND Unome="Silva"</sub> (FUNCIONARIO) )<br>
TEMP ← π <sub>Pnr</sub> ( CPF_SILVA &#8904; <sub>Cpf=Fcpf</sub> TRABALHA_EM )<br>
RESULT ← π <sub>Projnome</sub> ( TEMP &#8904; <sub>Pnr=Projnumero</sub> PROJETO )
1. Qual o nome das pessoas que trabalham em pelo menos um dos projetos que o funcionário "João B Silva" trabalha em?<br>
CPF_SILVA ← π <sub>CPF</sub> ( σ <sub>Pnome="João" AND Unome="Silva"</sub> (FUNCIONARIO) )<br>
PROJETOS_SILVA ← π <sub>Pnr</sub> ( CPF_SILVA &#8904; <sub>Cpf=Fcpf</sub> TRABALHA_EM )<br>
CPFS ← π <sub>Pnr</sub> ( PROJETOS_SILVA &#8904; <sub>PROJETOS_SILVA.Pnr=TRABALHA_EM.Pnr</sub> TRABALHA_EM )<br>
1. Qual o nome das pessoas que não trabalham em qualquer dos projetos que o funcionário "João B Silva" trabalha em? Pessoas que não trabalham em qualquer projeto ESTÃO INCLUÍDAS no resultado da consulta.<br>
1. Qual o nome das pessoas em que todos os projetos que trabalham em estão entre os projetos que o funcionário "João B Silva" trabalha em? Pessoas que não trabalham em qualquer projeto NÃO ESTÃO INCLUÍDAS no resultado da consulta.<br>

IMPORTANTE: Use a sintaxe da Álgebra Relacional conforme os exemplos apresentados até então.
