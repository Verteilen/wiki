# Database

A variables holder container, User can modify them during the compute stage as well.

## Views

The database page location

<img style="width:50%" src="./../../static/database/DatabasePage.png" />

In this page, you can do everything in the action bar

* Added database
* Export database
* Added Variable
* etc...

<img style="width:100%" src="./../../static/database/DatabasePage2.png" />

## Add Database

Click top left corner for creating a new database

<img style="width:50%" src="./../../static/database/NewDatabase.png" />

You must enter name to create <br />
You can also apply template for the database

<img style="width:50%" src="./../../static/database/NewDatabase2.png" />

Click the template in the group and hit confirm

<img style="width:50%" src="./../../static/database/NewDatabase3.png" />

The button text will change to current select template

<img style="width:50%" src="./../../static/database/NewDatabase4.png" />

## Select Database

Click the database name for select another database

<img style="width:50%" src="./../../static/database/SelectDatabase.png" />

## Add Variable

Click top right corner for creating a new variable

<img style="width:50%" src="./../../static/database/NewVariable.png" />

You must enter name to create

<img style="width:50%" src="./../../static/database/NewVariable2.png" />

You can select different datatype for the variable you are about to create

<img style="width:50%" src="./../../static/database/NewVariable3.png" />

This is the special datatype, the detail is in the next section

<img style="width:50%" src="./../../static/database/NewVariable4.png" />

## Expression

Checkout [Expression](https://www.npmjs.com/package/expressionparser) for language details

Expression is execute during the compute stage, The value here is expression string, which is not the result yet <br />
In this case the expression will be 4 + 9999, then it will return 10003 and store in e1 variable container

<img style="width:100%" src="./../../static/database/Expression.png" />