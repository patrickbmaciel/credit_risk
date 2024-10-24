# Credit Risk

## Introdução

O projeto "Credit Risk" tem como objetivo explorar a inadimplência em empréstimos, um desafio significativo para instituições financeiras que buscam mitigar riscos e aprimorar suas decisões de crédito. A análise de risco de crédito é fundamental, pois possibilita prever a capacidade de um indivíduo de cumprir suas obrigações financeiras. Isso é representado pela variável `status_emprestimo`, onde um valor de 1 indica adimplência e 0, inadimplência. Essa abordagem oferece uma compreensão mais profunda dos fatores que influenciam o comportamento de pagamento dos mutuários. Para alcançar esses objetivos, o projeto se baseia em um conjunto de dados públicos disponível no Kaggle, que abrange características financeiras e pessoais dos indivíduos.

Esta documentação descreve a análise de risco de crédito realizada no script `1.analise_regressao`, onde foi desenvolvido um modelo de regressão logística para estimar a probabilidade de inadimplência. A exploração dos dados revelou padrões relevantes, fornecendo uma base sólida para a construção de um modelo preditivo eficaz. Além disso, a análise permitiu identificar os perfis de mutuários e os riscos associados, proporcionando insights valiosos para a tomada de decisões.

Na sequência, o projeto também se aprofunda na implementação de diferentes algoritmos de machine learning, conforme detalhado no script `2.machine_learning`. Esses algoritmos, incluindo Árvores de Decisão, Naive Bayes, K-Nearest Neighbors e Random Forest, são aplicados para prever a inadimplência, classificando a variável alvo em adimplência (1) ou inadimplência (0). Cada modelo é avaliado quanto à sua acurácia e eficácia, permitindo uma comparação das abordagens utilizadas.

Ao final, o projeto busca não apenas otimizar os processos de concessão de crédito, mas também oferecer uma ferramenta robusta para a avaliação do risco de crédito, capacitando as instituições financeiras a tomar decisões mais informadas e assertivas.

## Scripts

### 1.analise_regressao

No pré-processamento dos dados, realiza-se diversos processos, como renomeação de colunas, tratamento de variáveis categóricas e binárias, além de lidar com outliers e valores ausentes. Destacam-se o ajuste de idades acima de 77,5 anos e tempos de emprego superiores a 65,5 anos, considerados outliers. O tratamento de outliers foca em garantir maior precisão nos resultados, removendo idades consideradas fora do padrão. Essas medidas visam evitar distorções nos modelos preditivos que serão desenvolvidos.

A análise exploratória inclui estatísticas descritivas das variáveis, destacando padrões como maior comprometimento de renda e juros elevados para maiores valores de empréstimos. As visualizações gráficas revelam que a maioria dos empréstimos gira em torno de 10.000 dólares, com taxas de juros distribuídas em torno de 10%. Além disso, elabora-se uma matriz de correlação, que indica uma forte relação entre idade e duração do histórico de crédito, e uma correlação moderada entre renda anual e valor do empréstimo.

Posteriormente, estima-se um modelo de regressão logística, através da função `stats::glm` para prever a inadimplência de empréstimos, representada pela variável `status_emprestimo`, usando as variáveis presentes na base de dados, com o objetivo de estimar a probabilidade de inadimplência com base nos fatores socioeconômicos e históricos financeiros dos indivíduos. Tal modelo apresenta acurácia de 86.79%.

### 2.machine_learning

Neste script. utiliza-se algoritmos de machine learning para estimar a capacidade de um indivíduo de cumprir suas obrigações financeiras. Para alcançar esse objetivo, os dados foram divididos em conjuntos de treino (70%) e teste (30%), visando evitar overfitting e garantir a generalização dos modelos.

Entre os modelos implementados, a Árvore de Decisão utiliza critérios como Entropia e Gini para dividir os dados, gerando uma acurácia de aproximadamente 92%. O modelo Naive Bayes, por sua vez, baseia-se em probabilidades calculadas a partir das características independentes e obteve uma acurácia de 81%. Já o modelo de Aprendizado Baseado em Instância (KNN), que classifica novos dados com base na proximidade a amostras de treinamento, apresentou uma acurácia de 82%, após normalização e codificação das variáveis.

O Random Forest, que combina múltiplas árvores de decisão para melhorar a precisão e reduzir o overfitting, teve o melhor desempenho, com uma acurácia de 93%, utilizando 100 árvores. Cada um dos modelos foi avaliado com base em matrizes de confusão e acurácia, permitindo uma comparação direta de seus resultados.

Conclui-se que, embora o Random Forest tenha se destacado em termos de precisão, todos os modelos fornecem insights valiosos sobre a relação entre as variáveis que influenciam o risco de crédito. As abordagens aplicadas permitem que instituições financeiras utilizem essas previsões para tomar decisões mais informadas, otimizando processos de concessão de crédito e mitigando riscos financeiros.
