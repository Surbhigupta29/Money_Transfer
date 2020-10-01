## MoneyTransferApp
This application is a REST-based API that enables transfer of money from one bank account to another. The money transfers are inherently transactional in nature.

## Getting Started
Just Git-Pull the files and run ```npm install``` then start the server using ```npm start```.

## Prerequisites
NodeJS must be installed.

## Rest APIs
### Customer

/customer  
- This is a **POST** endpoint for creating customer record wih the fields required: customerName, pancard. 

/customer
- This is a **GET** endpoint which retrieves all customer records.

### Account

/account
- This is a **POST** endpoint for creating account for an existing customer wih the fields: customerId, AccountType, amount. 

/account
- This is a **GET** endpoint for retrieves all account records of all customers. 

/account/transacions
- This is a **PUT** endpoint. 
It takes input: ```fromAccountId, toAccountId, amount``` from request body.
The successful repsonse gives the follwing feilds: ```newSrcBalance, totalDestBalance, transferedAt```

## Notes 
Account types are ‘Savings’, ‘Current’ and ‘BasicSavings’. A single user can have multiple such accounts. 

The following rules apply:
* Transfer between accounts belonging to the same user is not allowed.
* The balance in ‘BasicSavings’ account type should never exceed Rs. 50,000
* Source account should have the required amount for the transaction to succeed

### Postman Link
- https://www.getpostman.com/collections/a816887d6151dac3a0ee