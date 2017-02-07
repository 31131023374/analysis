
#Main Information:
- Contract ID       (R)
- Customer          (R)
- Order Date        (R)
- Pricelist         (O)
- Start Date        (O)
- End Date          (O)
- Industry Sector   (O)
- Brand(s)          (O)
- Min value         (R)
- Max value         (O)
- Discount Benefit (percent and fixed amount) (O)

(O): Optional
(R): Required

#Tab Contract line:
  Each line is a sales order linked to current contract, including following fields:
- SO ID
- Order Date
- Sales Person
- Total
- Total Discount
- Total After Discount
- Taxes
- Total with taxes
- Is All Tasks Done?

At footer of table, show 
- Cumulative total (sum of all Total with taxes)
- Remain Value = Min Value - Cumulative total.

#Tab Other Information
- Salesperson (O)
- Sales Team  (O)
- Company     (O)
- Tags        (O)

#Status: 
New - Doing - Done - Canceled 

#Buttons in Header line:
- Create SO
- Cancel
- Set to Done

#Permission:
The same rules as Sales Order:
- Administration profile has full permission
- Owner of Contract is salesperson set to Salesperson field. 
  + Can read, edit, cancel, set to done  
  + Create sales orders from contract
  + Set/Delete followers
- Follower can:
  + Read contract and all its sales orders
  + Create sales orders from contract
- Open contracts: contracts not be set salesperson
  + Administration profile: Full permission
  + Others: permission as a follower

#Create Sales Order from Contract
- Information to be transfer:
  + Customer          
  + Order Date       
  + Pricelist         
  + Industry Sector
  + Brand(s)         
  + Discount Benefit
- Constraint:
  + Sales person of sales order is set to current user
  + Owner of Contract is always set as follower of sales order
  + Check if total with taxes of SO is bigger than Remain Value, if yes, force user to confirm before create
  
