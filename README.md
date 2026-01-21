# Classificação da Satisfação Econômica na América Latina com Machine Learning

---

## Visão Geral do Projeto

- Classificação binária da satisfação econômica de cidadãos latino-americanos  
- Uso de dados reais do **Latinobarómetro**  
- Comparação de múltiplos algoritmos de classificação  
- Avaliação de diferentes estratégias de balanceamento  
- Análise de importância de variáveis para suporte à tomada de decisão  

---

## Objetivo

Aplicar algoritmos de Machine Learning para:

- Classificar cidadãos como **satisfeitos** ou **insatisfeitos** com a economia  
- Avaliar o impacto de técnicas de balanceamento de classes  
- Comparar modelos individuais e métodos de ensemble  
- Identificar os principais fatores associados à percepção econômica  

---

## Base de Dados

Os dados utilizados são provenientes das pesquisas do **Latinobarómetro**, referentes aos anos de:
https://www.latinobarometro.org/lat.jsp
- 2016  
- 2017  
- 2018  
- 2020  

### Características do conjunto de dados

| Etapa | Observações | Variáveis |
|------|------------|-----------|
| Dados brutos | 80.816 | 409 |
| Após pré-processamento | 43.141 | 62 |

### Variável alvo

A variável *satisfação com a economia* foi transformada em classificação binária:

- **Satisfeito:** respostas 1 e 2  
- **Insatisfeito:** respostas 3 e 4  

---

## Metodologia

O fluxo de desenvolvimento seguiu as seguintes etapas:

1. Integração de dados de múltiplos anos  
2. Remoção de variáveis com alto percentual de valores ausentes  
3. Tratamento de valores faltantes  
4. Binarização de variáveis categóricas  
5. Normalização dos dados  
6. Separação em treino (80%) e teste (20%)  
7. Aplicação de técnicas de balanceamento:
   - Sem balanceamento
   - Random Undersampling
   - SMOTE-N  
8. Treinamento dos modelos  
9. Otimização de hiperparâmetros com validação cruzada (5-fold)  
10. Avaliação de desempenho e comparação dos resultados
11. Utilização de modelos explicativos para compreender o comportamento dos modelos  

---

## Modelos Utilizados

- Random Forest  
- Gradient Boosting  
- XGBoost  
- Naïve Bayes (Bernoulli)  
- Ensemble Voting:
  - Hard Voting
  - Soft Voting  

---

## Métricas de Avaliação

Os modelos foram avaliados com métricas amplamente utilizadas em projetos profissionais:

- Precision  
- Recall  
- F1-score  
- Accuracy  

Devido ao desbalanceamento do problema, foi dada atenção especial ao desempenho da **classe minoritária (Satisfeito)**.

---

## Resultados Principais

- Acurácia próxima de **86%** para Gradient Boosting, XGBoost, Random Forest e Soft Voting  
- Melhor desempenho geral na identificação da classe **Insatisfeito**  
- Técnicas de ensemble apresentaram melhor equilíbrio entre precisão e recall  
- Soft Voting mostrou melhor capacidade de generalização sem perda relevante de acurácia  

---

## Análise de Importância das Variáveis

As variáveis mais relevantes para a classificação foram:

1. **Satisfação com a democracia**  
2. **Comparação da economia em relação a 12 meses antes**  
3. **Percepção de progresso do país**  
4. **Avaliação da distribuição de renda**  
5. **Percepção sobre a atuação do governo**  

Os resultados indicam uma forte relação entre **percepção econômica** e **avaliação institucional e política**, reforçando a importância de variáveis socioeconômicas no modelo.

---

## Tecnologias e Ferramentas

- Python  
- Jupyter Notebook  
- Pandas  
- NumPy  
- Matplotlib  
- Seaborn  
- Scikit-learn  
- XGBoost  
- mlxtend  
- shap
