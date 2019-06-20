---
id: add-permissions-to-role
title: Add Permissions to a Role
sidebar_label: Add Permissions to a Role
---

In order for Users to access a database through the EDC, they need to be assigned to a Role. On top of that, the Role must also have specific database Permissions applied to it. By default, all of the data in your database is not able to be seen until permissions are granted.  

To add Permissions to a Role, first click on the "Roles" link on the left-hand side of the page.  

Then, select the Role that you would like to add Permissions to. This will take you to that Role's Edit page.  

Once on the Edit page, click on the "Permissions" Tab. This tab will show you all of the permissions that are currently assigned to that Role. To add a Permission, click on the "Add Permission" button.  

This will take you to a new page with a form.  

The Type field determines whether the Role will be able to Read, Write, or Delete data from your database. The Connector is the name of the Connector that creates the connection to your database. The Schema Name allows you to select the Schema for your database. The Resource Type specifies whether you are granting access to a Table, View, or Stored Procedure. The Resource is the name of the specific Table, View, or Stored Procedure that you would like to grant access to. Finally, the Property field is the name of the column in your Table, View, or Stored Procedure. If you would like to grant rights to all columns, simply write "All_Properties." Once you have provided values for all the fields, click "Add Permission."  

If the EDC successfully creates the permission, you will be redirected back to the Role's Edit page which the new permission listed on the "Permissions" tab. Now users assigned to your Role can successfully make queries based on the Permission.