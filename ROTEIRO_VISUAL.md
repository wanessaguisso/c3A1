# 🎬 ROTEIRO VISUAL DE APRESENTAÇÃO

*Siga este roteiro célula por célula. Imprima ou abra no celular!*

---

## 🎯 SLIDE MENTAL 1: INTRODUÇÃO

```
┌─────────────────────────────────────────────┐
│  ANÁLISE DE PREÇOS DE CASAS NOS EUA         │
│                                             │
│  📊 Dataset: 1.460 casas, 81 variáveis      │
│  🎯 Objetivo: Prever preços + Padrões       │
│  🤖 7 Modelos ML + 4 Técnicas Não Sup.      │
└─────────────────────────────────────────────┘
```

**FALAR:** "Vou apresentar nossa análise de preços de casas nos EUA..."

---

## 📂 CÉLULA 1: CARREGAMENTO

```python
✅ Dados carregados
Treino: (1460, 81)
Teste: (1459, 80)
```

**FALAR:** "Carregamos 1.460 casas para treino. O teste não tem SalePrice - é o que vamos prever."

**APONTAR:** Primeira tabela com as 5 casas

---

## 🔗 CÉLULA 2: CORRELAÇÃO

```
🎨 GRÁFICO: 01_matriz_correlacao.png
```

**FALAR:** "Esta matriz mostra relações entre variáveis."

**APONTAR:** 
- "Cores vermelhas = correlação forte"
- "OverallQual: **0.79** - o mais forte!"
- "GrLivArea: **0.71**"
- "GarageCars: **0.64**"

**INSIGHT:** "Qualidade + Área + Garagem = Preço Alto!"

---

## 🛠️ CÉLULA 3-4: FEATURE ENGINEERING

```
🔤 Codificação: Texto → Números
🔢 Imputação: Preencher ausentes
📏 Normalização: StandardScaler
✂️ Split: 80% treino / 20% teste
```

**FALAR:** "Preparamos os dados para ML:"
1. "Transformamos categorias em números"
2. "Preenchemos valores ausentes com mediana"
3. "Normalizamos tudo na mesma escala"
4. "Separamos treino e teste"

---

## 📈 CÉLULA 5: REGRESSÃO LINEAR

```
┌──────────────────────────┐
│  REGRESSÃO LINEAR        │
├──────────────────────────┤
│  RMSE:  $34,000         │
│  MAE:   $22,000         │
│  R²:    0.85            │
└──────────────────────────┘
```

**FALAR:** "Modelo mais simples. Assume relação linear."

**INTERPRETAR:** "Erro médio de $34k. Explica 85% da variação."

---

## 🌳 CÉLULA 6: RANDOM FOREST

```
┌──────────────────────────┐
│  RANDOM FOREST  🏆       │
├──────────────────────────┤
│  RMSE:  $28,500  ⬇️      │
│  MAE:   $17,500  ⬇️      │
│  R²:    0.89     ⬆️      │
└──────────────────────────┘
```

```
🎨 GRÁFICO: 02_feature_importance.png
```

**FALAR:** "Ensemble de 200 árvores. Captura não-linearidade."

**APONTAR GRÁFICO:** "Top 3: OverallQual, GrLivArea, GarageCars"

**DESTAQUE:** "Melhorou! R² subiu para **0.89** - agora explica 89%!"

---

## 🎯 CÉLULA 7: KNN REGRESSOR

```
┌──────────────────────────┐
│  KNN REGRESSOR           │
├──────────────────────────┤
│  RMSE:  $35,000         │
│  MAE:   $23,000         │
│  R²:    0.82            │
└──────────────────────────┘
```

**FALAR:** "Prevê baseado nas 5 casas mais similares."

**COMPARAR:** "Menos preciso que RF, mas rápido."

---

## 📊 CÉLULA 8: COMPARAÇÃO REGRESSÃO

```
🎨 GRÁFICO: 03_regressao_comparacao.png
```

**APONTAR:** Gráfico de barras com 3 modelos

**FALAR:** "**Random Forest vence** com R²=0.89!"

**EXPLICAR:** "Por quê? Captura relações complexas. Exemplo: dobrar área não dobra preço."

---

## 🎭 CÉLULA 9-12: CLASSIFICAÇÃO

```
Transformação: Preço → Alto/Baixo
Mediana: $163.000
```

### Modelo 1: Regressão Logística 🏆
```
┌──────────────────────────┐
│  REG. LOGÍSTICA  🏆      │
│  Acurácia: 94.52%       │
│  (276/292 casas certas)  │
└──────────────────────────┘
```

### Modelo 2: Árvore de Decisão
```
Acurácia: 88.70%
```

### Modelo 3: KNN Classifier
```
Acurácia: ~92%
```

### Modelo 4: Naive Bayes
```
Acurácia: ~88%
```

**FALAR:** "Classificamos como 'caro' ou 'barato'. Útil para filtros rápidos."

---

## 📊 CÉLULA 13: COMPARAÇÃO CLASSIFICAÇÃO

```
🎨 GRÁFICO: 05_classificacao_metricas.png
```

**APONTAR:** Barra da Regressão Logística (a mais alta)

**FALAR:** "**94.52% de acurácia** - quase perfeita! Muito acima dos 50% de baseline."

---

## 🎯 CÉLULA 14-15: CLUSTERIZAÇÃO

```
🎨 GRÁFICO: 06_elbow_silhueta.png
```

**APONTAR:** 
- Gráfico esquerdo: "Cotovelo em K=4"
- Gráfico direito: "Silhueta valida K=4"

**FALAR:** "K-Means busca grupos naturais. Métodos indicam **4 clusters** ideal."

```
🎨 GRÁFICO: 07_kmeans_clusters_pca.png
```

**APONTAR:** 
- 4 cores diferentes (clusters)
- Centróides em vermelho (X)

**INTERPRETAR OS 4 GRUPOS:**
```
🏘️ Cluster 0: Casas ECONÔMICAS
🏡 Cluster 1: Casas MÉDIAS (padrão)
🏠 Cluster 2: Casas PREMIUM
🏰 Cluster 3: Casas de LUXO
```

**APLICAÇÃO:** "Sites imobiliários podem recomendar casas similares!"

---

## 📐 CÉLULA 16-17: PCA

```
📊 VARIÂNCIA EXPLICADA:
  PC1: 12.94%
  PC2: 5.21%
  ...
  Total (60 componentes): 95%
```

**FALAR:** "PCA reduz dimensões. Das 80 features, apenas **60 componentes** explicam 95%."

**INSIGHT:** "Temos redundância! Podemos simplificar sem perder informação."

```
🎨 GRÁFICO: 09_pca_2d_visualization.png
```

**APONTAR:** 
- Esquerdo: "Clusters em 2D"
- Direito: "Cores = preços. Casas caras se agrupam aqui!"

---

## 🔍 CÉLULA 18: OUTLIERS (LOF)

```
┌──────────────────────────────┐
│  OUTLIERS DETECTADOS         │
├──────────────────────────────┤
│  Total: 64 casas (5.48%)    │
│  Inliers: 1104 (94.52%)     │
└──────────────────────────────┘
```

**FALAR:** "LOF identifica casas atípicas - características muito diferentes."

**O QUE SÃO:**
- ❓ Erros de registro?
- 💎 Oportunidades de investimento?
- 🏛️ Propriedades únicas?

**APLICAÇÃO:** "Investidor deve analisar esses 64 outliers!"

---

## 🔗 CÉLULA 19: APRIORI

```
🎨 GRÁFICO: 11_apriori_lift.png
```

**FALAR:** "Apriori encontra associações entre características."

**EXEMPLO:** "Zona RL → Garagem 2 carros (frequente)"

**MÉTRICAS:**
- Support: Frequência
- Confidence: Probabilidade
- Lift: Força da associação (>1 = interessante)

**APLICAÇÃO:** "Construtores decidem features padrão por bairro."

---

## 🎯 CÉLULA 20: CONCLUSÕES

```
╔════════════════════════════════════════╗
║  🎯 CONCLUSÕES FINAIS                  ║
╠════════════════════════════════════════╣
║  1️⃣ TOP FATORES DE PREÇO:             ║
║     • OverallQual                      ║
║     • GrLivArea                        ║
║     • GarageCars                       ║
║                                        ║
║  2️⃣ MELHOR MODELO REGRESSÃO:          ║
║     🏆 Random Forest (R²=0.89)        ║
║     → Erro médio: $17.500             ║
║                                        ║
║  3️⃣ MELHOR MODELO CLASSIFICAÇÃO:      ║
║     🏆 Reg. Logística (94.52%)        ║
║                                        ║
║  4️⃣ SEGMENTAÇÃO:                      ║
║     • 4 perfis distintos de casas     ║
║                                        ║
║  5️⃣ OUTLIERS:                         ║
║     • 64 casas atípicas (5.48%)       ║
╚════════════════════════════════════════╝
```

---

## 💡 INSIGHTS PRÁTICOS

```
┌─────────────────────────────────────┐
│  💰 PARA COMPRADORES:               │
│  ✅ Priorize OverallQual            │
│  ✅ Área habitável importa          │
│  ✅ Garagem agrega valor            │
└─────────────────────────────────────┘

┌─────────────────────────────────────┐
│  🏠 PARA VENDEDORES:                │
│  ✅ Invista em qualidade            │
│  ✅ Amplie área útil/garagem        │
│  ✅ Mantenha porão/banheiros OK     │
└─────────────────────────────────────┘

┌─────────────────────────────────────┐
│  📈 PARA INVESTIDORES:              │
│  ✅ Modelo prevê com 89% precisão   │
│  ✅ Analise os 64 outliers          │
│  ✅ Foque em OverallQual alto       │
└─────────────────────────────────────┘
```

---

## 🎤 FECHAMENTO

```
╔════════════════════════════════════════╗
║                                        ║
║  "Alcançamos R²=0.89 na predição de   ║
║   preços - um resultado sólido e      ║
║   aplicável no mundo real."           ║
║                                        ║
║  ✅ 1.460 casas analisadas            ║
║  ✅ 7 modelos treinados               ║
║  ✅ 4 técnicas não supervisionadas    ║
║  ✅ 8 visualizações profissionais     ║
║  ✅ Insights práticos extraídos       ║
║                                        ║
║        OBRIGADA! 🎉                   ║
║        Perguntas? 🙋                  ║
║                                        ║
╚════════════════════════════════════════╝
```

---

## 🎬 TRANSIÇÕES ENTRE SEÇÕES

**EDA → Feature Eng:**
> "Agora que entendemos os dados, vamos prepará-los para ML..."

**Feature Eng → Regressão:**
> "Com dados preparados, treinamos 3 modelos de regressão..."

**Regressão → Classificação:**
> "Agora mudamos o problema: em vez de preço exato, classificamos alto/baixo..."

**Classificação → Não Supervisionado:**
> "Até aqui usamos labels. Agora vamos descobrir padrões sem supervisão..."

**Não Sup → Conclusões:**
> "Juntando tudo, extraímos insights práticos para o mercado..."

---

## ⏱️ CHECKPOINT DE TEMPO

```
✅ Minuto 5  → Terminei EDA
✅ Minuto 7  → Terminei Feature Eng
✅ Minuto 11 → Terminei Regressão
✅ Minuto 14 → Terminei Classificação
✅ Minuto 19 → Terminei Não Supervisionado
✅ Minuto 22 → Fechamento
```

**Se estiver atrasado(a):** Acelere nos modelos KNN e Naive Bayes (menos importantes)  
**Se estiver adiantado(a):** Elabore mais nos insights práticos

---

## 🔥 MANTRA FINAL

```
╔═══════════════════════════════════════╗
║                                       ║
║   Eu DOMINO o conteúdo                ║
║   Eu ENTENDO os resultados            ║
║   Eu estou PREPARADA                  ║
║                                       ║
║   VAMOS LÁ! 🚀                        ║
║                                       ║
╚═══════════════════════════════════════╝
```

---

**IMPRIMA ESTA FOLHA E LEVE PARA A APRESENTAÇÃO!** 📄✨
