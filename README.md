# DataChallenge_Career_Parcours_IA_2026
Challenge Data Science : Prédire de manière séquentielle l'évolution d'une carrière par HrFlow.ai (https://challengedata.ens.fr/participants/challenges/151/)

  
  
### Résultats 

| Modèle | Hyperparamètres | F1-Macro |
| :--- | :--- | :---: |
| **Prédiction aléatoire** | *Baseline* | 0,2417 |
| **XGBClassifier** | Hyperparamètres par défaut | 0,2674 |
| **XGBClassifier** | `subsample=0.85`, `reg_lambda=5`, `n_estimators=300`, `min_child_weight=1`, `max_depth=4`, `learning_rate=0.03`, `colsample_bytree=0.7` | 0,2518 |
| **RandomForestClassifier** | Hyperparamètres par défaut | 0,2945 |
| **RandomForestClassifier** | **`n_estimators=100`, `min_samples_split=5`, `min_samples_leaf=4`, `max_features='sqrt'`, `max_depth=20`** | **0,3217** 🏆 |
| **RandomForestClassifier** | `n_estimators=75`, `min_samples_split=10`, `min_samples_leaf=8`, `max_features='log2'`, `max_depth=40` | 0,3066 |
| **CatBoostClassifier** | Hyperparamètres par défaut | 0,2648 |
| **CatBoostClassifier** | `learning_rate=0.03`, `l2_leaf_reg=1`, `iterations=400`, `grow_policy='SymmetricTree'`, `depth=8`, `bagging_temperature=1.0` | 0,2864 |
| **MLPClassifier** | Hyperparamètres par défaut | 0,2442 |
| **MLPClassifier** | `early_stopping=True`, `max_iter=300`, `learning_rate_init=0.005`, `learning_rate='constant'`, `hidden_layer_sizes=(64, 32)`, `batch_size=128`, `alpha=0.1`, `activation='tanh'` | 0,2493 |
| **Méthode d'ensemble** | Soft Voting (`XGBClassifier`, `RandomForestClassifier`, `CatBoostClassifier`) | 0,2917 |