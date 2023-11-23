## [Tópico 04] - Requisitos de Dados - <ind>BD e-cred</ins>
###### *by Prof. Plinio Sa Leitao-Junior (INF/UFG)*

O <ins>acesso ao crédito</ins> é um bem importante e constitui um elemento de qualidade para a sociedade. A <ins>concessão de crédito</ins> é baseada em muitos componentes, tal como o <ins>cálculo de indicadores de crédito</ins>, por exemplo, o risco de inadimplência de pessoas e empresas.

Nesse contexto, um <ins>novo serviço</ins> de apoio à concessão de crédito tem sido planejado, nos moldes de outros existentes, tais como SPC e SERASA. A ideia é prover informações úteis àqueles que utilizam o serviço, visando a <ins>apoiá-los em tomadas de decisão<ins> para a concessão de crédito. 

### Software

Para viabilizar <ins>a gestão e a operacionalização</ins> do serviço, será concebido o <ins>_software_ **e-cred**</ins>.

### Crédito

O **crédito** representa um <ins>valor monetário concedido</ins>, mediante uma <ins>análise positiva sobre sua concessão</ins>. Se o crédito for concedido, há uma <ins>contrapartida de pagamento</ins> do crédito por parte do <ins>beneficiário do crédito</ins>.<br>
&#x267B; Dois atores são identificados:<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ... aquele que <ins>concede o crédito</ins>, e<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ... aquele que <ins>recebe o crédito</ins>.

### Perfil de Usuário

Foram identificados <ins>três perfis de usuário</ins> para o serviço:
-	O usuário que <ins>primariamente utiliza o serviço</ins> é chamado de **ASSOCIADO** (pessoa física ou jurídica), pois usa o serviço para apoiar as suas decisões sobre concessões de crédito. Basicamente, os associados estão interessados em informações sobre pessoas com potencial para concessão de crédito.<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#x270D; ASSOCIADO é aquele que <ins>concede o crédito</ins>.
-	O usuário que <ins>solicita o crédito ao associado</ins> é chamado de **CLIENTE** (pessoa física ou jurídica), cujas informações de identificação, histórico das dívidas, histórico de indicadores de crédito e histórico de concessões de crédito podem ser obtidas a partir do banco de dados.<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#x270D; CLIENTE é aquele que <ins>recebe o crédito</ins>.
-	O usuário que <ins>administra o serviço</ins> é chamado de **GESTOR** (pessoa física).

### Dívida

Cada <ins>débito (passado ou presente)</ins> é chamado de <ins>dívida</ins>.<br>
&#x267B; Por exemplo, se um ASSOCIADO concedeu um crédito para um CLIENTE, mas o CLIENTE não pagou ao ASSOCIADO até a data de vencimento do compromisso, então uma `dívida` é caracterizada:<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#x270D; ASSOCIADO é o `credor da dívida`,<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#x270D; CLIENTE é o `devedor da dívida`.<br>
&#x267B; Uma dívida possui dois estados: 'em aberto' ou 'quitada':<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ... dados da **DÍVIDA EM ABERTO**:<br>
Associado credor, cliente devedor, identificador da dívida (número fornecido pelo associado), valor da dívida, tipo da dívida, data de vencimento.<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ... dados da **DÍVIDA QUITADA**:<br>
Todos os dados da dívida em aberto e: data de quitação, valor pago.

### Indicador de Crédito

Um **indicador de crédito** é um  <ins>componente para a tomada de decisão </ins> sobre a concessão de crédito. Vários são os indicadores de crédito disponibilizados pelo **e-cred**, tais como:<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ... _qualidade de cadastro_,<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ... _carteira elegível para cobrança_,<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ... &#8252; dentre outros &#8252;<br>
&#x267B; Se um associado solicitar, <ins>um indicador de crédito é calculado</ins> com relação a um cliente (pessoa física ou jurídica), para produzir um <ins>número decimal</ins>:<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ... qual o valor para o indicador _qualidade de cadastro_ daquela pessoa?<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ... qual o valor para o indicador _carteira elegível para cobrança_ daquela pessoa?

### Contratação de Indicador de Crédito

Se o associado <ins>contratar o direito de uso</ins> de um indicador de crédito:<br>
&#x267B; O associado poderá fornecer [e usar] a sua <ins>fórmula específica</ins> de cálculo para esse indicador, ou poderá utilizar a <ins>fórmula genérica</ins> (fórmula _default_) do indicador.<br>
&#x267B; O <ins>cálculo do indicador de crédito</ins> referente a um cliente poderá ser solicitado pelo associado, a qualquer tempo, para produzir um número decimal desse indicador em relação ao cliente.<br>
&#x267B; O associado irá <ins>pagar um valor</ins> por cada cálculo solicitado de indicador.<br>
&#x267B; Se um associado contratar um indicador, então há:<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ... um valor a ser pago por solicitação; e<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ... uma quantidade mínima mensal de solicitações – uma franquia.

### Concessão de crédito

A tomada de decisão sobre a concessão de um crédito para um cliente é uma responsabilidade do próprio associado. O _software_ **e-cred** apenas fornece informações.

A solicitação de concessão de crédito terá dois estados:  'aprovado' e 'reprovado', bem como:<br>
O associado que pode conceder o crédito, o cliente que solicitou o crédito, o valor do crédito solicitado, a data da solicitação do crédito e, se a solicitação for aprovada, a data da concessão do crédito. 

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
