# TP2 - Predição para Imobiliárias

## 👨‍🎓 Autor

**Matheus Felipe Gonçalves de Souza**

Projeto desenvolvido para a faculdade na disciplina de Ciência de Dados.

---

## 📌 Sobre o projeto

Este projeto tem como objetivo utilizar técnicas de **Machine Learning** para auxiliar uma empresa do setor imobiliário na análise e previsão de imóveis.

Foram desenvolvidos dois modelos preditivos:

- **Regressão Linear:** utilizada para prever o preço de venda dos imóveis.
- **Árvore de Decisão:** utilizada para classificar se um imóvel possui possibilidade de ser vendido rapidamente, em até 30 dias.

---

## 📊 Base de dados

O projeto utiliza o arquivo:

`imoveis_saopaulo.csv`

Os dados são referentes a imóveis de São Paulo e possuem informações utilizadas para realizar as previsões.

Antes da criação dos modelos, foi realizada uma análise exploratória dos dados, verificando:

- Quantidade de registros e colunas;
- Estatísticas descritivas;
- Valores nulos;
- Variáveis utilizadas nos modelos.

A coluna `id_imovel` foi removida por não possuir relevância para as previsões.

---

## 🤖 Modelos utilizados

### 1. Regressão Linear

A Regressão Linear foi utilizada para prever o:

**`preco_venda_reais`**

O conjunto de dados foi dividido em:

- 80% para treinamento;
- 20% para teste.

As principais métricas utilizadas foram:

- R²;
- MSE;
- RMSE.

A análise também permitiu observar a influência das variáveis no preço dos imóveis. Por exemplo, a área do imóvel apresentou uma relação positiva com o preço, enquanto a distância do marco zero apresentou uma relação negativa.

---

### 2. Árvore de Decisão

A Árvore de Decisão foi utilizada para prever a variável:

**`venda_rapida_30_dias`**

O objetivo é classificar os imóveis entre:

- **Venda rápida**
- **Venda demorada**

Foram utilizadas as métricas:

- Acurácia;
- Precisão;
- Recall;
- F1-Score;
- Matriz de Confusão.

---

## ⚠️ Análise de risco

Para a estratégia de marketing da imobiliária, foi analisada a diferença entre:

**Falso Positivo:** o modelo prevê que o imóvel será vendido rapidamente, mas isso não acontece.

**Falso Negativo:** o modelo prevê que o imóvel demorará para vender, mas ele é vendido rapidamente.

Neste projeto, o **Falso Positivo** é considerado mais prejudicial, pois pode fazer com que a empresa invista em publicidade para imóveis que possuem baixa probabilidade de venda rápida.

---

## 🔧 Otimização do modelo

Foi realizado um teste com diferentes valores de `max_depth` na Árvore de Decisão:

- 1
- 3
- 5
- 10
- None

O objetivo foi analisar o comportamento do modelo e identificar possíveis problemas de **overfitting** e **underfitting**.

Após a comparação dos resultados, foi escolhida a profundidade:

```python
max_depth = 5
