---
id: overview
title: Overview
sidebar_label: Overview
---

The EDC is an **open-source** framework that provides a more efficient way to dynamically access your data layer. Database schemas can be changed on the fly, without having to recompile your application.  

## Write To Tables
Write to database tables by defining the model at runetime

```c#
//Create a new customer
customer = TableOperation.CreateNewRow("AdventureWorks", "Customer", customer);
```  

```c#
// Update an existing customer
customer = TableOperation.UpdateRow("Adventureworks", "Customer", customer); 
```  

### Use the RESTful API

```js
$.ajax({
  type: "POST",
  url: "/api/AdventureWorks/_table/Customer",
  data: data,
});
```  

```js 
$.ajax({
  type: "PUT",
  url: "/api/AdventureWorks/_table/Customer/42",
  data: data,
});
```  

## Read From Tables
Read from tables by defining the model at runetime  

```c#
// Retieve a list of customers
var customers = TableOperation.Get("Adventureworks", "Customers"); 
```  

```c#
// Retieve a single customer
var customer = TableOperation.GetById("Adventureworks", "Customers", "42"); 
```  

### Use the RESTful API

```js
$.ajax({
  type: "GET",
  url: "/api/AdventureWorks/_table/Customers/42",
  data: data,
});
```  

```js
$.ajax({
  type: "GET",
  url: "/api/AdventureWorks/_table/Customers",
  data: data,
});
```  

## Delete From Tables 
Delete a row from a table  

```c#
// Delete a customer
TableOperation.DeleteRow("Adventureworks", "Customer", "42"); 
```  

### Use the RESTful API

```js
$.ajax({
  type: "DELETE",
  url: "/api/AdventureWorks/_table/Customer/42",
  data: data,
});
```  

## Add a table to a database
Create a new table in the database  

```c#
// Create a Table
DatabaseOperation.CreateTable("Adventureworks", "Customer"); 
```  

### Use the RESTful API

```js
$.ajax({
  type: "POST",
  url: "/api/AdventureWorks/",
  data: data,
});
```

## Add a column to a table
Create a new column in the table  

```c#
// Create a column
TableOperation.CreateColumn("Adventureworks", "Customer", "Zipcode");
```  

### Use the RESTful API 

```js
$.ajax({
  type: "POST",
  url: "/api/AdventureWorks/_table/Customer/42",
  data: data,
});
```


