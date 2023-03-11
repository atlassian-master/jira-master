**Goal:**
The value of JIRA field will be appended instead of overwriting; the value of JIRA field will be depending on other field.

**Background:**

By default, JIRA field will be replaced with new value. 

There is a case that the field needs to be appended a new value, and the old value will be still existing without replacing or overwritting.

For example, we have a field called "Solution History", and each time the "Solution" value is updated, the "Solution History" will have the latest value of "Solution" added and also keep the old value  of "Solution History". This case is usable when workflow of the issue goes to reopen and second "Solution" or more "Solution" is needed to enter. The "Solution History" will help keep track fo the changes.

**Skills Used:**
1. Automation : 
2. Smart Value: Please refer to: https://support.atlassian.com/cloud-automation/docs/jira-smart-values-issues/

**Implementation:**
1. Create custom field.
2. Setup the Automation Rule.
   a. Add condition when the "Solution" field is modified
   b. Add action of "Edit issue fields" on "Solution History" field.
   c. Enter the value:
   ```
      {{now}}: 

      {{fieldChange.toString}}

      {{issue.Solution History}}
   ```

3. Save and enable the Automation rule.


**Youtube Video**
https://youtu.be/ynR1WLeMHLA
