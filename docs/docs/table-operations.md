---
id: table-operations
title: Table Operations
sidebar_label: Table Operations
---

The EDC provides users with the ability to use OData to query their database tables.  

Learn more about OData <a href="https://www.odata.org/getting-started/" target="_blank">here.</a>  

For our examples, assume that a Connector called "AdventureWorks" has been created and the database has a table called "States".  

## Get Data From Tables  

One of the quickest ways to make a GET request to your database is to simply make an AJAX call with following url:  

```js
../api/<connector>/_table/<table_name>
```  

In this example, our query string would look like this:  

```js
../api/AdventureWorks/_table/States
```  

This is telling the EDC api to make a request to the "States" table in the "AdventureWorks" connector. The full AJAX call would look similar to the following:  

```js
$.ajax({
    type: "GET",
    content: "application/json",
    url: "/api/AdventureWorks/_table/States",
    success: function(result) {
        // It worked!
        console.log(result)
    }
})
```  

In a front-end application like React, you might use [axios](#):  

```js
axios.get('/api/AdventureWorks/_table/States')
.then(result => {
    //It worked
    console.log(result)
})
```  

### Result

The EDC API will always return a JSON object. In our example, we would have gotten the information back from the EDC:  

```json
[
    {
        "id": 1,
        "StateName": "Alabama"
    },
    {
        "id": 2,
        "StateName": "Alaska"
    },
    {
        "id": 3,
        "StateName": "Arizona"
    },
    {
        "id": 4,
        "StateName": "Arkansas"
    },
    {
        "id": 5,
        "StateName": "California"
    }

    ...
]
```  

From this point, applications can interact with the data just like a normal JSON response.

## Post Data To Tables

To post data, make an AJAX call with the same url from GET and include the data to post.  

```js
var data = {
    StateName: "Virginia"
}

$.ajax({
    type: "POST",
    content: "application/json",
    url: "/api/AdventureWorks/_table/States",
    data: data,
    success: function(result) {
        // It worked!
        console.log(result)
    }
})
```  

On success, the network response from the EDC API will contain the data that was just inserted into the database.  

## Update A Table

The only difference between posting and updating is that the url in the ajax request will require the ID of the object to update. In this example, the will update the item with ID of 1.  

```js
var data = {
    StateName: "AlabamaIsCool"
}

$.ajax({
    type: "PUT",
    content: "application/json",
    url: "/api/AdventureWorks/_table/States/1",
    data: data,
    success: function(result) {
        // It worked!
        console.log(result)
    }
})
```  

Now the first item in the database will have the name AlabamaIsCool.  

## Deleting From A Table

To delete data from a database, make an AJAX call that contains the ID of the object to delete.  

```js
$.ajax({
    type: "DELETE",
    content: "application/json",
    url: "/api/AdventureWorks/_table/States/1",
    success: function(result) {
        // It worked!
        console.log(result)
    }
})
```  

This will delete the object with an ID of 1 from the "States" table inside of the "AdventureWorks" connector.
