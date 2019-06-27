---
id: stored-procedure-operations
title: Stored Procedure Operations
sidebar_label: Stored Procedure Operations
---

The EDC provides users with the ability to use OData to query their database stored procedures.  

Learn more about OData <a href="https://www.odata.org/getting-started/" target="_blank">here.</a>  

For this example, assume that a Connector called "AdventureWorks" has been created and the database has a stored procedure called "StateSales".   

## Get Data From Stored Procedures 

One of the quickest ways to make a GET request to a database is to simply make an AJAX call with following url:  

```js
../api/<connector>/_sproc/<sproc_name>
```  

In this example, our query string would look like this:  

```js
../api/AdventureWorks/_sproc/StateSales
```  

This is telling the EDC api to make a request to the "StateSales" view in the "AdventureWorks" connector. The full AJAX call would look similar to the following:  

```js
$.ajax({
    type: "GET",
    content: "application/json",
    url: "/api/AdventureWorks/_sproc/StateSales",
    success: function(result) {
        // It worked!
        console.log(result)
    }
})
```  

In a front-end application like React, you might use [axios](#):  

```js
axios.get('/api/AdventureWorks/_sproc/StateSales')
.then(result => {
    //It worked
    console.log(result)
})
```  

### Result

The EDC API will always return a JSON object. In our example, the following information would be returned from the EDC:

```json
[
    {
        "id": 1,
        "StateID": 1,
        "StateSales": 150434
    },
    {
        "id": 2,
        "StateID":2,
        "StateSales":87555
    },
    {
        "id": 3,
        "StateID":3,
        "StateSales":45000
    }
]
```  

From this point, applications can interact with the data just like a normal JSON response.


