---
id: table-operations
title: Table Operations
sidebar_label: Table Operations
---

The EDC provides users with the ability to use OData to query their database.  

Learn more about OData <a href="https://www.odata.org/getting-started/" target="_blank">here.</a>  

For our examples, we will assume that we have generated a Connector called "test" and we have a table called "people".  

## Get Data From Tables  

### Front-End

One of the quickest ways to make a GET request to your database is to simply make an AJAX call with following url:  

```js
../api/<connector>/_table/<table_name>
```  

In this example, our query string would look like this:  

```js
../api/test/_table/people
```  

This is telling the EDC api to make a request to the "people" table in the "test" connector. The full AJAX call would look similar to the following:  

```js
$.ajax({
    type: "GET",
    content: "application/json",
    url: "/api/test/_table/people",
    success: function(result) {
        // It worked!
        console.log(result)
    }
})
```  

In a front-end application like React, you might use [axios](#):  

```js
axios.get('/api/test/_table/people')
.then(result => {
    //It worked
    console.log(result)
})
```  

### Back-End  

In addition to making calls in the views of your application, the EDC also supports making calls from your back-end controllers as well using TableOperations.GetAll().

```c#
public ActionResult Get()
        {
            var results = TableOperations.GetAll("test", "people");
                                 
            return Json(results);
        }
```

### Result

The EDC API will always return a JSON object. In our example, we would have gotten the information back from the EDC:  

```json
[
    {
        "id": 1,
        "name": "Jim",
        "age": 23
    },
    {
        "id": 2,
        "name": "Bob",
        "age": 31
    },
    {
        "id": 3,
        "name": "Joe",
        "age": 27
    }
]
```  

From this point, you can interact with your data how you normally would within your application.

## Post Data To Tables

### Front-End

To post data from the front-end of your application, you simply make an AJAX call with the same url from [GET](#front-end) and include the data that you wish to post.  

```js
var data = {
    "name":Jeff,
    "age":54
}

$.ajax({
    type: "GET",
    content: "application/json",
    url: "/api/test/_table/people",
    data: data,
    success: function(result) {
        // It worked!
        console.log(result)
    }
})
```  

On success, the network response from the EDC API will contain the data that you just inserted into your database.  

### Back-End

In order to post information to your backend controller, you should setup a controller method that takes in a model of the database table that you are trying to update.  

Then, you simply call CreateNewRow in your method.  

```c#
[HttpPost]
public ActionResult Post(ViewModel model) 
{
    if(ModelState.IsValid)
    {
        model.BuildConnectionString();
        model = TableOperations.CreateNewRow("test", "people", model)
    }
    return Json(model);
}
```  

## Update Tables

### Front-End

The only difference between posting and updating is that the url that you put in your ajax request will require the ID of the object you are trying to update. In this example, we will update the item with ID of 1.  

```js
var data = {
    "name":Jeff,
    "age":54
}

$.ajax({
    type: "PUT",
    content: "application/json",
    url: "/api/test/_table/people/1",
    data: data,
    success: function(result) {
        // It worked!
        console.log(result)
    }
})
```  

Now the first item in the database will have the name Jeff and the age of 54.  

### Back-End

Updating in the back-end is also very similar to inserting. Make another method that also takes in the same type of model and call the UpdateRow method.  

```c#
[HttpPost]
public ActionResult Post(ViewModel model) 
{
    if(ModelState.IsValid)
    {
        model.BuildConnectionString();
        model = TableOperations.UpdateRow("test", "people", model)
    }
    return Json(model);
}
```  

Additionally, you can combine both the insert and update methods into one method and just do a check to see if the ID is equal to 0:  

```c#
[HttpPost]
public ActionResult Post(ViewModel model)
{
    if(ModelState.IsValid)
    {
        model.BuildConnectionString();

        if (model.Id == 0)
            model = TableOperations.CreateNewRow("test", "people", model);
        else
            TableOperations.UpdateRow("test", "people", model);
    }

    return Json(model);
}
```  

## Deleting From A Table

### Front-End

To delete data from your database, make an AJAX call that contains the ID of the object that you wish to delete.  

```js
$.ajax({
    type: "DELETE",
    content: "application/json",
    url: "/api/test/_table/people/1",
    success: function(result) {
        // It worked!
        console.log(result)
    }
})
```  

This will delete the object with an ID of 1 from the "people" table inside of the "test" connector.

### Back-End
