# 超市零售信息管理系统
* [一.需求分析](https://github.com/dogg21/SE_Final#1%E9%9C%80%E6%B1%82%E5%88%86%E6%9E%90)
    * [1.設計概念](https://github.com/dogg21/SE_Final#%E4%B8%80%E8%A8%AD%E8%A8%88%E6%A6%82%E5%BF%B5)
    * [2.功能說明](https://github.com/dogg21/SE_Final#%E4%BA%8C%E5%8A%9F%E8%83%BD%E8%AA%AA%E6%98%8E)
    * [3.功能模組圖](https://github.com/dogg21/SE_Final#%E4%B8%89%E5%8A%9F%E8%83%BD%E6%A8%A1%E7%B5%84%E5%9C%96)
    * [4.業務流程圖](https://github.com/dogg21/SE_Final#%E5%9B%9B%E6%A5%AD%E5%8B%99%E6%B5%81%E7%A8%8B%E5%9C%96)
* [二.概念結構設計](https://github.com/dogg21/SE_Final#2%E6%A6%82%E5%BF%B5%E7%B5%90%E6%A7%8B%E8%A8%AD%E8%A8%88)
   * [1.實體描述](https://github.com/dogg21/SE_Final#%E4%B8%80%E5%AF%A6%E9%AB%94%E6%8F%8F%E8%BF%B0)
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
```
import pymssql  #引入pymssql模組

def conn():
    connect = pymssql.connect(host = "localhost",database = "Manager",charset="utf8")  
    if connect:
        print("連接成功!")
    return connect

if __name__ == '__main__':
    conn = conn()
```
### 2.創建資料庫表
資料庫中表的創建可以直接在SQLServer中手動建表，也可以通過Python程式進行建表，其語法規則和SQL一樣，代碼如下：
```
import pymssql

connect = pymssql.connect(host = "127.0.0.1:1433",database = "Manager",charset="utf8")  # 建立连接
if connect:
    print("连接成功!")

cursor = connect.cursor()   # 创建一个游标对象,python里的sql语句都要通过cursor来执行
cursor.execute("create table Staff(Snum  varchar(10) primary key,Sname varchar(20) not null,Ssex varchar(5) check(Ssex in('男','女')),Sage int not null check(Sage>=18),Sstand int not null check(Sstand>=0),Sphone varchar(20) not null,Sid varchar(25) not null,Spart varchar(10) not null,Ssalary money check(Ssalary>=0))")
cursor.execute("create table Vendor(Vnum varchar(10) primary key,Vname varchar(10) not null,Vphone varchar(20) not null,Vpalce varchar(10) not null)")
cursor.execute("create table Goods(Gnum varchar(10) primary key,Gname varchar(10) not null,Gtype varchar(10) not null,Gprice money check(Gprice>=0),Gbid money check(Gbid>=0),Gstock int check(Gstock>=0),Galarm int check(Galarm>=0), Gplan int check(Gplan>=0),Vnum varchar(10) not null,foreign key(Vnum) references Vendor(Vnum))")
cursor.execute("create table Menber(Mnum varchar(10) primary key,Mname varchar(10) not null,Mphone varchar(20) not null,Mdate datetime,Mtotal money check(Mtotal>=0),Mbalance money check(Mbalance>=0),Mcip varchar(25) not null)")
cursor.execute("create table Ware(Wnum varchar(10) primary key,Wname varchar(10) not null,Wplace varchar(10) not null)")
cursor.execute("create table Trade(Tnum varchar(10) primary key,Tdate datetime  not null,Snum varchar(10) not null,Gnum varchar(10) not null,Tamount int check(Tamount>=0),Tmoney money check(Tmoney>=0),Mnum varchar(10) not null,foreign key(Snum) references Staff(Snum),foreign key(Gnum) references Goods(Gnum),foreign key(Mnum) references Menber(Mnum))")
cursor.execute("create table Infor(Tnum varchar(10) not null,Gnum varchar(10) not null,Iamount int check(Iamount>=0),Imoney money check(Imoney>=0),Idate datetime not null,foreign key(Tnum) references Trade(Tnum),foreign key(Gnum) references Goods(Gnum))")
cursor.execute("create table Entry(Enum varchar(10) primary key,Gnum varchar(10) not null,Eamount int check(Eamount>=0),Emoney money check(Emoney>=0),Vnum varchar(10) not null,Edate datetime not null,Snum varchar(10) not null,foreign key(Snum) references Staff(Snum),foreign key(Gnum) references Goods(Gnum),foreign key(Vnum) references Vendor(Vnum))")
cursor.execute("create table Exits(Xnum varchar(10) primary key,Gnum varchar(10) not null,Xamount int check(Xamount>=0),Xmoney money check(Xmoney>=0),Xdate datetime not null,Snum varchar(10) not null,foreign key(Snum) references Staff(Snum),foreign key(Gnum) references Goods(Gnum))")
connect.commit()  #提交
cursor.close()  # 关闭游标
connect.close()  # 关闭连接
```
### 3.插入數據
在Goods表中批量插入資料:
```
import pymssql

connect = pymssql.connect(host = "127.0.0.1:1433",database = "Manager",charset="utf8")
if connect:
    print("连接成功!")

cursor = connect.cursor()  # 创建一个游标对象,python里的sql语句都要通过cursor来执行
sql = "insert into Goods(Gnum,Gname,Gtype,Gprice,Gbid,Gstock,Galarm,Gplan,Vnum) values ('200001','薯片','零食',8,5,500,100,600,'100002')"
sql = "insert into Goods(Gnum,Gname,Gtype,Gprice,Gbid,Gstock,Galarm,Gplan,Vnum) values ('200002','可乐','饮料',4,2,1000,200,1500,'100001')"
sql = "insert into Goods(Gnum,Gname,Gtype,Gprice,Gbid,Gstock,Galarm,Gplan,Vnum) values ('200003','猪肉','肉类',32,20,400,50,500,'100003')"
cursor.execute(sql)
connect.commit()  # 提交
cursor.close()
connect.close()
```
在Vendor表中批量插入資料：
```
import pymssql
import tkinter as tk
import tkinter.messagebox

#数据库添加操作
def add():
    # 连接数据库
    connect = pymssql.connect(host = "127.0.0.1:1433",database = "Manager",charset="utf8")
    # 创建光标
    cursor = connect.cursor()
    # 编写SQL语句
    sql = "insert into Goods(Gnum,Gname,Gtype,Gprice,Gbid,Gstock,Galarm,Gplan,Vnum) values('%s','%s','%s','%s','%s','%s','%s','%s',%s)" % (v1.get(), v2.get(), v3.get(), v4.get(), v5.get(), v6.get(), v7.get(), v8.get(), v9.get())
    # 执行SQL语句，并且输出完成提示信息，否则回滚
    try:
        cursor.execute(sql)
        connect.commit()
        tkinter.messagebox.showinfo("提示", "数据添加成功")
    except:
        connect.rollback()
    # 关闭数据库连接，防止泄露
    connect.close()

#数据库删除操作
def delete():
    connect = pymssql.connect(host = "127.0.0.1:1433",database = "Manager",charset="utf8")
    cursor=connect.cursor()
    sql = "delete from Goods where Gnum='%s'" % (v10.get())
    try:
        cursor.execute(sql)
        connect.commit()
        tkinter.messagebox.showinfo("提示","数据删除成功")
    except:
        connect.rollback()
    connect.close()

#数据库更新操作
def update():
    connect = pymssql.connect(host = "127.0.0.1:1433",database = "Manager",charset="utf8")
    cursor = connect.cursor()
    sql="update Goods set Gstock='%s' where Gnum='%s'"%(v11.get(),v12.get())
    try:
        cursor.execute(sql)
        connect.commit()
        tkinter.messagebox.showinfo("提示","数据更新成功！")
    except:
        connect.rollback()
    connect.close()

#数据库模糊条件查询
def select():
    connect = pymssql.connect(host = "127.0.0.1:1433",database = "Manager",charset="utf8")
    cursor = connect.cursor()
    sql = "select Vname from Vendor,Goods where Goods.Vnum=Vendor.Vnum and Goods.Gnum like'%s'"%('%'+v13.get()+'%')
    try:
        cursor.execute(sql)
        results = cursor.fetchall()
        for row in results:
            Vname = row[0]
            tkinter.messagebox.showinfo("提示","Vname=%s" % (Vname))
    except:
        return

#添加商品界面
def Staff_add():
    #构建全集变量，方便上面的函数调用
    global window_function
    global v1,v2,v3,v4,v5,v6,v7,v8,v9
    #生成窗口
    window_function=tk.Tk()
    #窗口标题
    window_function.title("超市零售信息管理系统")
    #窗口大小
    window_function.geometry('400x700')
    #生成标签
    tk.Label(window_function, text="添加新商品", font=("黑体", 20)).grid(row=0,column=1,pady=10)
    tk.Label(window_function, text="请输入商品编号：").grid(row=1, column=0, padx=20, pady=20)
    tk.Label(window_function,text="请输入商品名称：").grid(row = 2,column =0,padx=20,pady=20)
    tk.Label(window_function,text="请输入商品类别：").grid(row = 3,column =0,padx=20,pady=20)
    tk.Label(window_function,text="请输入商品售价：").grid(row = 4,column =0,padx=20,pady=20)
    tk.Label(window_function, text="请输入商品成本：").grid(row=5, column=0, padx=20, pady=20)
    tk.Label(window_function, text="请输入库存量：").grid(row=6, column=0, padx=20, pady=20)
    tk.Label(window_function, text="请输入告警量：").grid(row=7, column=0, padx=20, pady=20)
    tk.Label(window_function, text="请输入计划库存量：").grid(row=8, column=0, padx=20, pady=20)
    tk.Label(window_function, text="请输入供货商编号：").grid(row=9, column=0, padx=20, pady=20)
    #定义变量记录输入信息
    v1 = tk.StringVar()
    v2 = tk.StringVar()
    v3 = tk.StringVar()
    v4 = tk.StringVar()
    v5 = tk.StringVar()
    v6 = tk.StringVar()
    v7 = tk.StringVar()
    v8 = tk.StringVar()
    v9 = tk.StringVar()
    #生成输入框
    entry1 = tk.Entry(window_function,show=None,textvariable=v1).grid(row = 1,column =1)
    entry2 = tk.Entry(window_function,show=None,textvariable=v2).grid(row = 2,column =1)
    entry3 = tk.Entry(window_function,show=None,textvariable=v3).grid(row = 3,column =1)
    entry4 = tk.Entry(window_function, show=None, textvariable=v4).grid(row=4, column=1)
    entry5 = tk.Entry(window_function, show=None, textvariable=v5).grid(row=5, column=1)
    entry6 = tk.Entry(window_function, show=None, textvariable=v6).grid(row=6, column=1)
    entry7 = tk.Entry(window_function, show=None, textvariable=v7).grid(row=7, column=1)
    entry8 = tk.Entry(window_function, show=None, textvariable=v8).grid(row=8, column=1)
    entry9 = tk.Entry(window_function, show=None, textvariable=v9).grid(row=9, column=1)
    #生成按钮
    button = tk.Button(window_function, text="添加", command=add).place(relx=0.3,rely=0.9)

    button2 = tk.Button(window_function, text="返回", command=chaneg_main).place(relx=0.5,rely=0.9)
    #显示窗口
    window_function.mainloop()

#删除商品界面
def Staff_delete():
    global window_function
    global v10
    window_function=tk.Tk()
    window_function.title("超市零售信息管理系统")
    window_function.geometry('500x400')
    tk.Label(window_function, text="删除商品", font=("黑体", 20)).grid(row=0,column=1,pady=20)
    tk.Label(window_function,text="请输入商品编号：").grid(row = 1,column =0,padx=20)
    v10 =tk.StringVar()
    entry1=tk.Entry(window_function,show=None,textvariable=v10).grid(row = 1,column =1,pady=40)
    button = tk.Button(window_function, text="删除", command=delete,anchor = 's').place(relx=0.2,rely=0.5)
    button2 = tk.Button(window_function, text="返回", command=chaneg_main).place(relx=0.4,rely=0.5)
    window_function.mainloop()

#更新商品信息界面
def Staff_update():
    global window_function
    global v11,v12
    window_function=tk.Tk()
    window_function.title("超市零售信息管理系统")
    window_function.geometry('500x400')
    tk.Label(window_function, text="更新商品信息", font=("黑体", 20)).grid(row=0,column=1,pady=20)
    tk.Label(window_function,text="请输入商品库存：").grid(row = 1,column =0,padx=20,pady=20)
    tk.Label(window_function,text="请输入商品编号：").grid(row = 2,column =0,padx=20,pady=20)
    v11=tk.StringVar()
    v12=tk.StringVar()
    entry1=tk.Entry(window_function,show=None,textvariable=v11).grid(row = 1,column =1)
    entry2=tk.Entry(window_function,show=None,textvariable=v12).grid(row = 2,column =1)
    button = tk.Button(window_function, text="更新", command=update).place(relx=0.3,rely=0.5)
    button2 = tk.Button(window_function, text="返回", command=chaneg_main).place(relx=0.5,rely=0.5)
    window_function.mainloop()

#条件查找商品界面
def Staff_select():
    global window_function
    global v13
    window_function=tk.Tk()
    window_function.title("超市零售信息管理系统")
    window_function.geometry('500x400')
    tk.Label(window_function, text="查找商品的供货商名称", font=("黑体", 20)).grid(row=0,column=1,pady=20)
    tk.Label(window_function,text="请输入商品编号：").grid(row = 1,column =0,padx=20)
    v13 =tk.StringVar()
    entry1=tk.Entry(window_function,show=None,textvariable=v13).grid(row = 1,column =1,pady=40)
    button = tk.Button(window_function, text="查找", command=select).place(relx=0.3,rely=0.5)
    button2 = tk.Button(window_function, text="返回", command=chaneg_main).place(relx=0.5,rely=0.5)
    window_function.mainloop()

#添加商品界面跳转
def change_add():
    #销毁画布
    window.destroy()
    #生成新界面
    Staff_add()

#删除商品界面跳转
def change_delete():
    window.destroy()
    Staff_delete()

#更新商品界面跳转
def change_update():
    window.destroy()
    Staff_update()

#条件查询商品界面跳转
def change_select():
    window.destroy()
    Staff_select()

#主界面跳转
def chaneg_main():
    window_function.destroy()
    mainpage()

#主界面
def mainpage():
    global window
    window = tk.Tk()
    window.title("超市零售信息管理系统")
    window.geometry('500x400')
    #生成画布，销毁后生成新的画布实现跳转
    page = tk.Frame(window)
    page.pack()
    tk.Label(window, text="欢迎使用超市零售信息管理系统", font=("黑体", 20)).pack(pady=10)
    button1 = tk.Button(window, text="添加商品信息", command=change_add).pack(pady=10)
    button2 = tk.Button(window, text="删除商品信息", command=change_delete).pack(pady=10)
    button3 = tk.Button(window, text="修改商品信息", command=change_update).pack(pady=10)
    button4 = tk.Button(window, text="查找商品供货商名称", command=change_select).pack(pady=10)
    window.mainloop()

#主函数生成主界面
if __name__ == '__main__':
    mainpage()
```
### 4.創建介面按鈕，並實現資料庫的“增刪改查”
```
import pymssql
import tkinter as tk
import tkinter.messagebox

#数据库添加操作
def add():
    # 连接数据库
    connect = pymssql.connect(host = "127.0.0.1:1433",database = "Manager",charset="utf8")
    # 创建光标
    cursor = connect.cursor()
    # 编写SQL语句
    sql = "insert into Goods(Gnum,Gname,Gtype,Gprice,Gbid,Gstock,Galarm,Gplan,Vnum) values('%s','%s','%s','%s','%s','%s','%s','%s',%s)" % (v1.get(), v2.get(), v3.get(), v4.get(), v5.get(), v6.get(), v7.get(), v8.get(), v9.get())
    # 执行SQL语句，并且输出完成提示信息，否则回滚
    try:
        cursor.execute(sql)
        connect.commit()
        tkinter.messagebox.showinfo("提示", "数据添加成功")
    except:
        connect.rollback()
    # 关闭数据库连接，防止泄露
    connect.close()

#数据库删除操作
def delete():
    connect = pymssql.connect(host = "127.0.0.1:1433",database = "Manager",charset="utf8")
    cursor=connect.cursor()
    sql = "delete from Goods where Gnum='%s'" % (v10.get())
    try:
        cursor.execute(sql)
        connect.commit()
        tkinter.messagebox.showinfo("提示","数据删除成功")
    except:
        connect.rollback()
    connect.close()

#数据库更新操作
def update():
    connect = pymssql.connect(host = "127.0.0.1:1433",database = "Manager",charset="utf8")
    cursor = connect.cursor()
    sql="update Goods set Gstock='%s' where Gnum='%s'"%(v11.get(),v12.get())
    try:
        cursor.execute(sql)
        connect.commit()
        tkinter.messagebox.showinfo("提示","数据更新成功！")
    except:
        connect.rollback()
    connect.close()

#数据库模糊条件查询
def select():
    connect = pymssql.connect(host = "127.0.0.1:1433",database = "Manager",charset="utf8")
    cursor = connect.cursor()
    sql = "select Vname from Vendor,Goods where Goods.Vnum=Vendor.Vnum and Goods.Gnum like'%s'"%('%'+v13.get()+'%')
    try:
        cursor.execute(sql)
        results = cursor.fetchall()
        for row in results:
            Vname = row[0]
            tkinter.messagebox.showinfo("提示","Vname=%s" % (Vname))
    except:
        return

#添加商品界面
def Staff_add():
    #构建全集变量，方便上面的函数调用
    global window_function
    global v1,v2,v3,v4,v5,v6,v7,v8,v9
    #生成窗口
    window_function=tk.Tk()
    #窗口标题
    window_function.title("超市零售信息管理系统")
    #窗口大小
    window_function.geometry('400x700')
    #生成标签
    tk.Label(window_function, text="添加新商品", font=("黑体", 20)).grid(row=0,column=1,pady=10)
    tk.Label(window_function, text="请输入商品编号：").grid(row=1, column=0, padx=20, pady=20)
    tk.Label(window_function,text="请输入商品名称：").grid(row = 2,column =0,padx=20,pady=20)
    tk.Label(window_function,text="请输入商品类别：").grid(row = 3,column =0,padx=20,pady=20)
    tk.Label(window_function,text="请输入商品售价：").grid(row = 4,column =0,padx=20,pady=20)
    tk.Label(window_function, text="请输入商品成本：").grid(row=5, column=0, padx=20, pady=20)
    tk.Label(window_function, text="请输入库存量：").grid(row=6, column=0, padx=20, pady=20)
    tk.Label(window_function, text="请输入告警量：").grid(row=7, column=0, padx=20, pady=20)
    tk.Label(window_function, text="请输入计划库存量：").grid(row=8, column=0, padx=20, pady=20)
    tk.Label(window_function, text="请输入供货商编号：").grid(row=9, column=0, padx=20, pady=20)
    #定义变量记录输入信息
    v1 = tk.StringVar()
    v2 = tk.StringVar()
    v3 = tk.StringVar()
    v4 = tk.StringVar()
    v5 = tk.StringVar()
    v6 = tk.StringVar()
    v7 = tk.StringVar()
    v8 = tk.StringVar()
    v9 = tk.StringVar()
    #生成输入框
    entry1 = tk.Entry(window_function,show=None,textvariable=v1).grid(row = 1,column =1)
    entry2 = tk.Entry(window_function,show=None,textvariable=v2).grid(row = 2,column =1)
    entry3 = tk.Entry(window_function,show=None,textvariable=v3).grid(row = 3,column =1)
    entry4 = tk.Entry(window_function, show=None, textvariable=v4).grid(row=4, column=1)
    entry5 = tk.Entry(window_function, show=None, textvariable=v5).grid(row=5, column=1)
    entry6 = tk.Entry(window_function, show=None, textvariable=v6).grid(row=6, column=1)
    entry7 = tk.Entry(window_function, show=None, textvariable=v7).grid(row=7, column=1)
    entry8 = tk.Entry(window_function, show=None, textvariable=v8).grid(row=8, column=1)
    entry9 = tk.Entry(window_function, show=None, textvariable=v9).grid(row=9, column=1)
    #生成按钮
    button = tk.Button(window_function, text="添加", command=add).place(relx=0.3,rely=0.9)

    button2 = tk.Button(window_function, text="返回", command=chaneg_main).place(relx=0.5,rely=0.9)
    #显示窗口
    window_function.mainloop()

#删除商品界面
def Staff_delete():
    global window_function
    global v10
    window_function=tk.Tk()
    window_function.title("超市零售信息管理系统")
    window_function.geometry('500x400')
    tk.Label(window_function, text="删除商品", font=("黑体", 20)).grid(row=0,column=1,pady=20)
    tk.Label(window_function,text="请输入商品编号：").grid(row = 1,column =0,padx=20)
    v10 =tk.StringVar()
    entry1=tk.Entry(window_function,show=None,textvariable=v10).grid(row = 1,column =1,pady=40)
    button = tk.Button(window_function, text="删除", command=delete,anchor = 's').place(relx=0.2,rely=0.5)
    button2 = tk.Button(window_function, text="返回", command=chaneg_main).place(relx=0.4,rely=0.5)
    window_function.mainloop()

#更新商品信息界面
def Staff_update():
    global window_function
    global v11,v12
    window_function=tk.Tk()
    window_function.title("超市零售信息管理系统")
    window_function.geometry('500x400')
    tk.Label(window_function, text="更新商品信息", font=("黑体", 20)).grid(row=0,column=1,pady=20)
    tk.Label(window_function,text="请输入商品库存：").grid(row = 1,column =0,padx=20,pady=20)
    tk.Label(window_function,text="请输入商品编号：").grid(row = 2,column =0,padx=20,pady=20)
    v11=tk.StringVar()
    v12=tk.StringVar()
    entry1=tk.Entry(window_function,show=None,textvariable=v11).grid(row = 1,column =1)
    entry2=tk.Entry(window_function,show=None,textvariable=v12).grid(row = 2,column =1)
    button = tk.Button(window_function, text="更新", command=update).place(relx=0.3,rely=0.5)
    button2 = tk.Button(window_function, text="返回", command=chaneg_main).place(relx=0.5,rely=0.5)
    window_function.mainloop()

#条件查找商品界面
def Staff_select():
    global window_function
    global v13
    window_function=tk.Tk()
    window_function.title("超市零售信息管理系统")
    window_function.geometry('500x400')
    tk.Label(window_function, text="查找商品的供货商名称", font=("黑体", 20)).grid(row=0,column=1,pady=20)
    tk.Label(window_function,text="请输入商品编号：").grid(row = 1,column =0,padx=20)
    v13 =tk.StringVar()
    entry1=tk.Entry(window_function,show=None,textvariable=v13).grid(row = 1,column =1,pady=40)
    button = tk.Button(window_function, text="查找", command=select).place(relx=0.3,rely=0.5)
    button2 = tk.Button(window_function, text="返回", command=chaneg_main).place(relx=0.5,rely=0.5)
    window_function.mainloop()

#添加商品界面跳转
def change_add():
    #销毁画布
    window.destroy()
    #生成新界面
    Staff_add()

#删除商品界面跳转
def change_delete():
    window.destroy()
    Staff_delete()

#更新商品界面跳转
def change_update():
    window.destroy()
    Staff_update()

#条件查询商品界面跳转
def change_select():
    window.destroy()
    Staff_select()

#主界面跳转
def chaneg_main():
    window_function.destroy()
    mainpage()

#主界面
def mainpage():
    global window
    window = tk.Tk()
    window.title("超市零售信息管理系统")
    window.geometry('500x400')
    #生成画布，销毁后生成新的画布实现跳转
    page = tk.Frame(window)
    page.pack()
    tk.Label(window, text="欢迎使用超市零售信息管理系统", font=("黑体", 20)).pack(pady=10)
    button1 = tk.Button(window, text="添加商品信息", command=change_add).pack(pady=10)
    button2 = tk.Button(window, text="删除商品信息", command=change_delete).pack(pady=10)
    button3 = tk.Button(window, text="修改商品信息", command=change_update).pack(pady=10)
    button4 = tk.Button(window, text="查找商品供货商名称", command=change_select).pack(pady=10)
    window.mainloop()

#主函数生成主界面
if __name__ == '__main__':
    mainpage()
```
## 五.總結
在開始設計前，要事先做足需求分析，瞭解自己的資料庫具體要實現什麼樣的功能，因為每一個數據中需要建立許多表，很容易混亂各個表之間的邏輯關係，因此可以把概念結構設計放在邏輯結構設計之前進行
## 參考文獻
[软件工程 超市销售管理系统](https://abg.baidu.com/view/c0c12e10a216147916112804?fr=seoSearch-income-top3page)

[超市综合管理信息系统](https://xiaojie.blog.csdn.net/article/details/131471335?spm=1001.2101.3001.6650.6&utm_medium=distribute.pc_relevant.none-task-blog-2%7Edefault%7EBlogCommendFromBaidu%7ERate-6-)

[数据库课程设计—超市零售信息管理系统（Python实现）](https://blog.csdn.net/weixin_45525142/article/details/119729731?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522170357706416800222863070%2522%252C%2522scm%2522%253A%252220140713.130102334.pc%255Fblog.%2522%257D&request_id=170357706416800222863070&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~blog~first_rank_ecpm_v1~rank_v31_ecpm-4-119729731-null-null.nonecase&utm_term=%E8%B6%85%E5%B8%82%E7%AE%A1%E7%90%86%E7%B3%BB%E7%BB%9F%E7%9A%84%E8%AE%BE%E8%AE%A1%E4%B8%8E%E5%AE%9E%E7%8E%B0&spm=1018.2226.3001.4450)

[数据库课程设计超市信息管理系统](https://blog.csdn.net/yh1009/article/details/130857542?ops_request_misc=&request_id=&biz_id=102&utm_term=%E8%B6%85%E5%B8%82%E7%AE%A1%E7%90%86%E7%B3%BB%E7%BB%9F&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduweb~default-2-130857542.nonecase&spm=1018.2226.3001.4187)
