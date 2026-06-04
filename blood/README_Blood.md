# 🩸 Classificação de Doação de Sangue

Análise de Machine Learning para prever se um doador voltará a doar sangue, usando o **Blood Transfusion Service Center Dataset** (OpenML).

---

## 📋 Dataset

**Fonte:** [Blood Transfusion — OpenML ID 1464](https://www.openml.org/d/1464)  
**Instâncias:** 748 | **Features:** 4 | **Alvo:** `Class` — doou (1) / não doou (0)

| Feature | Descrição |
|---|---|
| Recency | Meses desde a última doação |
| Frequency | Total de doações |
| Volume | Total de sangue doado (ml) |
| Time | Meses desde a primeira doação |

**Baseline:** 76.2% (classe majoritária — não doou)

---

## 🎯 Resultados

| Modelo | AUC-ROC |
|---|---|
| Regressão Logística | ~0.74 |
| LDA (Stratified K-Fold) | ~0.75 |
| Naive Bayes | — |

---

## 🚀 Como Executar

```bash
pip install -r requirements.txt
jupyter notebook Blood.ipynb
```

---

## 👤 Autor

**[Seu Nome]**  
🔗 [LinkedIn](https://linkedin.com/in/seu-perfil) | 🐙 [GitHub](https://github.com/seu-usuario)
