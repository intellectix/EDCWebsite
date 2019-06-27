---
id: add-permissions-to-role
title: Add Permissions to a Role
sidebar_label: Add Permissions to a Role
---
###PRO 

In order for Users to access a database through the EDC, they need to be assigned to a Role. On top of that, the Role must also have specific database Permissions applied to it. By default, all of the data in your database is not able to be seen until permissions are granted.  

To add Permissions to a Role, first click on the "Roles" link on the left-hand side of the page.  

Then, select the Role to add Permissions to. The EDC will redirect to that Role's Edit page.  

Once on the Edit page, click on the "Permissions" Tab. This tab will show all of the permissions that are currently assigned to that Role. To add a Permission, click on the "Add Permission" button.  

The EDC will redirect to a new page with a form.  

The Type field determines whether the Role will be able to Read, Write, or Delete data from the database. The Connector is the name of the Connector that creates the connection to the database. The Schema Name allows for selection of the database Schema. The Resource Type specifies whether access is being granted to a Table, View, or Stored Procedure. The Resource is the name of the specific Table, View, or Stored Procedure that to grant access to. Finally, the Property field is the name of the column in a Table, View, or Stored Procedure. To grant rights to all columns, write "All_Properties." Once values have been provided for all the fields, click "Add Permission."  

If the EDC successfully creates the permission, the system will redirect back to the Role's Edit page which the new permission listed on the "Permissions" tab. Now users assigned to the Role can successfully make queries based on the Permission.