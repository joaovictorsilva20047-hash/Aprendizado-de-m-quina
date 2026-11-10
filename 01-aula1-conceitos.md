<img src="assets/logo-udf.jpg" alt="UDF Centro Universitário" width="230">

**Profa. Kadidja Valéria | UDF**  
Ciência de Dados e Aprendizado de Máquina · Sistemas de Informação · 2026.2

# Aula 1 — Conceitos e classificação de problemas

## Identificação

- Estudante ou equipe: **João Victor Alves Silva**
- Turma: **Lab 05**
- Data de realização: **04/11/2026**
- Integrantes e contribuições (se em equipe): **individual**

## Objetivos

Distinguir programação tradicional e Machine Learning, identificar atributos e alvo e diferenciar classificação, regressão e agrupamento.

## 1. Explicação com suas palavras

1. Como um modelo aprende com dados? **Um modelo aprende por meio da análise de vários dados e exemplos que são apresentados a ele. Durante esse processo, o computador identifica padrões e características que ajudam a encontrar respostas. Depois de aprender com esses dados, ele consegue utilizar o conhecimento adquirido para fazer previsões ou identificar informações novas.**
2. Qual diferença entre algoritmo e modelo? **O algoritmo é o conjunto de instruções e métodos utilizados para ensinar o computador a encontrar padrões nos dados. Já o modelo é o resultado desse processo de aprendizado. Ou seja, o algoritmo é o método utilizado para aprender, enquanto o modelo é aquilo que foi aprendido.**
3. Compare uma regra de bloqueio de palavra com um modelo de spam. **Uma regra de bloqueio de palavra funciona de maneira programada, identificando palavras específicas que foram definidas anteriormente para bloquear uma mensagem. Já um modelo de spam aprende analisando várias mensagens que já foram classificadas como spam ou legítimas. Dessa forma, ele consegue identificar diferentes padrões, mesmo quando uma mensagem não apresenta exatamente as palavras que foram bloqueadas por uma regra.**
4. Dê um exemplo de atributo e alvo e defina o momento da previsão. **Um exemplo seria utilizar informações de estudantes para prever se eles podem abandonar os estudos.

Os atributos seriam informações como frequência nas aulas, notas e quantidade de atividades entregues. O alvo seria a situação do estudante, podendo ser evasão ou permanência.

A previsão aconteceria quando um novo estudante fosse analisado com base nessas informações, permitindo que o modelo estimasse a possibilidade de ele permanecer ou abandonar o curso.**

## 2. Quadro comparativo

| Critério | Supervisionado | Não supervisionado |
| --- | --- | --- |
| Presença de alvo no treino | Possui um alvo conhecido, com respostas previamente identificadas. | Não possui alvo ou respostas previamente definidas. |
| Pergunta que pode responder | Qual será a resposta ou categoria de um novo dado? | Quais padrões ou grupos existem nesses dados? |
| Tipo de saída | Categorias ou valores numéricos. | Grupos, padrões e associações. |
| Tarefas e exemplo | Classificação de spam e previsão de preços. | Agrupamento de clientes por comportamento de compra. |
| Dados necessários | Dados com exemplos e resultados conhecidos. | Dados sem classificação ou rótulos prévios. |
| Forma de avaliação | Comparação das previsões com as respostas corretas. | Análise da qualidade e organização dos grupos encontrados. |
| Limitação | Depende de dados classificados corretamente e em quantidade suficiente. | Os grupos encontrados podem não ter significado prático ou serem difíceis de interpretar. |

## 3. Situações-problema

Os casos são cenários didáticos. Escolha **pelo menos cinco** e justifique sua classificação pelo significado do alvo ou por sua ausência.

| Caso | Situação-problema |
| --- | --- |
| 1 Educação | Prever evadiu/permaneceu com histórico rotulado de turmas anteriores. |
| 2 Saúde | Estimar o tempo de espera em minutos a partir de registros de atendimento. |
| 3 Comércio | Descobrir perfis de compra sem categorias prévias de clientes. |
| 4 Finanças | Prever inadimplente/adimplente com contratos e desfechos conhecidos. |
| 5 Segurança digital | Distinguir spam/legítima com mensagens já revisadas. |
| 6 Comércio | Estimar o total de vendas em reais na próxima semana. |
| 7 Educação | Agrupar perfis de acesso ao ambiente virtual sem rótulo de evasão. |
| 8 Saúde | Classificar exames em categorias previamente definidas por especialistas. |

| Caso escolhido | Alvo ou ausência de alvo | Categoria, quantidade ou grupos? | Abordagem e justificativa | Dados necessários e limitação |
| --- | --- | --- | --- | --- |
| 1. Educação | Possui alvo: evadiu ou permaneceu. | Categoria | Aprendizado supervisionado de classificação, pois existem exemplos anteriores com resultados conhecidos. | Histórico de frequência, notas e situação dos estudantes. A limitação é que nem sempre os dados conseguem representar todos os motivos da evasão. |
| 2. Saúde | Possui alvo: tempo de espera em minutos. | Quantidade numérica. | Aprendizado supervisionado de regressão, pois o objetivo é estimar um valor numérico. | Registros de atendimentos, horários e duração das consultas. A limitação é que imprevistos podem alterar o tempo de espera. |
| 3. Comércio | Não possui alvo ou categorias definidas anteriormente. | Grupos. | Aprendizado não supervisionado de agrupamento, pois o objetivo é encontrar perfis de clientes com comportamentos semelhantes. | Histórico de compras, frequência e valores gastos. A limitação é que os grupos encontrados podem não representar exatamente o comportamento de todos os clientes. |
| 4. Finanças | Possui alvo: inadimplente ou adimplente. | Categoria | Aprendizado supervisionado de classificação, pois existem contratos anteriores com resultados conhecidos. | Histórico de pagamentos, valores dos contratos e atrasos. A limitação é que o comportamento financeiro pode mudar ao longo do tempo. |
| 7. Educação | Não possui alvo de evasão ou permanência. | Grupos | Aprendizado não supervisionado de agrupamento, pois busca encontrar estudantes com comportamentos de acesso semelhantes. | Registros de acesso ao ambiente virtual, frequência e participação nas atividades. A limitação é que acessar pouco o sistema não significa necessariamente que o estudante irá abandonar o curso. |

## 4. Raciocínio crítico

“Detectar fraude” define sozinho o tipo de aprendizado? Compare o uso de exemplos rotulados e a busca de operações atípicas sem rótulos. **Não. Detectar fraude não define sozinho o tipo de aprendizado, pois isso depende da maneira como os dados são utilizados.

Quando temos exemplos anteriores de operações que já foram identificadas como fraudulentas ou legítimas, podemos utilizar o aprendizado supervisionado de classificação. Nesse caso, o modelo aprende com os resultados conhecidos e tenta identificar novas fraudes.

Por outro lado, quando não temos operações classificadas, podemos utilizar o aprendizado não supervisionado para encontrar movimentações diferentes do comportamento habitual. Assim, o sistema identifica operações suspeitas que precisam ser analisadas.

Portanto, a diferença está na existência ou não de dados previamente classificados. Os dois métodos podem ajudar na identificação de fraudes, mas trabalham de maneiras diferentes.**

## Entrega

Salve este arquivo preenchido. Critérios: distinção conceitual, pertinência dos dados, justificativa e clareza. [Voltar ao início](README.md).
