## WTT Discount policies

WTT is using many discount policies to determine the discount percent for each Order lines of SO. These policies could be devided into 3 type: 
 - Package: using a template SO to apply when creating SO. this template is also determined the fixed order lines with quantity and discount percent. 
 - Pre-signed contract: fixed discount percent for all order lines of children SOs of the contract
 - Ordinary: bases on SO total value and the customer type to determine the discount percent (by indexing a table). The bigger value, the bigger discounnt.

Base on current system, here are new key functions
 - "Customer type" field in Contacts. 2 values: (default) "Agency", "Direct"
 - Package (template SO): add a new item in "Sales" Menu, above Contract. The package form is the same to So form but there is only one button in nav bar: "Create SO" (clone a new SO from this template SO). In the SO form, also add new field : "Package" to show linked package.
 - "Is discountable" field in Product. 2 values: True / False.
 - At bottom of the form, show the description of discount "Discount from package [Name]" / "Discount from contracts [Percent]%" / "Discount for [Customer Type] with [Percent]%"
 
 Use case description: When creating new SO, user can choose 3 options:
 - If user picks a contract to link, use discount percent of the selected contract to apply. (Pre-signed type)
 - If user picks a package to link, load all contents of the selected package to SO (overwrite). (Package type)
 - If neither of above options are picked, the discount percent is re-calculated every times Order lines change bases on Total and Customer type. Example table:  (Ordinary type)
  
|Total   | Agency  | Direct  |
|--------|---------|---------|
|< 10M   |   15%   |   10%   |
|   10M - 50M |   20% |  15% |
| > 50M  | 25%  | 20%  |
 
There is also some global rules:
 - if the product is not "discountable", the discount is always 0%
 - if the payment term is "Immediate Payment" and type is Ordinary, plus 5% discount percent to all. 
