---
id: create-connector
title: Create a Connector
sidebar_label: Create a Connector
---

## Create Connection

Once logged into the EDC Dashboard, click the "Connectors" link on the left of the page.  

Once on the Connectors page, click the "Add Connector" button in the top right corner.  

Next, select which type of database to connect to the EDC. Currently, the EDC supports MS SQL, MySQL, and Oracle.  

After clicking on a database, fill out the form (all fields are required) and the EDC will generate a connection string with the information provided that looks like the following:  

```c#
<add name="MovieDBContext" 
   connectionString="Data Source=(LocalDb)\MSSQLLocalDB;Initial Catalog=aspnet-MvcMovie;Integrated Security=SSPI;AttachDBFilename=|DataDirectory|\Movies.mdf" 
   providerName="System.Data.SqlClient" 
/>
```  

If the EDC successfully reaches a connection, the system will redirect to the Connectors page and the new connector will be displayed in the list. This connector can now be used to query the database through our API.  

## Editing a Connector  

To edit a connector, click on the "Edit" button on the connectors page.  

This will load a page which will allow updates to any of the information provided when the connector was created, as well as [create user joins](/docs/create-user-join).