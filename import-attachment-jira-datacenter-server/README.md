#####  Goal:

 Import JIRA issue via csv, with attachments
 
##### Youtube Video:

 please subscribe and click like if you really like it, it will encourage me to do more valuable things. Thanks.

##### Background:

   - JIRA csv import is frequently used by importing data from external system into JIRA, including rememdy, Rally, HP ALM etc.

   - How to import attachments within csv is a critical problem
   
##### Skills Used:

  - Linux copy command, scp or ftp
  - JIRA csv import



##### Implementation:


  - Prepare the attachment file, copy the attachments on JIRA instance:
  - Prepare the csv file, the attachment can be set multiple columns if issue has multiple attachments. The count of attachment column depends on the **max** value of attachments count of each issue. In our example in youtube, the column of **Attachment** is 3 since one of the issue has 3 attachments, all the other issues have less than 3 attachments
  - Save the csv and run import.
