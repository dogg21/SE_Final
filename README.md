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

員工表(Staff):
| 屬性名  | 含意 | 類型 | 說明 |
| --- | --- | --- | --- |
| Snum  | 員工編號 | varchar | 主鍵 |
| Sname  | 員工姓名 | varchar | |
| Ssex  | 員工性別 | varchar | '男' or '女' |
| Sage  | 員工年齡 | int | Sage >= 18 |
| Sstand  | 員工工齡 | int |  |
| Sphone  | 員工電話 | varchar |  |
| Sid  | 員工身分字號 | varchar |  |
| Spart  | 員工所屬部門 | varchar |  |
| Ssalary  | 員工工資 | money | Ssalary >= 0 |

商品表(Goods):
| 屬性名  | 含意 | 類型 | 說明 |
| --- | --- | --- | --- |
| Gnum | 商品編號 | varchar | 主鍵 |
| Gname | 商品名稱 | varchar | |
| Gtype | 商品類別 | varchar | |
| Gprice | 商品售價 | money | Gprice >= 0 |
| Gbid | 商品進價 | money | Gbid >= 0 |
| Gstock | 庫存量 | int | Gstock >= 0 |
| Galarm | 警告量 | int | Galarm >= 0 |
| Gplan | 計畫庫存量 | int | Gplan >= 0 |
| Vnum | 進貨商編號 | varchar | 是表Vendor外鍵 |

會員表(Menber):
| 屬性名  | 含意 | 類型 | 說明 |
| --- | --- | --- | --- |
| Mnum | 會員卡號 | varchar | 主鍵 |
| Mname | 會員姓名 | varchar | |
| Mphone | 會員電話 | varchar | |
| Mdate | 註冊日期 | datatime | |
| Mtotal | 累計金額 | money | Mtotal >= 0 |
| Mbalance | 卡內餘額 | money | Mbalance >= 0 |
| Mcip | 會員密碼 | varchar |  |

供貨商(Vendor):
| 屬性名  | 含意 | 類型 | 說明 |
| --- | --- | --- | --- |
| Vnum | 供貨商編號 | varchar | 主鍵 |
| Vname | 供貨商名稱 | varchar | |
| Vphone | 供貨商電話 | varchar | |
| Vplace | 供貨商地址 | varchar | |

倉庫(Ware):
| 屬性名  | 含意 | 類型 | 說明 |
| --- | --- | --- | --- |
| Wnum | 倉庫編號 | varchar | 主鍵 |
| Wname | 倉庫名稱 | varchar | |
| Wplace | 倉庫地址 | varchar | |

退貨訊息(Infor):
| 屬性名  | 含意 | 類型 | 說明 |
| --- | --- | --- | --- |
| Tnum | 交易單號 | varchar | 是表Trade的外鍵 |
| Gnum | 商品編號 | varchar | 是表Goods的外鍵 |
| Iamount | 退貨數量 | int | Iamount >= 0 |
| Imoney | 退款金額 | money | Imoney >= 0 |
| Idate | 退款日期 | datetime |  |

商品交易表(Trade):
| 屬性名  | 含意 | 類型 | 說明 |
| --- | --- | --- | --- |
| Tnum | 交易單號 | varchar | 主鍵 |
| Tdate | 交易日期 | datetime | |
| Snum | 員工編號 | varchar | 是表Staff的外鍵 |
| Gnum | 商品編號 | varchar | Tmoney |
| Tamount | 交易數量 | int | Tamount >= 0 |
| Tmoney | 交易金額 | money | Tmoney >= 0 |
| Mnum | 會員卡號 | varchar | 是表Menber的外鍵 |

進貨訊息表(Entry):
| 屬性名  | 含意 | 類型 | 說明 |
| --- | --- | --- | --- |
| Enum | 進貨單編號 | varchar | 主鍵 |
| Gnum | 商品編號 | varchar | 是表Goods的外鍵 |
| Eamount | 進貨量 | int | Eamount >= 0 |
| Emoney | 總金額 | money | Emoney >= 0 |
| Vnum | 供貨商編號 | varchar | 是表Vendor的外鍵 |
| Edate | 進貨日期 | datetime |  |
| Snum | 進貨員編號 | varchar | 是表Staff的外鍵 |

出貨訊息表(Exits):
| 屬性名  | 含意 | 類型 | 說明 |
| --- | --- | --- | --- |
| Xnum | 出貨單編號 | varchar | 主鍵 |
| Gnum | 商品編號 | varchar | 是表Goods的外鍵 |
| Xamount | 出貨量 | int | Xamount >= 0 |
| Xmoney | 總金額 | money | Xmoney >= 0 |
| Xdate | 出貨日期 | datetime |  |
| Snum | 出貨員編號 | varchar | 是表Staff的外鍵 |

## 四.代碼實現
### 1.實現Python 連接 SQL Severe 資料庫
'''
import pymssql  #引入pymssql模块

def conn():
    connect = pymssql.connect(host = "127.0.0.1:1433",database = "Manager",charset="utf8")  
    if connect:
        print("連接成功!")
    return connect

if __name__ == '__main__':
    conn = conn()
'''

