---
id: using-the-dashboard
title: Using the Dashboard
sidebar_label: Using the Dashboard
---

## Overview    


The EDC dashboard allows users to view important high-level information quickly.  

Once the DLL has been installed, boot up your project and add '/edc' to the end of your URL. The EDC dashboard will automatically compile itself and load.

![Dashboard](/docs/assets/dashboard.png)

The top of the dashboard shows the number of database requests the EDC has received today, the number of unique IP Addresses that have requested data, and the number of failed requests.  

Beneath the scoreboard, there are two graphs. On the left, a pie chart which shows a quick breakdown of the day's requests. Hovering over the pie chart shows how many GET, POST, PUT, and DELETE requests the EDC has received today. On the right, there is a bar graph which shows a breakdown of the past week and the number of requests received each day.  

Underneath the graphs, there is a table showing the 10 most recent requests. Clicking on the requests brings up a modal which shows more in-depth information. Hitting the refresh button on the top of the table will check for any new requests that have come in without having to reload the page.
