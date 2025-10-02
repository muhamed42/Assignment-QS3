* View List of Invoices
# TC-01
## Verify that the user can view a list of invoices associated with their account.
### Steps
- Navigate to the GET /invoices endpoint.
- Click on "Try it out" and then "Execute."
- Show the response and explain that it includes a list of invoices returned in the response.
### Expected Result
- The response includes a list of all invoices.
### Actual Result
- The response includes a list of all invoices.

* Create New Invoice
# TC-02
## Verify that the user can create a new invoice with valid details.
### Steps
- Input valid details in the payload.
- Click on 'Try it out', fill in the necessary details, and execute."
- The response should indicate that the invoice was created successfully.
### Expected Result
- The response should indicate that the invoice was created successfully.
### Actual Result
- A new invoice is created, and the response indicates success.
- But it has a wrong "Username" not as i entered while create invoice, Also all Invoices that have been created have same "Username*.(Failed)

  
# TC-03
## Verify that the user can create a new invoice with valid details with missing fields.
### Steps
- Input valid details in the payload with missing fields(createdby)
- Click on 'Try it out', fill in the necessary details, and execute."
- The response should indicate that the invoice wasn't created successfully.
### Expected Result
- The response should indicate that the invoice wasn't created successfully.
### Actual Result
- The response should indicate that the invoice wasn't created successfully.
- As Excpected.

# TC-04
## Verify that the user can create a new invoice with valid details with negative amount in cost fields.
### Steps
- Input negative amount in the payload with cost field.
- Click on 'Try it out', fill in the necessary details, and execute."
- The response should indicate that the invoice wasn't created successfully.
### Expected Result
- The response should indicate that the invoice wasn't created successfully.
### Actual Result
- The response should indicate that the invoice wasn't created successfully.
- required not ot put negative sign.

# TC-05
## Verify that the user can create a new invoice with valid details with negative amount in discount fields.
### Steps
- Input negative amount in the payload with discount field.
- Click on 'Try it out', fill in the necessary details, and execute."
- The response should indicate that the invoice wasn't created successfully.
### Expected Result
- The response should indicate that the invoice wasn't created successfully.
### Actual Result
- The response should indicate that the invoice wasn't created successfully.
- required not ot put negative sign & discount% should be between 0 t0 100.

# TC-06
## Verify that the user can create a new invoice with valid details with amount in discount fields.
### Steps
- Input amount 101 in the payload with discount field. 
- Click on 'Try it out', fill in the necessary details, and execute."
- The response should indicate that the invoice wasn't created successfully.
### Expected Result
- The response should indicate that the invoice wasn't created successfully.
### Actual Result
- The response should indicate that the invoice wasn't created successfully.
- required discount % should be between 0 t0 100.

# TC-07
## Verify that the user can create a new invoice with valid details with negative amount in tax fields.
### Steps
- Input negative amount in the payload with cost tax .
- Click on 'Try it out', fill in the necessary details, and execute."
- The response should indicate that the invoice wasn't created successfully.
### Expected Result
- The response should indicate that the invoice wasn't created successfully.
### Actual Result
- The response should indicate that the invoice wasn't created successfully.
- required not ot put negative sign.

# TC-08
## Verify that the user can create a new invoice with valid details with amount cost fields.
### Steps
- Input negative amount in the payload with cost(01) .
- Click on 'Try it out', fill in the necessary details, and execute."
- The response should indicate that the invoice wasn't created successfully.
### Expected Result
- The response should indicate that the invoice wasn't created successfully.
### Actual Result
- The response should indicate that the invoice wasn't created successfully.
- Invalid leading zero before '1'

 # TC-09
## Verify that the user can create a new invoice with valid details with amount cost fields.
### Steps
- Input negative amount in the payload with cost(a) .
- Click on 'Try it out', fill in the necessary details, and execute."
- The response should indicate that the invoice wasn't created successfully.
### Expected Result
- The response should indicate that the invoice wasn't created successfully.
### Actual Result
- The response should indicate that the invoice wasn't created successfully.
- 'a' is an invalid start of a value

* View Invoice Details
# TC-09
## Verify that the user can view detailed information of a specific invoice using a valid ID.
### Steps
- GET /invoices/{id} endpoint.
- "Click 'Try it out', enter the ID, and hit 'Execute.' The response should provide the invoice details."
### Expected Result
- The response contains detailed information for the specified invoice.
### Actual Result
- The response contains worng & an invoice details for the inserted id invoice.(Failed  

# TC-10
## Verify that the user can view detailed information of a specific invoice using a invalid ID.
### Steps
- GET /invoices/{id} endpoint.
- "Click 'Try it out', enter the invalid ID, and hit 'Execute.' The response shouldn't provide the any invoice details."
### Expected Result
- The response returns an error message.
### Actual Result
- The response returns an error message.

# TC-11
## Verify that the user can view detailed information of a specific invoice using a non-existence ID.
### Steps
- GET /invoices/{id} endpoint.
- "Click 'Try it out', enter the non-existence ID, and hit 'Execute.' The response shouldn't provide the any invoice details."
### Expected Result
- The response returns an error message.
### Actual Result
- The response with a invoice details is appeared,instead that the id is non-exist in database.(Failed)

# TC-12
##  Verify that the software can Calculate Total Profit & Total Amount, while create a new invoice with all valid details.
### Steps
- POST /invoices endpoint.
- "Click 'Try it out', enter the valid details in fields , and hit 'Execute.' The Create an invoice and verify profit calculation.
### Expected Result
- Check the response to ensure the profit amount is accurate.".
### Actual Result
- After creating an invoice, we found that that the total profit is calculated uncorrectly.
- After creating an invoice, we found that that the total profit is calculated uncorrectly.(Failed)

  
* Return Existing Invoice
# TC-13
## Verify that the user can return an existing invoice.
### Steps
- POST /invoices/{id}/return endpoint.
- "Click 'Try it out', enter the invoice ID, and hit 'Execute.'
### Expected Result
- The invoice is marked as returned, and the contact's balance is adjusted.
### Actual Result
- Executed and observed the error message "Cannot return a paid invoice".(Failed)
  
* Pay Invoice
# TC-14
##  Verify that the user can pay a specific invoice with a valid amount.
### Steps
- POST /invoices/{id}/pay endpoint.
-  enter a valid invoice ID, let’s pay a specific invoice with a valid amount." and hit 'Execute.'
### Expected Result
- The invoice is marked as paid, and the payment amount is added to the contact's balance.
### Actual Result
- The response returns Error: response status is 400 with response body"Invoice is already paid."(Failed)

# TC-15
##  Verify that the user can pay a specific invoice with a valid amount for non-exsitence Id invoice .
### Steps
- POST /invoices/{id}/pay endpoint.
-  enter a invalid invoice ID, let’s pay a specific invoice with a valid amount." and hit 'Execute.'
### Expected Result
- The response returns an error message non-existence Id invoice
### Actual Result
- The response returns Error: response status is 400 with response body"Invoice is already paid."(Failed)
