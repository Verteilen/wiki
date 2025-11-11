# Task

## Overview

The task page location

<img style="width:25%" src="./../../static/TaskPage.png" />

Toolbar layout

<img style="width:100%" src="./../../static/TaskPage2.png" />

## Add New Task

Click button to add task

<img style="width:100%" src="./../../static/AddTask.png" />

As you can see, you must enter the name, otherwise the menu will not accept

<img style="width:50%" src="./../../static/AddTask2.png" />

<img style="width:50%" src="./../../static/AddTask3.png" />

You can choose it to be setup job type <br />
Which it's the task run in every nodes once

<img style="width:50%" src="./../../static/AddTask4.png" />

Or you can choose distribute, which let this be a cronjob type <br />
It will generate a number of subtask that use every nodes to finish it

!!! Warning "Execute Order"
    No It does not have order like, first node run first job, second node run second job <br />
    As long as the node finish the current subtask, it will fetch the next unfinish subtask <br />
    It run as quickly as possible

<img style="width:50%" src="./../../static/AddTask5.png" />
<img style="width:50%" src="./../../static/AddTask6.png" />

With multicore checked, One node can have multiple subtask execute at the same time

!!! Warning "Compute Heavy"
    If your task have cpu or gpu heavy compute task <br />
    We recommand you not to check this <br />
    It should be use on the lightweight task such as transcoding or formating json etc...

<img style="width:50%" src="./../../static/AddTask7.png" />

New update 

* Decide that the display should change to single row, It's eaiser to read

<img style="width:50%" src="./../../static/AddTask8.png" />


## Binding

It's a project binding parameter, It's just a default binding to a data vault <br />
You can actually leave this empty, You can assign it in the console page as well

* Click green text to jump to parameter setting menu <br />
* Click dotted box to select other parameter

<img style="width:60%" src="./../../static/Binding.png" />

* Click None to unbind
* Click other to change binding

<img style="width:60%" src="./../../static/Binding2.png" />

This is what you see when project is binding to nothing

<img style="width:60%" src="./../../static/Binding3.png" />