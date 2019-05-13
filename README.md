# DSAI_HW3

首先看完資料集後，發現資料並沒有很乾淨，要建造模型必須要清洗資料成自己喜歡的樣子。

先分析離群值，有些離群值是不合理的，有可能是手誤造成數據錯誤，例如售價小於0元。此時以其他相同特徵當作參考，取其中的中位數當作清洗後的數值，這邊如果用K-NN應該會更加優秀，因為如果只是填補平均值，等於損失掉一筆資料，如同直接剔除掉，而用K-NN則會讓這筆資料有價值。

再來因為資料的標籤不正確，商店名稱同時會擁有城市名稱，所以必須更改成正確的，商品的種類一樣有此問題。

測試資料集與訓練資料集有些許的名稱無法對稱，測試資料集比訓練資料還多了363項新的資料，這也是必須要做處裡的。

待特徵資料處裡完後，分離一部分資料來做測試資料集。在這邊因為認為是回歸的模式，所以使用xgboost演算法來進行預測。
