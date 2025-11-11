# 流程

一個擁有多個任務的容器, 還有會影響執行階段的配置項目

## 介面

流程介面的位置

<img style="width:50%" src="./../../../static/task/TaskPage.png" />

在這個頁面, 你可以透過工具列完成所有動作

* 新增流程
* 匯出流程
* 其他...

<img style="width:100%" src="./../../../static/task/TaskPage2.png" />

## 新增流程

按下新增按鈕 新增流程

<img style="width:100%" src="./../../../static/task/AddTask.png" />

你必須輸入名稱, 否則不會接受

<img style="width:50%" src="./../../../static/task/AddTask2.png" />

<img style="width:50%" src="./../../../static/task/AddTask3.png" />

你可以選擇流程的執行模式, 透過下拉式選單選取

<img style="width:50%" src="./../../../static/task/AddTask4.png" />

你可以選擇分散運算模式 <br />
執行階段會生成多個子流程

<img style="width:50%" src="./../../../static/task/AddTask5.png" />

!!! Warning "執行順序"
    執行的節點並沒有任何順序可言 <br />
    任何節點只要完成任務, 就會去找下一個子流程執行

多核心模式, 單一節點可以同時跑多個子流程

<img style="width:50%" src="./../../../static/task/AddTask6.png" />

!!! Warning "高需求算力任務"
    如果你的流程內容含有 cpu 或是 gpu 高算力需求 <br />
    推薦你使用分散運算, 不要使用多核心

## 綁定

專案綁定的資料庫, 方便於執行階段建立 <br />
你可以留空, 執行階段再選擇資料庫

* 按左側進入資料庫頁面
* 按選擇, 選擇其他資料庫綁定

<img style="width:100%" src="./../../../static/task/Binding.png" />

* 按 None 取消綁定
* 按其他資料庫綁定

<img style="width:60%" src="./../../../static/task/Binding2.png" />

如果你專案沒有綁定, 看起來會是像這樣子

<img style="width:60%" src="./../../../static/task/Binding3.png" />