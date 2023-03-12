#####  Goal:

  Automatically assign the issue according to the sepecified condition

##### Youtube Video:

##### Background:

   - By default, JIRA assignee can only be assigned to project lead or component lead or keeping unassigned.

   - There is a case that the assigned should be assgined by the checking the value of existing fields, such as priority, summary/description text, labels etc.

##### Skills Used:

  - Script runner
  - Worflow post function
  - Groovy scripting


##### Implementation:

  - Define the workflow and add the post function.

  - Add the custom script in the postion function:
```
import com.atlassian.jira.issue.CustomFieldManager
import com.atlassian.jira.component.ComponentAccessor
import com.atlassian.jira.issue.fields.CustomField
import com.atlassian.jira.issue.MutableIssue
import org.apache.log4j.Logger
import org.apache.log4j.Level

def log = Logger.getLogger("com.acme.priority")
log.setLevel(Level.DEBUG)

def p_value =  issue.getPriority().getString("name")

log.debug('The issue priority value is: ' + p_value)

if(p_value.equals('High')){
    def user = ComponentAccessor.userManager.getUserByName('user2')
    log.debug('Setting the assignee to: ' + user.toString())
    issue.setAssignee(user)
}

if(p_value.equals('Highest')){
    def user = ComponentAccessor.userManager.getUserByName('manager1')
    log.debug('Setting the assignee to: ' + user.toString())
    issue.setAssignee(user)
}




```
  - Save the workflow and test.
