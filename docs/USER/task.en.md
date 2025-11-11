# Task

## Views

The task page location

<img style="width:50%" src="./../../static/task/TaskPage.png" />

In this page, you can do everything in the action bar

* Added task
* Export task
* etc...

<img style="width:100%" src="./../../static/task/TaskPage2.png" />

## Add New Task

Click button to add task

<img style="width:100%" src="./../../static/task/AddTask.png" />

As you can see, you must enter the name, otherwise the menu will not accept

<img style="width:50%" src="./../../static/task/AddTask2.png" />

<img style="width:50%" src="./../../static/task/AddTask3.png" />

You can choose task execute mode by dropdown menu here

<img style="width:50%" src="./../../static/task/AddTask4.png" />

Or you can choose distribute, which let this be a cronjob type <br />
It will generate a number of subtask that use every nodes to finish it

<img style="width:50%" src="./../../static/task/AddTask5.png" />

!!! Warning "Execute Order"
    No It does not have order like, first node run first job, second node run second job <br />
    As long as the node finish the current subtask, it will fetch the next unfinish subtask <br />
    It run as quickly as possible

With multicore checked, One node can have multiple subtask execute at the same time

<img style="width:50%" src="./../../static/task/AddTask6.png" />

!!! Warning "Compute Heavy"
    If your task have cpu or gpu heavy compute task <br />
    We recommand you not to check this <br />
    It should be use on the lightweight task such as transcoding or formating json etc...


## Binding

It's a project binding database, It's just a default binding to a data vault <br />
You can actually leave this empty, You can assign it in the console page as well

* Click green text to jump to database setting menu <br />
* Click dotted box to select other database

<img style="width:60%" src="./../../static/task/Binding.png" />

* Click None to unbind
* Click other to change binding

<img style="width:60%" src="./../../static/task/Binding2.png" />

This is what you see when project is binding to nothing

<img style="width:60%" src="./../../static/task/Binding3.png" />