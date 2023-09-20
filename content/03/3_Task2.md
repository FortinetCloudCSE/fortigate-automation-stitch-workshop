---
title: "Task 2 - Automation Action"
chapter: true
weight: 3
---

### Task 2 - Create Automation Action

This task creates the action to send an email indicating the Admin activity.

1. **Click** "Action"
1. **Click** "Create New"
1. **Scroll** to the Notifications actions
1. **Click** "Email"

  ![stitchtask2](../images/stitch_task2-01.jpg)
  ![stitchtask2](../images/stitch_task2-02.jpg)

1. **Enter**
    * Name: "Admin activity action"
    * From: "USERXX@ftg.com" <-- does not need to be a valid email
    * To: a valid email address to receive the email
    * Subject: "Admin activity"
1. **Click** OK

  ![stitchtask2](../images/stitch_task2-03.jpg)
  ![stitchtask2](../images/stitch_task2-04.jpg)

### Task 3 - Create Automation Stitch

1. **Click** "Action"
1. **Click** "Create New"

  ![stitchtask3](../images/stitch_task3-01.jpg)

1. **Enter**
    * Name: "Admin activity stitch"
1. **Click** "Add Trigger"
1. **Click** "Admin activity trigger" in "Select Entries"
1. **Click** "Apply"
1. **Click** "Add Action"
1. **Click** "Admin activity action" in "Select Entries"
1. **Click** "Apply"
1. **Click** "OK"

  ![stitchtask3](../images/stitch_task3-02.jpg)
  ![stitchtask3](../images/stitch_task3-03.jpg)
  ![stitchtask3](../images/stitch_task3-04.jpg)

### Task 4 - Test the Automation Stitch

1. **Logout**
1. **Login** with an incorrect password
1. **Login** with an the correct password

  ![stitchtask4](../images/stitch_task4-01.jpg)
