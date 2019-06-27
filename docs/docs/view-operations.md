---
id: view-operations
title: View Operations
sidebar_label: View Operations
---

The EDC provides users with the ability to use OData to query their database views.  

Learn more about OData <a href="https://www.odata.org/getting-started/" target="_blank">here.</a>  

For this example, assume that a Connector called "AdventureWorks" has been created and the database has a view called "PeopleInStates".  

## Get Data From Views  

One of the quickest ways to make a GET request to a database is to make an AJAX call with following url:  

```js
../api/<connector>/_view/<view_name>
```  

In this example, our query string would look like this:  

```js
../api/AdventureWorks/_view/PeopleInStates
```  

This is telling the EDC api to make a request to the "PeopleInStates" view in the "AdventureWorks" connector. The full AJAX call would look similar to the following:  

```js
$.ajax({
    type: "GET",
    content: "application/json",
    url: "/api/AdventureWorks/_view/PeopleInStates",
    success: function(result) {
        // It worked!
        console.log(result)
    }
})
```  

In a front-end application like React, you might use [axios](#):  

```js
axios.get('/api/AdventureWorks/_view/PeopleInStates')
.then(result => {
    //It worked
    console.log(result)
})
```  

### Result

The EDC API will always return a JSON object. In this example, the following information would be returned from the EDC:  

```json
[
    {
        "id": 1,
        "name": "Jim",
        "age": 23,
        "StateId": 1
    },
    {
        "id": 2,
        "name": "Bob",
        "age": 31,
        "StateId": 1
    },
    {
        "id": 3,
        "name": "Joe",
        "age": 27,
        "StateId": 3
    }
]
```  

From this point, applications can interact with the data just like a normal JSON response.


