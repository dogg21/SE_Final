# 超市零售信息管理系统
## 1.需求分析
### 一.設計概念
這個超市零售管理資訊系統旨在為超市的會員管理工作提供一個比較系統的零售管理平台，它幫助超市存儲及管理進貨、銷售、庫存以及人員信息，是一套管理工具、極大提高超市管理的 效率。 很大程度上幫助了超市管理者對超市的掌握與管理。
### 二.功能說明
1. 進貨管理:依銷售狀況及庫存情況，自動制定進貨計畫（亦可手動制定修改），可避免盲目進貨造成商品積壓。 依計劃單有選擇性地進行自動入庫登記。 綜合查詢列印計畫進貨與入庫
記錄及金額。
2. 銷售管理:商品正常銷售、促銷與限量、限期及禁止銷售管制。 綜合查詢各種銷售明細記錄、各地收銀員收銀記錄以及交結帳情況等。 以多種方式統計產生銷售排行榜，靈活察看並列印商品銷售日、月、年報表。
4. 庫存管理:綜合查詢庫存明細記錄。 庫存狀態自動警告提示。 如庫存過剩、少貨、缺貨等。 軟體為您預警，避免庫存商品積壓損失和缺貨。
5. 人員管理:員工、會員、供貨商、廠商等基本資料登記管理。 員工操作權限管理。 客戶銷售權限管理。
### 三.功能模組圖
![image](https://github.com/dogg21/SE_Final/blob/main/image/functions.png)
### 四.業務流程圖
![image](https://github.com/dogg21/SE_Final/blob/main/image/flow.png)
## 2.概念結構設計
### 一.實體描述
該超市資訊管理系統的抽象實體有六個:
1. 員工實體屬性：員工編號，姓名，性別，年齡，職務，入職日期
2. 庫存實體屬性：庫存編號，商品編號，商品名稱，商品價格，庫存商品數量，倉庫編號，商品入庫時間，商品出庫時間，商品出庫數量
3. 倉庫實體屬性：倉庫編號，倉庫姓名
4. 商品實體屬性：商品編號，名稱，價格，商品類型
5. 商品類型實體屬性：商品類型編號，類型名稱，商品注意事項
6. 供應商實體屬性：供應商編號，姓名，電話，位址
### 二.局部E-R圖
員工:

![image](https://github.com/dogg21/SE_Final/blob/main/image/staff.png)

商品:

![image](https://github.com/dogg21/SE_Final/blob/main/image/goods.png)

會員:

![image](https://github.com/dogg21/SE_Final/blob/main/image/menber.png)

供貨商:

![image](https://github.com/dogg21/SE_Final/blob/main/image/vendor.png)

倉庫:

![image](https://github.com/dogg21/SE_Final/blob/main/image/store.png)

### 三.全域E-R圖
![image](https://github.com/dogg21/SE_Final/blob/main/image/all.png)

## 3.邏輯結構設計

| 屬性名  | 含意 | 類型 | 說明 |
| --------|----- | -------|------ |
| Snum  | 員工編號  | varchar | 主鍵|


