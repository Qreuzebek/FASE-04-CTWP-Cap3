# FASE 04 — Cap 3: Classificação de Variedades de Grãos

Projeto de machine learning para classificação automática de três variedades de trigo (**Kama**, **Rosa** e **Canadian**) a partir de medições físicas dos grãos, usando o [Seeds Dataset](https://archive.ics.uci.edu/dataset/236/seeds).

---

## Estrutura do repositório

```
.
└── seeds.ipynb   # Notebook principal com análise, treinamento e resultados
```

O dataset de entrada (`seeds.txt`) é carregado diretamente no notebook. Baixe-o [aqui](https://archive.ics.uci.edu/dataset/236/seeds) e coloque na mesma pasta do notebook antes de executar.

---

## O que o notebook faz

O notebook está dividido em 4 fases:

| Fase | Conteúdo |
|------|----------|
| **1 — Análise Exploratória** | Estatísticas descritivas, histogramas, boxplots por variedade, pairplot e matriz de correlação |
| **2 — Pré-processamento** | Split treino/teste (70/30 estratificado) e normalização com `StandardScaler` |
| **3 — Treinamento e Comparação** | Treino de 5 modelos (Regressão Logística, KNN, Árvore de Decisão, Random Forest, SVM) com validação cruzada |
| **4 — Insights e Conclusões** | Grid Search nos dois melhores modelos, tabela comparativa e análise dos erros |

---

## Como executar

### Pré-requisitos

```bash
pip install pandas numpy scikit-learn seaborn matplotlib
```

### Passos

1. Clone o repositório:
   ```bash
   git clone https://github.com/Qreuzebek/FASE-04-CTWP-Cap3.git
   cd FASE-04-CTWP-Cap3
   ```

2. Baixe o arquivo `seeds.txt` e coloque-o na mesma pasta do notebook.

3. Abra o notebook:
   ```bash
   jupyter notebook seeds.ipynb
   ```

4. Execute todas as células em ordem (`Run All` ou `Shift + Enter` célula a célula).

---

## Resultados principais

| Modelo | Acurácia no teste |
|--------|:-----------------:|
| Regressão Logística | **90.5%** |
| KNN | 88.9% |
| SVM | 88.9% |
| SVM Otimizado (GridSearch) | 88.9% |
| Decision Tree | 85.7% |
| Random Forest | 84.1% |

- A variedade **Rosa** foi a mais fácil de classificar (95% de precisão e recall em todos os modelos).
- A maior dificuldade foi distinguir **Canadian** de **Kama**, as duas variedades de menor tamanho.
- As features mais importantes segundo o Random Forest foram **perímetro**, **comprimento do sulco** e **área**.
