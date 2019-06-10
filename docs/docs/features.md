---
id: features
title: Features
---

## Dashboard

The EDC Dashboard shows you a high level overview of what is going on behind the scenes in your application. Right at the top, you get a quick summary of the total database requests for the day, the number of unique IP address that have queried the database, and the number of requests that have failed (500 error). Below that, you can see two graphs. The first shows the total number of requests for the day broken down into GET, POST, PUT, and DELETE. The second graph shows you the total number of requests each day for the past seven days.

![alt-text](/img/dashboard.PNG "Dashboard")

At the bottom, you can see the 10 most recent requests made to your database. When you click on a request, it will show you the information captured in the Request, the Reponse, and if the user was authorized to proceed with their request.

In addition, at the top of the dashboard, you can also [add a Connector](#)

## Connectors

On the connectors page, you will see a list of all the database connections that have been made in your instance of the EDC.  
  
On the top of the page you can [add a connector](#).   
Clicking the edit button on the right will take you to [edit a connector](#). 

### Add A Connector

There are two places where you can initiate a connector creation. On the top right of the dashboard, you can click the "Add A Connector" button. On the Connectors page, you can click "Add Connector" in the top right as well. 

You will then be brought to a page asking you to choose with type of database your application will utilize. The EDC currently supports MS SQL, MySQL, and Oracle. Select your database type and you will be taken to a form which asks for all the required information to allow the EDC to make a connection to your database. Once you fill out the form, the EDC will test the connection and then return you back to the [Connectors](#) page on success.

### Edit A Connector

On the connectors page, click the edit button and you will be brought to the connector's edit page. The initial page shows you the same information that you provided when you added the Connector. If there have been any changes to your connection string, you should make your updates here.

On the Joins tab, you will see a list of all the user joins which have been specified for this connector. You can edit a user join in this list by clicking on its Alias which will bring you to its edit page. 

#### Add A User Join

To add a user join, click the "Add Join" button on the top right of the Tab. On the next page, you will specify in the form which columns you would like to join. When you are done, click "Save" and you will be redirected to the list of user joins. 

## Requests

The Requests page will show you the top 50 most recent requests that have been made to the database. This list will show you the same information as the dashboard:   
* Date/Time  
* Type (GET,POST,PUT,DELETE)  
* IP Address  
* Connector  
* Status  

When you click on a request you will see the information captured in the Request, the Reponse, and if the user was authorized to proceed with their request.

## Developer

Clicking on the Developer link will open a new window to the Swagger UI. This page allows you to make calls directly to the EDC upderlying API.  

To get this functionality working, first click on the Login tab and then click on the POST link. This will expand the UI to show a textbox which asks for a JSON object containing a users Username and Password. This information must be provided in the following format:  

```json
{
    "Username": "user",
    "Password": "123"
}
```
Once this information has been provided, click on the 'Try it out!' button and you will be provided with that users JWT token which is what the EDC API uses to authorize a user.  

Copy this JWT token and paste it into the api_key textbox at the top of the page. Then, hit 'Explore' and the page will refresh. You now have full access to that users rights within the API and can make requests on their behalf. All requests made in this UI will be logged and can be viewed back in the EDC UI's [Requests](#) page.

### Pull Data In A Table

Once the Swagger UI has refreshed with the users JWT token, click on the Tables tab and then the GET tab. 
