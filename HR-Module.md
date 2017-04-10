## This description is for Employee and Recruitment Module in HR Dep

After testing with Employee and Recruitment Module of Odoo, below are adjustments, improvements and also the profile permission definition

1. Profiles
 
 - HR Manager
 - HR Senior
 - HR Executive

2. Employee module
 
  - Home Address: change it into text field.
  - When creating a new user, if user is linked to an employee which is already link to a partner, it's not needed to create a new partner for this user, and use the current partner insteads.
  
3/ Recruitment module
- Merge "Subject / Application Name" and "Applicant's Name" => "Applicant's Name"
- Remove "Contact" field
- Change "Responsible" => "Manager"
- Add "HR staff" field below "Manager" field (to choose HR staff operating this application)
- Add "Applications" below "Job Positions" to menu for viewing all applications in Kanban viewstyle

4/ Permission

Levels: HR Executive < HR Senior < HR Manager < Admin.

The rules is that the higher level has the permissions the lower levels have + the permissions of its level. Profile Admin has full permissions as default.

 a) Employee module
- Department object:
    + HR Executive = HR Senior: View, Create
    + HR Manager: Edit, Delete
- Employee object
    + HR Executive = HR Senior: View, Create
    + HR Manager: Edit, Delete
- Contract object
    + HR Manager: View, Create, Edit, Delete
    
b) Recruitment module
- Job Position object:
     + HR Executive: View, Create
     + HR Senior: Edit, Delete
     + HR Manager: Start/Stop Recruitment
- Application object
     + HR Executive: View, Create
     + HR Senior: Edit, Create Employee, Refuse
     + HR Manager: Delete
