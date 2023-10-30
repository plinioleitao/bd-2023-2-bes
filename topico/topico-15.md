## [Tópico T15] - Álgebra Relacional - Vários comandos
###### *by Prof. Plinio Sa Leitao-Junior (INF/UFG)*

Seja abaixo uma [*ilustração para o banco de dados*](../media/fig-mr-2.jpg) **BD Empresa** [1], conforme Modelo Relacional (MR):

<img src="../media/fig-mr-2.jpg" width="400">

### Grupo 1: Fácil

1. π <sub>Pnome, Unome</sub> (FUNCIONARIO)
1. σ <sub>Sexo="F"</sub> (FUNCIONARIO)
1. π <sub>Pnome, Unome</sub> ( σ <sub>Sexo="F"</sub> (FUNCIONARIO) )
1. TRABALHA_EM  X  PROJETO
1. ρ FUNC ( π Pnome, Unome ( σ <sub>Sexo="F"</sub> (FUNCIONARIO) ) )
1. ρ FUNC (PrimeiroNome, UltimoNome) ( π <sub>Pnome, Unome</sub> ( σ <sub>Sexo="F"</sub> (FUNCIONARIO) ) )

### Grupo 2: Simples

1. TRABALHA_EM &#8904; <sub>Fcpf=cpf</sub>  FUNCIONARIO
1. FUNCIONARIO * ( ρ (cpf, Projnumero, Horas) (TRABALHA_EM) * PROJETO )
1. π <sub>Cpf_supervisor</sub> (FUNCIONARIO) ∪ π <sub>Cpf_gerente</sub> (DEPARTAMENTO)
1. π <sub>Cpf_supervisor</sub> (FUNCIONARIO) ∩ π <sub>Cpf_gerente</sub> (DEPARTAMENTO)
1. π <sub>Cpf_supervisor</sub> (FUNCIONARIO) – π <sub>Cpf_gerente</sub> (DEPARTAMENTO)
1. SUP_E_GER ← ρ (cpf) ( π Cpf_supervisor (FUNCIONARIO) ∩ π Cpf_gerente (DEPARTAMENTO) )<br>RESP ← π Pnome, Unome ( FUNCIONARIO * SUP_E_GER )
1. π Cpf, Pnome (FUNCIONARIO) ∩ π Fcpf, Nome_dependente (DEPENDENTE)
1. SUP_SEM_DEP ← ρ (cpf) ( π Cpf_supervisor (FUNCIONARIO) – π Fcpf (DEPENDENTE) )<br>RESP ← π Pnome, Unome ( FUNCIONARIO * SUP_SEM_DEP )

### Grupo 3: Motivador

1. ℑ CONTA cpf , MÉDIA Salario, MÁXIMO Salario , MÍNIMO Salario (FUNCIONARIO)
1. Dnr ℑ CONTA cpf , MÉDIA Salario, MÁXIMO Salario , MÍNIMO Salario (FUNCIONARIO)
1. ρ RESUMO (Dnumero, QtdeFunc, MediaSalario) Dnr ℑ CONTA cpf , MÉDIA Salario (FUNCIONARIO)<br>RESPOSTA ← π Dnome, QtdeFunc, MediaSalario ( DEPARTAMENTO * RESUMO )
1. ρ SUPERVISOR (π Cpf, Pnome (FUNCIONARIO) )<br>FUNCIONARIO &#8904; <sub>FUNCIONARIO.Cpf_supervisor = SUPERVISOR.Cpf</sub> SUPERVISOR
1. ρ SUPERVISOR (Cpf_supervisor, Pnome_supervisor) (π Cpf, Pnome (FUNCIONARIO) )<br>π Pnome, Pnome_supervisor (FUNCIONARIO * SUPERVISOR ) 

### _Under Construction_
