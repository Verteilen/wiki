# 運作流程

這是專案的內容, 分爲好幾層

```mermaid
---
title: 專案結構
---
flowchart LR
    A[專案] -.->|1| B[資料庫]
    A -->|N| C[流程]
    C -->|N| D[工作]
```

## 專案

The project container, you can put name and description in here, just easy to manage.

## 流程

This probably the most important part, defining tasks <br />
A project can have multiple task <br />
Every task can have different flags <br />
Currently Verteilen support 3 flags

* No Flags
* Setup
* Cluster
* Multithread

!!! note "No Flag Scenario"
    The backend will pick only one compute node, and run the task, then it will mark it as finish

```mermaid
---
title: 場景
---
flowchart LR
    Z[流程] --> Z0{預設}
    Z[流程] --> Z1{設置型}
    Z[流程] --> Z2{分散運算}
    Z[流程] --> Z3{多核運算}
    Z0 -->|生成| A0[1 x 子流程]
    Z1 -->|生成| A1[1 x 子流程]
    Z2 -->|生成| A2[(N x 子流程)]
    Z3 -->|生成| A3[(N x 子流程)]
    A0 --> B0(單一節點跑一次)
    A1 --> B1(多個節點跑一次)
    A2 --> B2(透用節點池運算)
    A3 --> B3(透用節點池運算 <br />一個節點可同時跑 2+ 子流程)
```

#### 設置型

You want every compute node run once

!!! warning "Compute Node Offline Scenario"
    If one of the compute node is offline, backend will keep waiting for it to back online to do the task

#### 分散運算

Base on the input number, it will create a queue, and run it one by one, until all the subtask finish <br />
Subtesk create base on the input number, if input is 5, then it will have 5 subtask create

#### 多核運算

Base on the input number, It will set the thread running upper-limit for a single compute node <br />
If the input is 4, and if cluster flag is on as well, then a single node can run 4 subtasks at once

This is useful for low compute task such as small file converting or apply metadata for a video file

## 工作

The content of the task <br />
A task can have multiple jobs

By the way, Verteilen currently support use Javascript VM to write the logic here

#### 表達式

## 資料庫

