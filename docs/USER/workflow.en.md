# Workflow

This is the entire project content, which contain several layers

```mermaid
---
title: Overview
---
flowchart LR
    A[Project] -.->|1| B[Parameter]
    A -->|N| C[Task]
    C -->|N| D[Job]
```

## Project

The project container, you can put name and description in here, just easy to manage.

## Task

This probably the most important part, defining tasks <br />
A project can have multiple task <br />
Every task can have different flags <br />
Currently Verteilen support 4 types of scenario 

* No Flags
* Setup
* Cluster
* Multithread

!!! note "No Flag Scenario"
    The backend will pick only one compute node, and run the task, then it will mark it as finish

```mermaid
---
title: scenario
---
flowchart LR
    Z[Task] --> Z0{No Flags}
    Z[Task] --> Z1{Setup}
    Z[Task] --> Z2{Cluster}
    Z[Task] --> Z3{Multithread}
    Z0 -->|Generate| A0[1 x Subtask]
    Z1 -->|Generate| A1[1 x Subtask]
    Z2 -->|Generate| A2[(N x Subtasks)]
    Z3 -->|Generate| A3[(N x Subtasks)]
    A0 --> B0(One Node Run Once)
    A1 --> B1(All Node Run Once)
    A2 --> B2(Run by Node Pool)
    A3 --> B3(Run by Node Pool <br />Run 2+ subtask at one node)
```

#### Setup

You want every compute node run once

!!! warning "Compute Node Offline Scenario"
    If one of the compute node is offline, backend will keep waiting for it to back online to do the task

#### Cluster

Base on the input number, it will create a queue, and run it one by one, until all the subtask finish <br />
Subtesk create base on the input number, if input is 5, then it will have 5 subtask create

#### Multithread

Base on the input number, It will set the thread running upper-limit for a single compute node <br />
If the input is 4, and if cluster flag is on as well, then a single node can run 4 subtasks at once

This is useful for low compute task such as small file converting or apply metadata for a video file

## Job

The content of the task <br />
A task can have multiple jobs

By the way, Verteilen currently support use Javascript VM to write the logic here

#### Expression

Currently the properties is use [Expression](https://www.npmjs.com/package/expressionparser) NPM package to do the work <br />
The point of the expression here is to get result base on different scenario

## Database

The variables which use during the compute stage <br />
You can change the variable in the compute stage as well, it will make a copy to that stage. so it's fine