# 🏦 Classificação de Risco de Crédito

> Análise de Machine Learning para predição de risco de crédito usando o **German Credit Dataset** (OpenML).

---

## 📋 Visão Geral

Este projeto aplica técnicas de Machine Learning para classificar clientes como **bom** ou **mau risco de crédito**, com base em variáveis socioeconômicas e financeiras. O objetivo é explorar e comparar diferentes abordagens de modelagem, validação e interpretabilidade.

**Dataset:** [German Credit — OpenML ID 31](https://www.openml.org/d/31)  
**Instâncias:** 1.000 clientes  
**Features:** 20 variáveis (numéricas e categóricas)  
**Alvo:** `class` — good (1) / bad (0)

---

## 🎯 Principais Resultados

| Modelo              | AUC-ROC (K-Fold) |
|---------------------|-----------------|
| Regressão Logística | 0.7375          |

### Comparação com runs do OpenML (10-fold CV)

| Referência       | AUC-ROC |
|------------------|---------|
| Run OpenML #1    | 0.5288  |
| Run OpenML #2    | 0.7146  |
| **Este projeto** | **0.7375** |

> O modelo desenvolvido supera as duas runs verificadas no OpenML para o mesmo dataset, com AUC-ROC de **0.7375** usando Regressão Logística com pré-processamento cuidadoso.

---

## 🔍 Destaques do Projeto

- **Baseline clara**: dataset com 70/30 de desbalanceamento — acurácia mínima esperada de 70% (chute ingênuo)
- **Pré-processamento robusto**: encoding ordinal com ordem semântica + One-Hot Encoding
- **Três estratégias de validação**: Holdout 25%, K-Fold (5) e LOOCV
- **Métricas adequadas para dados desbalanceados**: AUC-ROC e F1-Score além de acurácia

---

## 📁 Estrutura do Projeto

```
.
├── Credit.ipynb      # Notebook principal com toda a análise
├── credit.arff       # Dataset (formato ARFF)
├── README.md         # Este arquivo
├── requirements.txt  # Dependências
└── .gitignore
```

---

## 🚀 Como Executar

### Pré-requisitos

- Python 3.8+
- Jupyter Notebook ou JupyterLab

### Instalação

```bash
# Clone o repositório
git clone https://github.com/SEU_USUARIO/credit-risk-classification.git
cd credit-risk-classification

# Instale as dependências
pip install -r requirements.txt

# Inicie o Jupyter
jupyter notebook Credit.ipynb
```

---

## 📦 Dependências

```
pandas
numpy
matplotlib
scipy
scikit-learn
patsy
statsmodels
```

---

## 🧠 Metodologia

### 1. Análise Exploratória
- Distribuição da variável alvo e identificação do desbalanceamento
- Definição da baseline (70% acurácia pelo chute ingênuo)

### 2. Pré-processamento
- **Variáveis ordinais**: mapeamento com ordem semântica preservada
  - Ex: `checking_status`: `no checking=0`, `<0=1`, `0<=X<200=2`, `>=200=3`
- **Variáveis nominais**: One-Hot Encoding com `drop_first=True`
- **Padronização**: StandardScaler no pipeline do sklearn

### 3. Modelagem e Validação
- Regressão Logística com `max_iter=1000`
- Três estratégias comparadas: Holdout 25%, K-Fold (5) e LOOCV
- Pipeline sklearn para evitar data leakage

### 4. Avaliação
- **AUC-ROC**: métrica principal (robusta a desbalanceamento)
- **F1-Score e Recall por classe**
- **Matrizes de confusão** para cada estratégia de validação

---

## 💡 Principais Insights

1. **`checking_status`** e **`duration`** são as features com maior correlação com risco
2. Estratificar a divisão treino/teste produz resultados mais honestos, mesmo que a acurácia pareça menor
3. AUC-ROC é mais informativo que acurácia em datasets desbalanceados

---

## 🔗 Links Relevantes

- [Dataset no OpenML](https://www.openml.org/d/31)
- [Documentação do scikit-learn](https://scikit-learn.org/stable/)

---

## 👤 Autor

**[Seu Nome]**  
📧 [seu-email@email.com]  
🔗 [LinkedIn](https://linkedin.com/in/seu-perfil)  
🐙 [GitHub](https://github.com/seu-usuario)

---

## 📄 Licença

Este projeto está licenciado sob a [MIT License](LICENSE).
