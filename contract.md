
## Main Information:
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

## Tab Contract line:
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
 
## Tab Other Information
- Salesperson (R)
- Sales Team  (R)
- Company     (O)
- Tags        (O)

## Status: 
Draft -> In-Progress -> Done -> Canceled

- Status is set to In-Progress when contract is confirmed (only by profile Adminnistration)
- Status is set to Done when Cumulative Total >= Min Value

## Buttons in Header line:
- Create SO (only show when status is In-Progress)
- Confirm
- Cancel
- Set to Done

## In SO view

Also add a new field, Contract, for user to choose and view linked contract. 

## Permission:
The same rules as Sales Order:
- Administration profile has full permission
- Owner of Contract is salesperson set to Salesperson field. 
  + Can read, edit, cancel, set to done  
  + Create sales orders from contract
  + Add/Remove followers
- Follower can:
  + Read contract and all its sales orders
  + Create sales orders from contract

## Create Sales Order from Contract
- Information to be transfered:
  + Customer          
  + Order Date       
  + Pricelist         
  + Industry Sector
  + Brand(s)         
  + Discount Benefit (only percent, not fixed amount)
- Constraints:
  + Sales person of sales order is set to current user
  + Owner of Contract is always set as follower of sales order
  + Check if total with taxes of SO is bigger than Remain Value, if yes, force user to confirm (by OK/Cancel message box) before creating
  
