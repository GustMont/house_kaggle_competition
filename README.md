# House Prices - Advanced Regression Techniques

Olá! Se você está aqui, quer dizer que passamos da Sprint 3, maravilha! Agora vamos focar em descobrir padrões dos nossos dados, e esta atividade ponderada é perfeita para consolidarmos o nosso conhecimento. Em grupo, se juntem e entrem no site: [house_kaggle_competition](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques), leiam o desafio, baixem os dados, façam uma pequena análise e criem seus notebooks para solucionar o problema proposto. Boa sorte! Não esqueça de submeter o desafio global, vamos tentar chegar nos 100 primeiros do mundo!

## Para que eu possa corrigir a sua ponderada, faça o `git clone` deste repositório, faça suas modificações (lembre-se que este notebook ajudará você e seu grupo à desenvolver o relatório do Artefato, em relação à ocrrelações dos dados), crie uma branch com seu nome, e faça um commit das suas modificações NA SUA BRANCH. No card coloque o link do seu commit =)

## Claro, o Barema da ponderada segue:

Desenvolvimento e Submissão de Soluções para o Desafio House Kaggle

1. Compreensão do desafio House Kaggle, incluindo o contexto e os objetivos do desafio;
2. Implementação das soluções do desafio no notebook preparatório de forma que passem nos testes pré-setados;
3. Utilização de técnicas, algoritmos e bibliotecas para a resolução dos problemas propostos;
4. Submissão das soluções desenvolvidas ao Kaggle Open Challenge;
5. Descrição dos requisitos para o desenvolvimento das soluções e compreensão do desafio House Kaggle;
6. Explicação detalhada do desenvolvimento das soluções, avaliação, otimização e submissão ao Kaggle utilizando comentários no código;

A escrita do texto deve ser clara, precisa e livre de erros ortográficos. Será descontado até 20% dos pontos caso sejam encontrados erros de ortografia.

Avançado (9,1 - 10): cumpriu todos os 6 itens descritos acima;

Intermediário (7,1 - 9): cumpriu 5 dos 6 itens descritos acima;

Básico (4,1 - 7): cumpriu 4 dos 6 itens descritos acima;

Insuficiente (0 - 4): cumpriu menos que 3 itens descritos acima.


# Agora vamos para a nossa ponderada!

Descreva aqui as diferenças de treinamento que você encontrou entre os treinamentos de Ensemble. Passe por todos os métodos.
Descreva as modificações que você porpôs.

## Compreensão do desafio House Kaggle:

O desafio tem como objetivo prever o preço de imóveis com base em características como características físicas, condição da propriedade, localização, entre outros.

## Implementação das soluções e utilização de técnicas, algoritmos e bibliotecas:

O código do desafio apresenta a implementação de técnicas de Machine Learning para prever o preço dos imóveis, desde a preparação dos dados, utilizando as bibliotecas Pandas e NumPy, até a aplicação de modelos como Ridge, KNN, SVM, Árvores de Decisão, entre outros.

## Comparação entre modelos ensemble:

### Floresta Aleatória (RandomForestRegressor):
É um tipo de Ensemble baseado em árvores de decisão.
- Treinamento: Cria várias árvores de decisão com subconjuntos aleatórios dos dados e características.
- Etapas: Cada árvore é treinada independentemente usando amostras aleatórias e características aleatórias.
- Observação: As previsões de cada árvore são combinadas para obter uma previsão final.

### Boosted Trees (AdaBoost e GradientBoosting):
- Técnica: Constrói modelos sequencialmente para corrigir os erros dos modelos anteriores.
- Treinamento: Cada modelo é treinado sequencialmente, onde cada novo modelo é ajustado aos erros residuais do modelo anterior.
- Etapas: A cada iteração, o modelo tenta melhorar os erros cometidos pelo modelo anterior, focando nos exemplos que não foram bem previstos.
- Observação: AdaBoost pondera exemplos incorretamente classificados, enquanto GradientBoosting ajusta a resposta dos modelos anteriores.

### XGBoost:
- Técnica: Uma implementação otimizada de Gradient Boosting.
- Treinamento: Utiliza uma função de perda personalizável, otimiza uma função objetivo e usa aprendizado por gradientes.
- Etapas: Lida com a regularização internamente para evitar overfitting.
- Observação: Suporta treinamento paralelo, sendo mais rápido do que o GradientBoosting tradicional.

### Stacking:
Combina os resultados de vários modelos de base para criar um modelo final.
- Treinamento: Usa modelos variados (Gradient Boosting, AdaBoost, Ridge, SVM) como base.
- Etapas: Os modelos de base são treinados independentemente e, em seguida, suas saídas são usadas como entrada para o modelo final (usando uma meta-regressão neste caso).
- Observação: Mais complexo de configurar devido à necessidade de definir múltiplos modelos de base e o modelo final.
