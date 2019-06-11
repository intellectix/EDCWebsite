---
id: create-connector
title: Create a Connector
sidebar_label: Create a Connector
---

## Create Connection

When you are logged into the EDC Dashboard, click the "Connectors" link on the left of the page.  

Once on the Connectors page, click the "Add Connector" button in the top right corner.  

Next, you must select which type of database you wish to connect to the EDC. Currently, we support MS SQL, MySQL, and Oracle.  

After clicking on a database, simply fill out the form (all fields are required) and the EDC will generate a connection string with the information you provided that looks like the following:  

```c#
<add name="MovieDBContext" 
   connectionString="Data Source=(LocalDb)\MSSQLLocalDB;Initial Catalog=aspnet-MvcMovie;Integrated Security=SSPI;AttachDBFilename=|DataDirectory|\Movies.mdf" 
   providerName="System.Data.SqlClient" 
/>
```  

If the EDC successfully reaches a connection, the system will return you to the Connectors page and you should see your new connector displayed in the list. You can now use this connector to query your database through our API.  

## Editing a Connector  

To edit a connector, click on the "Edit" button on the connectors page.  

This will take you to a page which will allow you to update any of the information you provided when you added the connector, as well as [create user joins](/docs/create-user-join).