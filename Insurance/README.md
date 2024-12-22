# XGBoost + BayesSearchCV 預測模型

本專案使用 XGBoost 進行回歸分析，並結合 `BayesSearchCV` 進行超參數調優，最終選擇最佳的模型配置來預測目標變數。預測的目標是基於 `insurance.csv` 數據集。

## 目錄

- [安裝依賴](#安裝依賴)
- [數據集說明](#數據集說明)
- [數據預處理](#數據預處理)
- [訓練 XGBoost 模型](#訓練-xgboost-模型)
- [使用 BayesSearchCV 進行超參數調優](#使用-bayessearchcv-進行超參數調優)
- [評估模型](#評估模型)

## 安裝依賴

請確保你的 Python 環境中已安裝以下庫：

```bash
pip install -r requirements.txt
```

## 數據集說明

保險相關數據集，包含了多個特徵以及目標變數。我們的目標是預測保險費用。
- train.csv : 訓練集
- test.csv  : 測試集(沒有目標變數)
- submission.csv : 數據關於測試的預測結果

## 數據預處理

- datetime transfer
- filling missing value
- Label Encoding 
- Normalization

## 訓練 XGBoost 模型

XGBoost 是一個高效且強大的回歸模型。此模型在訓練過程中使用了 L1 和 L2 正則化來防止過擬合。你可以根據需要調整超參數來達到更好的預測效果。

## 使用 BayesSearchCV 進行超參數調優

BayesSearchCV 用於進行超參數的優化，通過基於過去的搜索結果來推斷未來應該選擇哪些超參數配置。這有助於找到最佳的參數組合以提高模型性能。

在本專案中，搜索的目標指標是 neg_mean_squared_error，這表示我們希望最小化均方誤差（MSE），以提高預測準確性。


## 評估模型

在訓練和調優過程完成後，我們使用不同的圖表和評估指標來評估模型的性能。這些指標包括：

- 散點圖：顯示真實值與預測值之間的對比。
- 直方圖：顯示預測結果的分佈，並幫助我們了解模型的預測誤差。



