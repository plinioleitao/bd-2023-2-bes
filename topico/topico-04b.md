## [Tópico 04] - Requisitos de Dados - <ind>BD e-cred</ins>
###### *by Prof. Plinio Sa Leitao-Junior (INF/UFG)*

O <ins>acesso ao crédito</ins> é um bem importante e constitui um elemento de qualidade para a sociedade. A <ins>concessão de crédito</ins> é baseada em muitos componentes, tal como o <ins>cálculo de indicadores de crédito</ins>, por exemplo, o risco de inadimplência de pessoas e empresas.

Nesse contexto, um <ins>novo serviço</ins> de apoio à concessão de crédito tem sido planejado, nos moldes de outros existentes, tais como SPC e SERASA. A ideia é prover informações úteis àqueles que utilizam o serviço, visando a <ins>apoiá-los em tomadas de decisão<ins> para a concessão de crédito. 

### Software

Para viabilizar <ins>a gestão e a operacionalização</ins> do serviço, será concebido o software **e-cred**.

### Crédito

O **crédito** representa um <ins>valor monetário concedido</ins>, mediante <ins>análise positiva sobre sua concessão</ins>. Se o crédito for concedido, há uma <ins>contrapartida de pagamento</ins> (compromisso) por parte do <ins>beneficiário do crédito</ins>.

### Indicador de Crédito

Um **indicador de crédito** é um  <ins>componente para a tomada de decisão </ins> sobre a concessão de crédito. Vários são os indicadores de crédito disponibilizados pelo **e-cred**, tais como _qualidade de cadastro_ e _carteira elegível para cobrança_, dentre outros:
- um indicador de crédito é <ins>calculado como relação a uma pessoa</ins> (pessoa física ou jurídica), para produzir um <ins>número decimal</ins>:
  - qual o valor para o indicador _qualidade de cadastro_ daquela pessoa?
  - qual o valor para o indicador _carteira elegível para cobrança_ daquela pessoa?

### Perfil de Usuário

Foram identificados <ins>três perfis de usuário</ins> para o serviço:
-	Aquele que <ins>primariamente utiliza o serviço</ins> é chamado de **ASSOCIADO** (pessoa física ou jurídica), pois usa o serviço para apoiar as suas decisões sobre concessões de crédito. Basicamente, os associados estão interessados em informações sobre pessoas com potencial para concessão de crédito.
-	Aquele que <ins>solicita o crédito ao associado</ins> é chamado de **CLIENTE** (pessoa física ou jurídica), cujas informações de identificação, histórico das dívidas, histórico de indicadores de crédito e histórico de concessões de crédito podem ser obtidas a partir do banco de dados.
-	Aquele que <ins>administra o serviço</ins> é chamado de **GESTOR** (pessoa física).

### Dívida

Cada <ins>débito (passado ou presente)</ins> é chamado de <ins>dívida</ins>. Uma dívida possui dois estados: 'em aberto' ou 'quitada'. 

### Envio da Dívida

Como compromisso, cada associado <ins>'envia' dívidas em aberto dos seus clientes</ins> para o **e-cred**, visando a <ins>compor o banco de dados</ins>, com dados tais como:
-	cliente devedor, identificador da dívida (número interno do próprio associado), valor da dívida, tipo da dívida, data de vencimento, dentre outros dados.

Se a dívida for quitada em algum momento, o <ins>evento da quitação</ins> também deverá ser enviado, com os seguintes dados:
-	cliente devedor, identificador da dívida (número interno do próprio associado), data de quitação, valor pago.

### Mais requisitos ...

Blá ... blá 

### Demandas Informacionais

DEMANDAS INFORMACIONAIS - ASSOCIADO:
1. Qual o valor total das dívidas quitadas do Cliente X no Período Y?
1. Qual o valor total das dívidas em aberto do Cliente X?
1. Qual o valor computado do Indicador Z para o Cliente X?
1. Qual o histórico de concessões de crédito do Cliente X?
1. Qual o histórico de cálculo do Indicador Z para o Cliente X?
1. Quais os clientes possuem o mesmo nome fonetizado de "HEDMAR DE SOUSA SILVA"? Nesse caso, o nome fonetizado poderia ser "EDIMARSOUZACIUVA". 
