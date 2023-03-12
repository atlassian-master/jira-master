#####  Goal:

  Automatically close the parent issue when subtasks are all closed.

##### Youtube Video:

 https://youtu.be/G-uY1PCLeEk Please subscribe and click like if you really like it, it will encourage me to do more valuable things. Thanks.

##### Background:

   - By default, when all subtasks are closed, the parent issue will be still isolated. It is quite helpful to automatically close the parent issue to have a better SLA in report.

##### Skills Used:

  - Script runner
  - Worflow post function


##### Implementation:

  - Define the workflow and add the post function to "Closed" transition of sub task issue type.

  - Add the post function "Transition parent when all subtasks are resolved", and select the right transition ID for workflow of parent issue.

  - Save the workflow and test.
