# 🧪 Predição de Solubilidade Aquosa com Descritores Moleculares

Aplicação de Machine Learning para prever a solubilidade aquosa (logS) de compostos orgânicos a partir de descritores moleculares calculados com RDKit.

---

## 📋 Dataset

**Fonte:** [AqSolDB — Harvard Dataverse](https://doi.org/10.7910/DVN/OVHAW8)  
**Instâncias:** 9.982 compostos | **Target:** `Solubility` (logS)  
**Descritores:** 13 features moleculares + 1 combinada (RingFeatures)

---

## 🎯 Resultados

| Modelo | R² | MAE | RMSE |
|---|---|---|---|
| Regressão Linear | 0.5187 | 1.2476 | 1.6810 |
| Ridge | 0.5178 | 1.2561 | 1.6826 |
| Gradient Boosting | 0.6873 | 0.9678 | 1.3550 |
| XGBoost | 0.6890 | 0.9462 | 1.3514 |
| **Random Forest** | **0.7602** | **0.7968** | **1.1866** |

> **Modelo final:** Random Forest com `descriptor_columns_v2` (14 features)

---

## 🔍 Destaques do Projeto

- **Download automatizado** dos dados via API do Harvard Dataverse
- **RDKit** para conversão de SMILES e cálculo de descritores moleculares
- **Engenharia de features**: variáveis de anéis (aromáticos, saturados, alifáticos e RingCount) combinadas em `RingFeatures`, reduzindo dimensionalidade sem perda de performance
- **Comparação de 5 modelos**: de regressão linear a modelos ensemble
- **Interpretabilidade**: MolLogP domina com ~65% de importância — coerente com a relação entre lipofilia e solubilidade aquosa descrita por Hansch e Leo (1979)

---

## 🧠 Interpretação Química

O MolLogP (coeficiente de partição octanol-água) se destaca como principal preditor, capturando a relação inversa entre lipofilia e solubilidade — princípio fundamental em físico-química orgânica. O BertzCT aparece como segundo descritor mais relevante, possivelmente refletindo o efeito da complexidade estrutural sobre os dipolos moleculares e a interação com o solvente.

---

## 🚀 Como Executar

```bash
pip install -r requirements.txt
jupyter notebook Chem_LR.ipynb
```

> O notebook faz o download automático do dataset na primeira execução.

---

## 📦 Dependências

```
pandas
numpy
matplotlib
seaborn
scipy
scikit-learn
rdkit
xgboost
requests
```

---

## 👤 Autor

**[Artur Amasai Melo dos Santos]**  

