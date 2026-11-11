<img src="assets/logo-udf.jpg" alt="UDF Centro Universitário" width="230">

**Profa. Kadidja Valéria | UDF**  
Ciência de Dados e Aprendizado de Máquina · Sistemas de Informação · 2026.2

# Aula 2 — Registro do laboratório supervisionado

## Identificação

- Estudante ou equipe: **João Victor Alves Silva**
- Turma: **Lab 05**
- Data de realização: **10/11/2026**
- Integrantes e contribuições (se em equipe): **individual**
## Percurso escolhido

- [x] Python/Colab ou Jupyter.
- [ ] Orange Data Mining.

Use o [notebook de apoio](notebooks/laboratorio.ipynb) ou o [CSV sintético](dados/educacionais-sinteticos.csv). O CSV contém 600 registros fictícios. Atributos: `frequencia_sem4`, `nota_sem4`, `entregas_sem4`. Alvo: `evasao_fim_semestre` (0 permaneceu, 1 evadiu). As associações foram definidas pela simulação, sem validade empírica sobre estudantes reais.

## 1. Ambiente e reprodução

| Item | Registro |
| --- | --- |
| Ambiente e data | Google Colab ou Jupyter Notebook, utilizando Python. Data: 10/11/2026. Ambiente efetivamente utilizado: confirmar após execução. |
| Versões das ferramentas/bibliotecas | A registrar após executar o notebook. Devem ser informadas as versões do Python, pandas, scikit-learn, NumPy e Matplotlib, caso utilizadas. |
| Semente aleatória | A confirmar no código do notebook. Não presumir um valor. |
| Caminho do notebook executado ou fluxo Orange | notebooks/laboratorio-equipe.ipynb (caminho previsto para salvar a execução). |
| Origem dos dados e condição sintética | Arquivo dados/educacionais-sinteticos.csv, disponibilizado para a atividade. São 600 registros fictícios, sem validade empírica sobre estudantes reais. |

## 2. Problema e preparação

- Pergunta de negócio: **É possível utilizar informações de frequência, notas e entrega de atividades para identificar estudantes com maior possibilidade de evasão ao final do semestre?**
- Unidade de análise e horizonte: **Cada registro representa um estudante fictício. A previsão considera informações referentes às primeiras quatro semanas do semestre, buscando identificar a situação do estudante ao final do semestre.**
- Atributos disponíveis no instante da previsão: **frequencia_sem4: frequência do estudante nas primeiras quatro semanas.
nota_sem4: nota obtida no período.
entregas_sem4: quantidade de atividades entregues.**
- Variável-alvo e sua natureza: **A variável-alvo é evasao_fim_semestre, que representa a situação do estudante ao final do semestre.
- 0 = permaneceu.
- 1 = evadiu.
É uma variável categórica binária, portanto, trata-se de um problema de classificação supervisionada.**
- Ausências e outros problemas encontrados: **A existência de valores ausentes, registros duplicados ou informações inconsistentes deverá ser verificada durante a análise do CSV. Não devemos afirmar que existem ou não existem problemas sem conferir os dados.**
- Tratamentos e conjunto usado para aprendê-los: **Primeiramente, será feita uma inspeção dos dados para verificar valores ausentes e inconsistências. Caso seja necessário realizar algum tratamento, os parâmetros serão definidos utilizando somente os dados de treinamento, evitando que informações do teste influenciem o aprendizado.**

## 3. Desenvolvimento e teste

- Método de divisão e justificativa: **Método de divisão e justificativa:

A proposta é dividir os dados em 80% para treinamento e 20% para teste, utilizando divisão estratificada para manter uma proporção semelhante das classes nos dois conjuntos.**
- Quantidades de treino e teste: **Considerando os 600 registros:
- Treinamento: 480 registros.
- Teste: 120 registros.
Essas quantidades correspondem à divisão planejada e precisam ser confirmadas na execução.**
- Procedimento de validação no treino: **A proposta é utilizar validação cruzada estratificada com cinco partes (5-fold). Dessa maneira, o modelo será avaliado em diferentes divisões do treinamento, permitindo comparar seu desempenho com mais segurança.**
- Parâmetros da árvore e como foram escolhidos: **Será utilizada uma árvore de decisão, inicialmente com parâmetros padrão. Depois, serão testadas alterações na profundidade máxima da árvore e na quantidade mínima de registros por folha, buscando encontrar um equilíbrio entre aprendizado e capacidade de generalização.**
- Como o teste ficou fora da seleção: **O conjunto de teste será separado antes da escolha dos parâmetros e utilizado somente na avaliação final. Assim, os resultados do teste não influenciarão a escolha do melhor modelo.**

### Alternativa Orange

Confira o alvo como categórico. Registre as conexões: File/Select Columns → Test & Score (Data), Tree → Test & Score (Learner), Test & Score → Confusion Matrix (Evaluation Results). Data Table permite inspeção. Se usar Preprocess, conecte o preprocessor ao learner para ajustar transformações dentro do treino. Não use apenas `Test on train data` como avaliação final.

**Fluxo e método de avaliação realmente utilizados:** PREENCHER

Se comparar configurações, use validação no treino e reserve teste independente. Documente em Test & Score as entradas Data e Test Data, quando utilizadas.

## 4. Resultados calculados de classificação

| Modelo | Configuração | Acurácia de treino | Acurácia de validação e dispersão | Acurácia de teste |
| --- | --- | --- | --- | --- |
| Referência | PREENCHER | PREENCHER | PREENCHER | PREENCHER |
| Árvore final | PREENCHER | PREENCHER | PREENCHER | PREENCHER |

Não invente valores. Se sua ferramenta não produziu uma medida, registre “não calculada” e explique.

**Matriz: linhas reais e colunas previstas; classe positiva = 1.**

| Real / previsto | Permaneceu (0) | Evadiu (1) |
| --- | --- | --- |
| Permaneceu (0) | PREENCHER (TN) | PREENCHER (FP) |
| Evadiu (1) | PREENCHER (FN) | PREENCHER (TP) |

- Acurácia calculada manualmente pela matriz: **PREENCHER**
- Sensibilidade da classe 1: **PREENCHER**
- Comparação com referência: **PREENCHER**
- Consequências dos falsos positivos: **PREENCHER**
- Consequências dos falsos negativos: **PREENCHER**
- Interpretação do gráfico e da árvore: **PREENCHER**

## 5. Experimentos no treino

Compare parâmetros usando apenas treino/validação. Após conhecer o teste, uma nova seleção exige novo teste independente para avaliação final.

| Experimento | Alteração | Resultado de validação | Interpretação |
| --- | --- | --- | --- |
| 1 | PREENCHER | PREENCHER | PREENCHER |
| 2 | PREENCHER | PREENCHER | PREENCHER |

Responda:

1. Como a profundidade e o tamanho das folhas podem afetar o sobreajuste? **PREENCHER**
2. Retirar um atributo e observar mudança no desempenho prova causalidade? **PREENCHER**
3. Se 95% permanecem, o que acontece com um modelo que sempre prevê permanência? **PREENCHER**

## 6. Regressão — seção independente

Execute a seção da biblioteca no notebook ou registre o procedimento equivalente em Orange. Dados também sintéticos. Alvo numérico: empréstimos por semana.

| Item | Registro |
| --- | --- |
| Atributos e alvo | PREENCHER |
| Divisão e preparação | PREENCHER |
| MAE do modelo e unidade | PREENCHER |
| MAE da referência | PREENCHER |
| R² do teste | PREENCHER |
| Interpretação do gráfico observado/previsto | PREENCHER |
| Interpretação dos resíduos | PREENCHER |
| Limitação de extrapolação | PREENCHER |

Explique por que R² não é porcentagem de acertos: **PREENCHER**

## 7. Evidências e conclusão

- Link relativo do notebook/fluxo: **PREENCHER**
- Links das imagens, se houver: **PREENCHER**
- Principal aprendizado: **PREENCHER**
- Limitações de generalização e vieses possíveis: **PREENCHER**
- Cuidados com privacidade e uso responsável: **PREENCHER**

Para inserir uma imagem salva, use `![Matriz de confusão](assets/minha-matriz.png)` e confira se o arquivo existe. Mostre apenas dados sintéticos.

[Voltar ao início](README.md).
