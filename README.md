# MDI343_Data_Challenge

| Model | Feature Engineering | Voting |Score FNR+FPR rate (Valid test) | 1-(FNR+FPR) (Valid Test) |
|-----------|-----------|-----------|-----------|-----------|
| Adaboost (baseline) | Features Selection | No | 0.52 | 0.48 |
| Gradient Boosting | Features Selection | No | 0.54 | 0.46 |
| XGBoost  | Features Selection | No | 0.45 | 0.55 |
| XGBoost  | Initial features | No | 0.40 | 0.60 |
| LightGBM | Initial features | No | 0.39 | 0.61 |
| CatBoost  | Initial features | No | 0.387 | 0.613 |
| XGBoost + LightGBM + CatBoost | Initial features | Yes | 0.382 | 0.618 |
| Neural Network | Initial features | No | 0.44 | 0.56 |
