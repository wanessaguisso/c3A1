# 📋 COLA RÁPIDA - APRESENTAÇÃO

*Consulte este documento durante a apresentação para não esquecer nada importante!*

---

## 🎯 ESTRUTURA (17 min)

```
1. INTRO (2 min) → 2. EDA (3 min) → 3. FEATURE ENG (2 min) 
→ 4. REGRESSÃO (4 min) → 5. CLASSIFICAÇÃO (3 min) 
→ 6. NÃO SUPERVISIONADO (5 min) → 7. CONCLUSÕES (3 min)
```

---

## 📊 NÚMEROS-CHAVE (MEMORIZE!)

### Dataset
- **1.460** casas de treino
- **81** variáveis
- **$163.000** = preço mediano

### Correlações Mais Fortes
1. **OverallQual**: 0.79
2. **GrLivArea**: 0.71
3. **GarageCars**: 0.64

### Regressão (Melhor → Pior)
| Modelo | R² | RMSE |
|--------|-----|------|
| 🏆 Random Forest | **0.89** | $28.5k |
| Linear | 0.85 | $34k |
| KNN | 0.82 | $35k |

### Classificação (Melhor → Pior)
| Modelo | Acurácia |
|--------|----------|
| 🏆 Reg. Logística | **94.52%** |
| KNN | ~92% |
| Árvore | 88.70% |
| Naive Bayes | ~88% |

### Não Supervisionado
- **4 clusters** (K-Means)
- **60 componentes** PCA para 95% variância
- **64 outliers** (5.48%)

---

## 💬 FRASES PRONTAS

### Abertura
> "Vou apresentar nossa análise de preços de casas nos EUA, onde aplicamos 7 modelos de ML para prever valores e identificar padrões."

### Matriz de Correlação
> "OverallQual tem correlação de 0.79 com preço - o preditor mais forte. Isso significa: invista em qualidade geral!"

### Random Forest
> "Random Forest venceu com R²=0.89 - explica 89% da variação nos preços. É melhor que Linear porque captura relações não-lineares."

### Classificação
> "Transformamos em binário: preço alto vs baixo. Regressão Logística acertou 94.52% - 276 de 292 casas!"

### Clusters
> "K-Means identificou 4 perfis: econômicas, médias, premium e luxo. Útil para segmentação de marketing."

### PCA
> "Das 80 features, apenas 60 componentes explicam 95% da informação - temos redundância!"

### Outliers
> "64 casas são atípicas - possíveis oportunidades de investimento ou erros de registro."

### Fechamento
> "Alcançamos R²=0.89 - um resultado sólido e aplicável no mundo real. Obrigada!"

---

## ❓ PERGUNTAS ESPERADAS

### "Por que Random Forest venceu?"
✅ "Captura relações não-lineares. Dobrar área não dobra preço - há diminuição marginal. RF modela isso."

### "O que é R²?"
✅ "Proporção da variância explicada. 0.89 = 89% da variação nos preços é explicada pelo modelo."

### "Como escolheu K=4?"
✅ "Método Elbow + Silhueta. Ambos indicaram 4 como ideal - balanço entre detalhe e simplicidade."

### "Por que normalizar?"
✅ "KNN e Reg. Logística são sensíveis à escala. Área (500-5000) dominaria quartos (1-10). StandardScaler iguala."

### "Como evitou overfitting?"
✅ "Split 80/20 treino/teste + Random Forest com max_depth=15. R² consistente entre treino e teste."

### "Qual modelo em produção?"
✅ "Regressão: Random Forest (melhor R²). Classificação: Reg. Logística (rápida + 94.52%)."

---

## 🎨 GRÁFICOS (O QUE APONTAR)

### 01_matriz_correlacao.png
👉 "Cores vermelhas = correlação forte. OverallQual no topo!"

### 02_feature_importance.png
👉 "Top 3: OverallQual, GrLivArea, GarageCars."

### 03_regressao_comparacao.png
👉 "RF tem menor RMSE e maior R² - vencedor absoluto!"

### 05_classificacao_metricas.png
👉 "Regressão Logística quase 95% - muito acima do baseline de 50%!"

### 06_elbow_silhueta.png
👉 "Cotovelo em K=4. Silhueta também indica 4 como ótimo."

### 07_kmeans_clusters_pca.png
👉 "Veja como os 4 grupos se separam bem. Centróides em vermelho."

### 09_pca_2d_visualization.png
👉 "Esquerda: clusters. Direita: cores = preços. Casas caras se agrupam!"

### 11_apriori_lift.png
👉 "Lift >1 = associação interessante entre características."

---

## ✨ INSIGHTS FINAIS (MEMORIZE!)

### Para COMPRADORES
✅ Priorize qualidade geral (OverallQual)  
✅ Área habitável importa  
✅ Garagem agrega valor  

### Para VENDEDORES
✅ Invista em melhorias de qualidade  
✅ Amplie área útil/garagem  
✅ Mantenha porão/banheiros em bom estado  

### Para INVESTIDORES
✅ Modelo prevê com 89% precisão  
✅ Analise os 64 outliers (oportunidades!)  
✅ Foque em OverallQual alto  

---

## ⚡ ERROS COMUNS (EVITE!)

❌ "O modelo é bom" → ✅ "R²=0.89 - explica 89% da variância"  
❌ "Tem erro pequeno" → ✅ "Erro médio de $17.500"  
❌ "Achamos grupos" → ✅ "4 clusters com Silhueta validando"  
❌ Falar rápido demais  
❌ Pular os gráficos  
❌ Não olhar para a plateia  

---

## 🔥 DICA DE OURO

**Estruture cada seção assim:**
1. **O que fizemos** ("Aplicamos Random Forest...")
2. **O resultado** ("R²=0.89, RMSE=$28.5k")
3. **O que significa** ("Explica 89% da variação...")
4. **Por que importa** ("Melhor que Linear porque...")

---

## ⏱️ CONTROLE DE TEMPO

| Minuto | O que falar |
|--------|-------------|
| 0-2 | Intro + contexto |
| 2-5 | EDA + correlação |
| 5-7 | Feature engineering |
| 7-11 | Regressão (3 modelos) |
| 11-14 | Classificação (4 modelos) |
| 14-19 | Não supervisionado |
| 19-22 | Conclusões + insights |

⏰ **Se estiver atrasada:** Pule detalhes de KNN e Naive Bayes (foque em RF e Reg. Log)  
⏰ **Se estiver adiantada:** Elabore mais nos insights práticos

---

## 🎤 ÚLTIMAS PALAVRAS

**Antes de começar:**
- Respire fundo 3x
- Sorria
- Lembre: você domina o conteúdo!

**Durante:**
- Fale devagar
- Aponte para gráficos
- Faça pausas após números importantes

**Ao final:**
- "Obrigada! Perguntas?"
- Mantenha confiança nas respostas

---

**VOCÊ VAI ARRASAR! 🚀🎉**
