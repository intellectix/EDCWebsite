---
id: add-permissions-to-role
title: Add Permissions to a Role
sidebar_label: Add Permissions to a Role
---
<div class="note" style="padding: 8px 35px 8px 14px; margin-bottom: 20px; text-shadow: 0 1px 0 rgba(255,255,255,0.5); border-radius: 4px; color: #3a87ad; background-color: #d9edf7; border-color: #bce8f1;">EDC Pro Subscription Required</div> 

In order for Users to access a database through the EDC, they need to be assigned to a Role. On top of that, the Role must also have specific database Permissions applied to it. By default, all of the data in your database is not able to be seen until permissions are granted.  

To add Permissions to a Role, first click on the "Roles" link on the left-hand side of the page.  

Then, select the Role to add Permissions to. The EDC will redirect to that Role's Edit page.  

Once on the Edit page, click on the "Permissions" Tab. This tab will show all of the permissions that are currently assigned to that Role. To add a Permission, click on the "Add Permission" button.  

The EDC will redirect to a new page with a form.  

The Type field determines whether the Role will be able to Read, Write, or Delete data from the database. The Connector is the name of the Connector that creates the connection to the database. The Schema Name allows for selection of the database Schema. The Resource Type specifies whether access is being granted to a Table, View, or Stored Procedure. The Resource is the name of the specific Table, View, or Stored Procedure that to grant access to. Finally, the Property field is the name of the column in a Table, View, or Stored Procedure. To grant rights to all columns, write "All_Properties." Once values have been provided for all the fields, click "Add Permission."  

If the EDC successfully creates the permission, the system will redirect back to the Role's Edit page which the new permission listed on the "Permissions" tab. Now users assigned to the Role can successfully make queries based on the Permission.