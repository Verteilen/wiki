# Workflow

Let's just put this image here for overview <br />
This is the entire project content, which contain several layers

![Workflow](./../static/Workflow.drawio.png)

## Project

The project container, you can put name and description in here, just easy to manage.

## Task

This probably the most important part, defining tasks <br />
A project can have multiple task <br />
Every task can have different flags <br />
Currently Verteilen support 3 flags

* Setup
* Cluster
* Multithread

!!! note "No Flag Scenario"
    The backend will pick only one compute node, and run the task, then it will mark it as finish

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

## Parameter

