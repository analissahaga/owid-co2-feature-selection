# owid-co2-feature-selection
Feature selection using SHAP, ANOVA, MI and RFE on OWID CO2 data
# OWID CO2 Feature Selection

Reprodução da metodologia de **Marcílio & Eler (2020)** aplicada aos dados de emissões de CO₂ do Our World in Data.

## Artigo de Referência

Marcílio-Jr, W. E., & Eler, D. M. (2020). *From explanations to feature selection: assessing SHAP values as feature selection mechanism*. In 2020 33rd SIBGRAPI Conference on Graphics, Patterns and Images (SIBGRAPI) (pp. 340-347). IEEE.

## Metodologia

Este projeto implementa os 4 métodos de seleção de features descritos no artigo:

1. **TreeSHAP** - Método embutido baseado em valores SHAP
2. **ANOVA** - Método de filtro univariado (F-test)
3. **Mutual Information** - Método de filtro univariado (dependência mútua)
4. **RFE** - Método envolvente (Recursive Feature Elimination)

### Protocolo de Avaliação

- **Keep Absolute**: Mantém d% das features mais importantes (10% a 100%)
- **Validação**: 5-fold cross-validation
- **Modelo**: XGBoost
- **Métricas**: 
  - Classificação: F1-score macro
  - Regressão: MSE negativo
- **Resultado final**: AUC das curvas de desempenho

## Dataset

[OWID CO2 Data](https://github.com/owid/co2-data) - Dados completos de emissões de CO₂ e gases de efeito estufa por país.

## Instalação

```bash
pip install -r requirements.txt
