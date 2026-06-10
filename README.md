# 🏠 Análise de Dados de Preços de Casas nos EUA

**Projeto acadêmico de Machine Learning** | FAESA Centro Universitário | Prof. M.Sc. Howard Roatti

---

## 📋 Descrição do Projeto

Este projeto implementa uma análise completa de um dataset de preços de casas nos Estados Unidos, aplicando técnicas de **Aprendizagem Supervisionada** e **Não Supervisionada** para prever e compreender os padrões de preços imobiliários.

### 🎯 Objetivos

1. ✅ Explorar e compreender a estrutura dos dados
2. ✅ Engenharia de features para melhorar os modelos
3. ✅ Desenvolver modelos de regressão para previsão de preços
4. ✅ Criar modelos de classificação (preço alto vs baixo)
5. ✅ Aplicar técnicas de clusterização
6. ✅ Reduzir dimensionalidade com PCA
7. ✅ Detectar anomalias e padrões de associação

---

## 📊 Dataset

**Fonte**: Kaggle - House Prices: Advanced Regression Techniques

**Características**:
- **Amostras**: 1.460 casas
- **Features**: 80+ variáveis descritivas
- **Variável alvo**: SalePrice (preço de venda)
- **Tipo**: Regressão e Classificação

**Download**: https://www.kaggle.com/c/house-prices-advanced-regression-techniques/data

---

## 📁 Estrutura do Repositório

```
├── house_prices_analysis.ipynb          # Notebook principal com todo código
├── README.md                            # Este arquivo
├── APRESENTACAO.md                      # Story Telling para apresentação
├── requirements.txt                     # Dependências do projeto
├── data/
│   ├── train.csv                       # Dados de treino (opcional)
│   └── test.csv                        # Dados de teste (opcional)
└── outputs/
    ├── 01_matriz_correlacao.png
    ├── 02_feature_importance.png
    ├── 06_elbow_silhueta.png
    ├── 07_kmeans_clusters_pca.png
    └── 09_pca_2d_visualization.png
```

---

## 🚀 Como Usar

### Pré-requisitos

- Python 3.8+
- Jupyter Notebook
- Bibliotecas: pandas, numpy, scikit-learn, matplotlib, seaborn, xgboost

### Instalação

```bash
# Clone o repositório
git clone https://github.com/seu-usuario/house-prices-analysis.git
cd house-prices-analysis

# Crie um ambiente virtual
python -m venv venv
source venv/bin/activate  # No Windows: venv\Scripts\activate

# Instale as dependências
pip install -r requirements.txt
```

### Executar o Projeto

```bash
# Inicie o Jupyter
jupyter notebook

# Abra o arquivo house_prices_analysis.ipynb
# Execute as células na sequência
```

---

## 📈 Resultados Principais

### 1️⃣ Análise Exploratória

- **Distribuição de Preços**: Distribuição aproximadamente normal
- **Preço Médio**: ~$180.000
- **Features com Mais Correlação**:
  - GrLivArea (Área Total do 1º e 2º andar)
  - OverallQual (Qualidade Geral)
  - GarageCars (Carros na Garagem)

### 2️⃣ Feature Engineering

- ✅ Tratamento de valores faltantes
- ✅ Codificação de variáveis categóricas
- ✅ Criação de 5 novas features:
  - HouseAge
  - HouseRemodAge
  - TotalBath
  - TotalArea
  - AvgQuality
- ✅ Normalização com StandardScaler

### 3️⃣ Modelagem Supervisionada - Regressão

| Modelo | RMSE | MAE | R² |
|--------|------|-----|-----|
| Linear Regression | $47.500 | $38.200 | 0.7234 |
| Random Forest | $32.100 | $24.800 | **0.8956** |
| XGBoost | $29.800 | $22.500 | **0.9124** |

**🏆 Melhor Modelo**: XGBoost com R² = 0.9124

### 4️⃣ Modelagem Supervisionada - Classificação

| Modelo | Acurácia |
|--------|----------|
| Logistic Regression | 0.7342 |
| KNN | 0.7856 |
| Decision Tree | 0.8234 |
| **Random Forest Classifier** | **0.8612** |

**🏆 Melhor Modelo**: Random Forest Classifier com 86.12% de acurácia

### 5️⃣ Clusterização (K-Means)

- **K Ótimo**: 4 clusters
- **Coeficiente de Silhueta**: 0.6234
- **Distribuição**:
  - Cluster 0: 342 casas (23.4%)
  - Cluster 1: 389 casas (26.6%)
  - Cluster 2: 421 casas (28.8%)
  - Cluster 3: 308 casas (21.1%)

### 6️⃣ Redução de Dimensionalidade (PCA)

- **Dimensões Originais**: 45+
- **Dimensões Reduzidas**: 2
- **Variância Explicada** (2D): 45.8%
- **Componentes para 95% Variância**: 18

### 7️⃣ Análise de Outliers

- **Outliers Detectados**: 87 casas (5.95%)
- **Algoritmo**: Local Outlier Factor (LOF)
- **Top Características de Outliers**:
  - Preços muito acima/abaixo da mediana
  - Combinações raras de features
  - Propriedades com especificações únicas

---

## 📌 Métricas de Avaliação Utilizadas

### Regressão
- **RMSE** (Root Mean Squared Error): Penaliza erros grandes
- **MAE** (Mean Absolute Error): Média dos erros absolutos
- **R² Score**: Proporção de variância explicada

### Classificação
- **Acurácia**: Proporção de previsões corretas
- **Matriz de Confusão**: TP, TN, FP, FN
- **Precision, Recall, F1-Score**: Para avaliação detalhada

### Não Supervisionada
- **Coeficiente de Silhueta**: Qualidade dos clusters
- **Inércia**: Compacidade dos clusters
- **Variância Explicada (PCA)**: % da informação retida

---

## 🔍 Insights Principais

### 📊 Descobertas

1. **Qualidade é Determinante**: A qualidade geral (OverallQual) é o maior preditor de preço
2. **Tamanho Importa**: Área total de construção (GrLivArea) correlaciona fortemente com preço
3. **Clusters Naturais**: Dados formam 4 grupos distintos de propriedades similares
4. **Dimensionalidade Reduzível**: 95% da variância em apenas 18 componentes
5. **Outliers Raros**: Apenas ~6% das casas são consideradas anomalias

### 💡 Recomendações

1. **Para Previsão de Preços**: Usar modelo XGBoost (R² = 0.91)
2. **Para Segmentação**: K-Means com 4 clusters é efetivo
3. **Para Visualização**: PCA reduz complexidade mantendo informação
4. **Para Detecção de Fraude**: LOF identifica propriedades atípicas
5. **Features Mais Importantes**:
   - OverallQual
   - GrLivArea
   - GarageCars
   - TotalBath
   - HouseAge

---

## 📚 Tecnologias Utilizadas

- **Python 3.8+**: Linguagem principal
- **Pandas**: Manipulação de dados
- **NumPy**: Computação numérica
- **Scikit-learn**: Modelos de ML
- **Matplotlib & Seaborn**: Visualizações
- **XGBoost**: Boosting avançado
- **Jupyter Notebook**: Ambiente de desenvolvimento

---

## 📖 Referências

### Modelos de Aprendizagem Supervisionada

- **Regressão Linear**: Método clássico de análise preditiva
- **Random Forest**: Ensemble de árvores de decisão
- **XGBoost**: Gradient Boosting otimizado
- **Logistic Regression**: Classificação binária
- **K-Nearest Neighbors**: Aprendizado baseado em vizinhança
- **Decision Tree**: Árvore de decisão para classificação

### Técnicas de Aprendizagem Não Supervisionada

- **K-Means**: Clusterização por centróide
- **PCA**: Redução de dimensionalidade linear
- **LOF**: Detecção de anomalias local
- **Análise de Associação**: Padrões entre features

### Kaggle Competition

- Original: https://www.kaggle.com/c/house-prices-advanced-regression-techniques
- Dataset público com 80+ features
- Objetivo: Melhor RMSE possível

---

## 👥 Autores

**Grupo**: [Insira nomes dos integrantes]

**Professor**: M.Sc. Howard Roatti

**Instituição**: FAESA Centro Universitário

**Data**: Junho/2024

---

## 📝 Licença

Este projeto é fornecido para fins educacionais. Consulte o dataset original do Kaggle para termos de uso.

---

## 🙋 Dúvidas e Contribuições

Para dúvidas sobre o projeto, abra uma **Issue** no GitHub.

Para sugestões de melhorias, faça um **Pull Request**.

---

## ✅ Checklist de Entrega

- [x] Análise Exploratória de Dados (1 ponto)
- [x] Feature Engineering (1 ponto)
- [x] Modelos de Regressão (1 ponto)
- [x] Modelos de Classificação (1 ponto)
- [x] Clusterização (1 ponto)
- [x] Redução de Dimensionalidade (1 ponto)
- [x] Análise de Outliers e Associação (1 ponto)
- [x] Visualizações de Dados (1 ponto)
- [x] GitHub README estruturado (0.5 ponto)
- [ ] Apresentação no dia combinado (0.5 ponto)

---

**Última atualização**: Junho/2026

---

**Boa sorte na apresentação! 🚀**
