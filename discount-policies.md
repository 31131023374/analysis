## WTT Discount policies
- Add fields:
 - is Agency to Contact
 - Package to SO
 - Is Discountable to Product

WTT is using many discount policies to determine the discount percent for each Order lines of SO. These policies could be devided into 3 type: 
 - Package: using a template SO to apply when creating SO. this template is also determined the fixed order lines with quantity and discount percent. 
 - Pre-signed contract: fixed discount percent for all order lines of children SOs of the contract
 - Ordinary: bases on SO total value and the customer type to determine the discount percent (by indexing a table). The bigger value, the bigger discounnt.

Base on current system, here are new key functions
 - "Customer type" field in Contacts. 2 values: (default) "Agency", "Direct"
 - Package (template SO): add new item in Sales Menu, similar to SO form but there is only one button in nav bar: "Create SO" (clone a new SO from this template SO.
