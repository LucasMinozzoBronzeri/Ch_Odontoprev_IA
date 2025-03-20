# IA_Odontoprev (em desenvolvimento)

# Integrantes do Grupo
- RM552648 - Diego Costa Silva: Desenvolvedor Java, frontend com Thymeleaf e mobile com React.
- RM553745 - Lucas Minozzo Bronzeri: DevOps e Machine Learning.
- RM553870 - Thaís Ribeiro Asfur: Quality Assurance e API em .NET (Minimal API).

# Desrcrição do Problema
Clínicas médicas fraudando consultas/exames/cirurgias. E, clientes que utilizam do plano de forma imprópria/desnecessária. Tudo isso gerando gastos para a Odontoprev.

# Descrição Solução
Um aplicativo que coloque a Odontoprev, o cliente, e a clínica no mesmo ambiente. Um aplicativo para que os clientes possam agendar e acompanhar suas consultas, contratar planos, e avaliar clínicas.  A clínica por sua vez, poderá lançar informações referentes as consultas dos clientes, e receber também.
Além disso, tanto no perfil da clínica e cliente, terão um histórico de consultas. Assim, podemos identificar padrões que indicam uma possível fraude, como: 
-	Consultas para o mesmo “problema” marcadas de forma recorrente;
-	Tempo de atendimento; 
-	Autorização prévia para procedimentos, consultas e exames mais caros;  

Uma funcionalidade que queremos implementar, é que só será possível começar um atendimento, se o cliente agendar e a clínica validar as informações. Por último, no momento do check-in, a consulta só irá ser iniciada, quando o cliente apresentar o código token para a recepcionista. Além disso, o sistema acompanhará um validador de IP, identificando possíveis compartilhamentos de login.

# Público-alvo
Clínicas, e pessoas físicas a partir dos 18 anos. De um lado, uma clínica buscando mais clientes e de outro lado o cliente, com acesso as melhores e mais indicadas clínicas que temos parceria. 

# Estudo de mercado
Amil Dental e Unimed Odonto, são duas das principais concorrentes da Odontoprev, as duas, assim como a Odontoprev, têm algumas opções de planos, a Amil tem menos opções que as demais, com preços perto da média, a Unimed tem uma grande gama de planos, os dois apresentam um diferencial, eles têm um plano empresarial, para que empresas, com um valor reduzido, possam assinar em grandes cargas e “distribuir” para seus funcionários. A Odontoprev contém planos mais completos que suas concorrentes, tendo como principais benefícios no plano “Bem-Estar Orto White”:

-	Aparelho Fixo e Móvel;
-	Manutenção de aparelhos;
-	Documentação ortodôntica completa;
-	Clareamento estético com Gel;

# Potencial de Mercado
Temos um foco de mercado direcionado a maiores de idade, temos um grande potencial, vendo que na nossa proposta, deixamos o atendimento bem mais dinâmico e seguro para o consumidor, tendo prevenções a usos indevidos de planos, também com o crescimento da odontologia no país, podemos afirmar que devemos alcançar números surpreendentes.

# Projeto IA

Trabalhando com o treinamento de um modelo de regressão, que tem como dados: id_alerta, motivo, tipo_fraude, data_alerta, status, id_solicitacao_pagamento, id_paciente, cpf_paciente, data_nascimento_paciente, telefone_paciente, id_clinica, razao_social_clinica, cnpj_clinica, telefone_clinica, id_procedimento, descricao_procedimento, valor_procedimento, id_solicitacao, data_solicitacao, valor_requerido, status_pagamento e de acordo com a coluna tipo_fraude, é gerada a coluna Chances_Fraude, a coluna "Chances_Fraude", tem os valores de 0 e 1, sendo 0 = sem chances de fraude e 1 = existem chances de fraude, para este projeto estamos utilizando:    
- Pandas: Com o foco em ler o arquivo CSV selecionado "dados_fraude.csv";
- Matplotlib: Utilizado para a criação de gráficos, para a análise dos dados de Distribiução de Score de Crédito, Renda Anual vs Chances de Fraude e Número de Transações vs Chances de Fraude;
- Scikit-learn: Fazendo a separação dos dados em "X" e "y" depois fazemos a separação em X_train, X_test, y_train, y_test, utilizando "train_test_split", logo em seguida nós treinamos o modelo e utilizamos o accuracy_score, para vermos qual foi a Acurácia do modelo;
- Oracledb: Para que a conexão entre o projeto e o Banco de Dados seja estabelecida;  
  
Iremos melhorar a API para a coleta dos dados que serão utilizados no modelo de detecção de sinistros, o modelo, ainda na versão Beta, utiliza de dados ficticios, para que haja o funcionamento;  

# Melhorias Realizadas  

- Alteração do CSV utilizado: agora as colunas fazem mais sentido, tendo conexão com as colunas criadas no Banco de Dados;
- Maior tratamento de dados: na atualização do projeto, fizemos uma melhora no tratamento dos dados, já que tivemos que excluir linhas com valores nulos, codificar manualmente colunas com valores do tipo String e usar o LabelEncoder para uma codificação de colunas mais simples, como a de "status_pagamento" e a de "status";
- Mudança no modelo: Após mudarmos os dados para treinamento do modelo, também mudamos o tipo do nosso modelo, o que antes era um "Logistic Regression" virou um "Random Forest";  

# Melhorias para Próxima Entrega  

As melhorias previstas, são:  
- Conexão com o projeto: mesmo conectando com o banco de dados, por falta de dados inseridos, até o momento, não tivemos uma iclusão maior do nosso projeto;
- Modelo: mesmo chegando em uma acurácia de 90.4%, ainda precisamos melhora-lo, vista que tinhamos dois dados, "0" e "1", a precisão do modelo com o "0" foi de apenas 69%, ao mesmo tempo em que a precisão com o "1", foi de 94%;
  
# Links  

Projeto:  
https://youtu.be/Q-xwUeuJtAE
