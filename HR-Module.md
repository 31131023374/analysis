## This description is for Employee and Recruitment Module in HR Dep

After testing with Employee and Recruitment Module of Odoo, below are adjustments, improvements and also the profile permission definition

1. Profiles
 - HR Manager
 - HR Senior
 - HR Executive

2. Employee module
 - Banking account number:  
    + Allow HR to Create new; 
    + When create new employee, Account holder is, by default the being-created employee (now only can choose from created employees)
    + Account Holder: change it into text field
 - Home Address: change it into text field.

3/ Recruitment module
- Merge "Subject / Application Name" and "Applicant's Name" => "Applicant's Name"
- Remove Contact field
- Change "Responsible" => "Manager"
- Add "HR staff" field below "Manager" field ( to choose HR staff operating this application)
- Add "Applications" to menu for viewing all application in Kanban viewstyle

4/ Permission

Levels: HR Executive < HR Senior < HR Manager < Admin.

The rules is that the higher level has the permissions the lower levels have + the permissions of its level. Profile Admin has full permission as default.

  a) Employee module
- Department object:
    + HR Executive = HR Senior: View, Create
    + HR Manager: Edit, Delete
- Employee object
    + HR Executive = HR Senior: View, Create
    + HR Manager: Edit, Delete
- Contract
    + HR Manager: View, Create, Edit, Delete
 b) Recruitment
- Job Position object:
     + HR Executive: View, Create
     + HR Senior: Edit, Delete
     + HR Manager: Start/Stop Recruitment
- Application object
     + HR Executive: View, Create
     + HR Senior: Edit, Create Employee, Refuse
     + HR Manager: Delete
