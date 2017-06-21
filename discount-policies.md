## WTT Discount policies
- Add fields:
 - is Agency to Contact
 - Package to SO
 - Is Discountable to Product

WTT is using many discount policies to determine the discount percent for each Order lines of SO. These policies could be devided into 3 type: 
 - Package: using a template SO to apply when creating SO. this template is also determined the fixed order lines with quantity and discount percent. 
 - Pre-signed contract: fixed discount percent for all order lines of children SOs of the contract
 - Regular: using table of discount percent and SO total value
