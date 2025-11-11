# 資料庫

參數的持有容器, 用戶也可以在執行階段進行更新

## 介面

資料庫頁面位置

<img style="width:50%" src="./../../../static/database/DatabasePage.png" />

在這個頁面, 你可以透過工具列完成所有動作

* 新增資料庫
* 匯出資料庫
* 新增參數
* 其他...

<img style="width:100%" src="./../../../static/database/DatabasePage2.png" />

## 新增資料庫

點擊左上角新增資料庫

<img style="width:50%" src="./../../../static/database/NewDatabase.png" />

必須輸入名稱 <br />
你也可以套用樣板來建立資料庫

<img style="width:50%" src="./../../../static/database/NewDatabase2.png" />

點選群組裡面你要的樣板, 然後按確定

<img style="width:50%" src="./../../../static/database/NewDatabase3.png" />

按鈕文字會變成你選擇的樣板

<img style="width:50%" src="./../../../static/database/NewDatabase4.png" />

## 選擇資料庫

典籍資料庫名稱選擇其他資料庫

<img style="width:50%" src="./../../../static/database/SelectDatabase.png" />

## 新增參數

點擊左上角新增參數

<img style="width:50%" src="./../../../static/database/NewVariable.png" />

必須輸入名稱

<img style="width:50%" src="./../../../static/database/NewVariable2.png" />

你可以選擇其他資料形態

<img style="width:50%" src="./../../../static/database/NewVariable3.png" />

這是特殊的資料形態, 下一區會詳細介紹

<img style="width:50%" src="./../../../static/database/NewVariable4.png" />

## 表達式

細節請看 [表達式](https://www.npmjs.com/package/expressionparser) 

表達式將會在運算階段使用, 你看到以下的參數是表達式的數值, 並非結果 <br />
以這個範例將會是 4 + 9999, 回傳 10003 並且保存在 e1 的參數容器中

<img style="width:100%" src="./../../../static/database/Expression.png" />