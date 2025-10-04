# View All Contacts
# 🟢TC-01
## User can view all contacts without any filters.
### Steps
- Navigate to the GET /contacts endpoint.
- Click on "Try it out" and then "Execute."
- Show the response and explain that it includes a list of all contacts.
### Expected Result
- The response includes a list of all contacts.
### Actual Result
- The response includes a list of all contacts.

# 🟢TC-02
## User can view contacts with pagination
## Test Data: page=1, limit=10
### Steps
- Navigate to the GET /contacts endpoint.
- Add query parameters for pagination 
- Execute and review the paginated response.
### Expected Result
- The response includes a paginated list of contacts.
### Actual Result
- The response includes a paginated list of contacts.

# 🟢TC-03
## User can view contacts with pagination
## Test Data: page=2, limit=10
### Steps
- Navigate to the GET /contacts endpoint.
- Add query parameters for pagination 
- Execute and review the paginated response.
### Expected Result
- The response includes a paginated list of contacts.
### Actual Result
- The response includes a paginated list of contacts.
  
# 🟢TC-04
## User can view contacts with pagination
## Test Data: page=1, limit=2
### Steps
- Navigate to the GET /contacts endpoint.
- Add query parameters for pagination
- Execute and review the paginated response.
### Expected Result
- The response includes a paginated list of contacts.
### Actual Result
- The response includes a paginated list of contacts.

# 🟢TC-05
## User can view contacts with search parameters.
## Test Data: "Email"
### Steps
- Navigate to the GET /contacts endpoint.
- Add a query parameter for search 
- Execute and show how the response filters contacts based on the search.

### Expected Result
- The response includes contacts matching the search criteria.
### Actual Result
- The response includes contacts matching the search criteria.
- Showing all the details of the contact.

# 🟢TC-06
## User can view contacts with search parameters.
## Test Data: "Firstname"
### Steps
- Navigate to the GET /contacts endpoint.
- Add a query parameter for search 
- Execute and show how the response filters contacts based on the search.

### Expected Result
- The response includes contacts matching the search criteria.
### Actual Result
- The response includes contacts matching the search criteria.
- Showing all the details of the contact.

# 🟢TC-07
## User can view contacts with search parameters.
## Test Data: "Lastname"
### Steps
- Navigate to the GET /contacts endpoint.
- Add a query parameter for search 
- Execute and show how the response filters contacts based on the search.

### Expected Result
- The response includes contacts matching the search criteria.
### Actual Result
- The response includes contacts matching the search criteria.
- Showing all the details of the contact.
- 
# 🔴TC-08
## Verify that the user can view contacts with search parameters (Invalid Contact email).
## Test Data: "email"
### Steps
- Navigate to the GET /contacts endpoint.
- Use an invalid ID in the GET /contacts/{email} endpoint.
- Execute and demonstrate the error message returned.
### Expected Result
- The response includes the error message.
### Actual Result
- The response includes contacts matching the search criteria.
- Showing all the details of the contact.
  
# Create New Contact
# 🟢TC-09
## User can create a new contact with valid details.
## Test Data 
```json
{
     "firstname": "Mohamed",
     "lastname": "Samir",
     "email": "mohamedelbehairy1@hotmail.com",
     "phone": "01155003316",
     "balance": "2"
     "username": "Mo"
   }
```
### Steps
- Navigate to the POST /contacts endpoint.
- Input valid data in the payload fields.
- Execute and show the success response.
### Expected Result
- A success message is returned, and the new contact is added to the contact list.
### Actual Result
- A success message is returned, and the new contact is added to the contact list.

# 🟢TC-10
## Create a new contact adding a query parameter.
## Test Data 
```json
{
     "firstname": "Mohamed",
     "lastname": "Samir",
     "email": "mohamedelbehairy1@hotmail.com",
     "phone": "01155003316",
     "balance": "2",
     "username": "Mo",
     "nickname": "MoMo"
   }
```
### Steps
- Navigate to the POST /contacts endpoint.
- Input valid data in the payload fields.
- Execute and show the success response.
### Expected Result
- The response includes an error message  status 400.
### Actual Result
- The response includes an error message  status 400.

# 🔴TC-11
## User can create a new contact with valid details.
## Test Data 
```json
{
     "firstname": "Mohamed",
     "lastname": "Samir",
     "email": "samir55486@gmail.com",
     "phone": "01155003316",
     "balance": "2"
     "username": "Mo"
   }
```
### Steps
- Navigate to the POST /contacts endpoint.
- Input valid data in the payload fields.
- Execute and show the success response.
### Expected Result
- A success message is returned, and the new contact is added to the contact list.
### Actual Result
- A success message is returned, and the new contact is added to the contact list.
But,The balance for the Contacts created have the same number, Despite entering different number in balance for each Contact.

# 🟢TC-12
## User cannot create a new contact with missing required fields.
## Test Data 
```json
{
     "firstname": "Mohamed",
     "lastname": "Samir",
     "email": "samir55486@gmail.com",
     "phone": "",
     "balance": "2"
     "username": "Mo"
   }
```
### Steps
- Send a POST request to the /contacts endpoint with missing details .
### Expected Result
- The response returns an error message indicating missing required fields.
- Error Massage Appered with missing details.
### Actual Result
- The response returns an error message indicating missing required fields.


# 🔴TC-13
## Another User can create another new contact with valid details..
## Test Data
```json
{
     "firstname": "Samir",
     "lastname": "Samir",
     "email": "mohamedelbehairy99@hotmail,com",
     "phone": "01155003319",
     "balance": "2"
     "username": "Mo"
   }
```
### Steps
- Navigate to the POST /contacts endpoint.
- Input valid data in the payload fields.
- Execute and show the success response.
### Expected Result
- A success message is returned, and the new contact is added to the contact list.
### Actual Result
- A success message is returned, and the new contact is added to the contact list.
But,The Username for the Contacts created have been generated by the software giving each contact same Username, Despite entering different varchar. in Username field for each Contact.

# 🔴TC-14
## Another User can create another new contact with valid details..
## Test Data
```json
{
     "firstname": "Samir",
     "lastname": "Samir",
     "email": "mohamedelbehairy99@hotmail,com",
     "phone": "01155003319",
     "balance": "2"
     "username": "Mo"
   }
```
### Steps
- Send a POST request to the /contacts endpoint with valid contact details.
### Expected Result
- A success message is returned, and the new contact is added to the contact list.
### Actual Result
- A success message is returned, and the new contact is added to the contact list.But The"ID" For the Created Contact should generated from the server not to be created by the User & Its not unique. Also all created contact have same ID number , Id num suppose to be unique.)

# 🔴TC-15
## User cannot create a new contact with missing required fields..
## Test Data
```json
{
     "firstname": "s55",
     "lastname": "smm",
     "email": "user@example11.com",
     "phone": "123456",
     "balance": "2"
     "username": ""
   }
```
### Steps
- Navigate to the POST /contacts endpoint.
- Input data with all required fields except "Username" field.
- Execute and demonstrate the error message returned.
### Expected Result
- A error message is returned, and the new contact is added to the contact list.
### Actual Result
- A success message is returned, and the new contact is added to the contact list.
- Despite the missing field "username".



# 🟢TC-16
## create a new contact with invalid phone number field..
## Test Data
```json
{
     "firstname": "s55",
     "lastname": "smm",
     "email": "user@example11.com",
     "phone": "tftuij",
     "balance": "2"
     "username": "djhd"
   }
```
### Steps
- Send a POST request to the /contacts endpoint with Invalid details.
- Input invalid Phone number containting alphabetic character.
### Expected Result
- The response returns an error message indicating invalid required field.
- Error Massage Appered with invalid details.
### Actual Result
- The response returns an error message indicating invalid required field.

# 🟢TC-17
## create a new contact with invalid phone number..
## Test Data
```json
{
     "firstname": "s55",
     "lastname": "smm",
     "email": "user@example11.com",
     "phone": "%$#$#@",
     "balance": "2"
     "username": ""
   }
```
### Steps
- Send a POST request to the /contacts endpoint with Invalid details.
- Input invalid Phone number containting Special character.
### Expected Result
- The response returns an error message indicating invalid required field.
- Error Massage Appered with invalid details.
### Actual Result
- The response returns an error message indicating invalid required field.

# 🟢TC-18
## create a new contact with invalid phone number..
## Test Data
```json
{
     "firstname": "s55",
     "lastname": "smm",
     "email": "user@example11.com",
     "phone": "1234^%$",
     "balance": "2"
     "username": ""
   }
```
### Steps
- Send a POST request to the /contacts endpoint with Invalid details.
- Input invalid Phone number containting Number & Special character.
### Expected Result
- The response returns an error message indicating invalid required field.
- Error Massage Appered with invalid details.
### Actual Result
- The response returns an error message indicating invalid required field.

# 🟢TC-19
## create a new contact with invalid phone number..
## Test Data
```json
{
     "firstname": "s55",
     "lastname": "smm",
     "email": "user@example11.com",
     "phone": "123yjhb",
     "balance": "2"
     "username": ""
   }
```
### Steps
- Send a POST request to the /contacts endpoint with Invalid details.
- Input invalid Phone number containting Number & alphabetic character.
### Expected Result
- The response returns an error message indicating invalid required field.
- Error Massage Appered with invalid details.
### Actual Result
- The response returns an error message indicating invalid required field.
  
# Request a Contact by Unique ID
# 🔴TC-20
## Verify that the user can request a contact using a valid unique ID.
## Test Data
```json
{
     "id": "3fb85e84-5717-4562-23fe-2c963f65afa9",
     

   }
```
### Steps
- Send a GET request to the /contacts/{id} endpoint, using a valid ID.
- Then Click Excute.
### Expected Result
- The response includes the details of the specified contact.
### Actual Result
- The response doesn't includes the details of the specified contact, giving details for another contacts since all contacts have the same id.
- How can i access data not related to my contact ?

# 🟢TC-21
## Verify that the user can request a contact without providing a contact ID.
## Test Data
```json
{
     "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
     

   }
```
### Steps
- Send a GET request to the /contacts/{id} endpoint, using a valid ID.
- Then Click Excute.
### Expected Result
- This test is shouldnt show any test result because a valid ID is required to fetch contact details.
### Actual Result
- No actual resul, since there's no action occured.
  
# Update Existing Contact
# 🔴TC-22
## Verify that the user can update an existing contact's information.
## Test Data
```json
{
     "id": "3fa85f64-5717-4562-b3fc-2c963f66afa9",
     

   }
```
### Steps
- Use the PUT /contacts/{id} endpoint with valid data (e.g.,balance num.& username).
- Execute and demonstrate the error message returned.
### Expected Result
- The response includes the details of the specified contact.
### Actual Result
- The response doesn't includes the details of the specified contact,it updates the balance but the username doesn't change or updated.

# 🔴TC-23
## Verify that the user can update an existing contact's information.
### Steps
- Use the PUT /contacts/{id} endpoint with valid data (e.g.lastname).
- Execute and demonstrate the error message returned.
### Expected Result
- The response includes the details of the specified contact.
### Actual Result
- The response includes 204 Msg of the specified contact,but the last name for the id doesn't change.
  
# 🟢TC-24
## Verify that the user cannot update a contact with invalid data.
## Test Data
```json
{
     "id": "3fa85f64-5717-4562-b3fc-2c963f66afa",
     

   }
```
### Steps
- Send a PUT request to the /contacts/{id} endpoint with invalid data.
- Click Excute.
### Expected Result
- The response returns an error message indicating the invalid data.
### Actual Result
- There's no excution for the invaild id.

# Remove Contacts
# 🔴TC-25
## Verify that the user can remove an existing contact.
## Test Data
```json
{
     "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
     

   }
```
### Steps
- Use the DELETE /contacts/{id} endpoint with a valid ID.
- Execute and show the success response confirming removal.
### Expected Result
- A success message is returned, and the contact is removed from the contact list.
### Actual Result
- A success message is returned,but all contacts with the same id still exist in database & didn't remove.

# 🟢TC-26
## Verify that the user receives an error when trying to remove a non-existent contact.
## Test Data 
```json
{
     "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
     

   }
```
### Steps
- Send a DELETE request to the /contacts/{id} endpoint with a invalid contact ID.
- Execute and demonstrate the error message returned.
### Expected Result
-The response returns an error message indicating the contact does not exist.
### Actual Result
The response returns an error message indicating the contact does not exist.
  

# Add Amount to Contact's Balance
# 🔴TC-27
## Verify that the user can add a specific amount to a contact's balance.
## Test Data
```json
{
     "id": "3fa85f64-5717-4562-b3fc-2c963f66afa9",
     "amount": "1",

   }
```
### Steps
- Send a PATCH request to the /contacts/{id}/balance endpoint with the amount to be added.
- Then Click Excute.
### Expected Result
-A success message is returned, and the contact's balance is updated accordingly.
### Actual Result
-  The software add wrong amount to the balance.if i add 3 to the amount the software made it 6 it doubles the number then added it to the balance.

# 🟢TC-28
## Verify that the user can add a specific amount to a contact's balance.
## Test Data
```json
{
     "id": "3fa85f64-5717-4562-b3fc-2c963f66afa9",
     "amount": "-1",

   }
```
### Steps
- Verify that the user cannot add a negative amount to a contact's balance.
- Then Click Excute.
### Expected Result
-end a PATCH request to the /contacts/{id}/balance endpoint with a negative amount.
### Actual Result
- The software accepts the negative amount.
  
 
