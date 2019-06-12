---
id: view-operations
title: View Operations
sidebar_label: View Operations
---

The EDC provides users with the ability to use OData to query their database views.  

Learn more about OData <a href="https://www.odata.org/getting-started/" target="_blank">here.</a>  

For our examples, we will assume that we have generated a Connector called "test" and we have a view called "peopleView".  

## Get Data From Views  

### Front-End

One of the quickest ways to make a GET request to your database is to simply make an AJAX call with following url:  

```js
../api/<connector>/_view/<view_name>
```  

In this example, our query string would look like this:  

```js
../api/test/_view/peopleView
```  

This is telling the EDC api to make a request to the "peopleView" view in the "test" connector. The full AJAX call would look similar to the following:  

```js
$.ajax({
    type: "GET",
    content: "application/json",
    url: "/api/test/_view/peopleView",
    success: function(result) {
        // It worked!
        console.log(result)
    }
})
```  

In a front-end application like React, you might use [axios](#):  

```js
axios.get('/api/test/_view/peopleView')
.then(result => {
    //It worked
    console.log(result)
})
```  

### Back-End  

In addition to making calls in the views of your application, the EDC also supports making calls from your back-end controllers as well using ViewOperations.GetAll().

```c#
public ActionResult Get()
        {
            var results = ViewOperations.GetAll("test", "peopleView");
                                 
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
        "age": 23,
        "city": "Seattle",
        "state": "Washington"
    },
    {
        "id": 2,
        "name": "Bob",
        "age": 31,
        "city": "Boston",
        "state": "Massachusetts"
    },
    {
        "id": 3,
        "name": "Joe",
        "age": 27,
        "city": "Baltimore",
        "state": "Maryland"
    }
]
```  

From this point, you can interact with your data how you normally would within your application.


