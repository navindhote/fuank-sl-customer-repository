Knauf - MuleSoft Senior Developer Task

1. Purpose

Fuank, a global hardware manufacturing company in China, implements a new strategic collaboration model with its resellers across the globe. External reseller e-commerce systems now should be able to share details of end-customers with Fuank’s CRM (Salesforce). Such transparent data exchange process will create additional trust and improve quality and speed of the support.

2. General Description

When new customer orders a hardware from a reseller’s e-commerce system, the customer data will be also pushed to Fuank’s endpoint via REST API. Fuank is also able to provide customer data to their resellers, if needed. Due to the fact, that current CRM implementation has limited functionality, part of Customer data should be stored in Cosmos DB.

3. Assumptions

only 1 API is enough (i.e. Customer API)

Customer API is responsible for customer id generation (GUID)

4. Functional requirements

Number

Description

1

Reseller can create a customer

2

Reseller can update the customer

3

Reseller can retrieve the customer by CustomerID

5. Non-functional requirements

Number

Description

1

If one of destination systems is unavailable, none of customer data should be accepted

2

Anypoint Monitoring (and logging) is used

3

Resellers are authorized using basic authentication

4

There is at least one positive and negative test case for each use case

6. Data model

Salesforce customer object

{
  "customerId": "4d4de7d6-7f5e-4778-9c70-babba6c25c55",
  "firstName": "Ulrich",
  "lastName": "Nielsen",
  "companyName": "E-ffoc",
  "email": "ulrichN@effoc.com",
  "phone": "+494341927420"
}


CosmosDB customer object

{
  "customerId": "4d4de7d6-7f5e-4778-9c70-babba6c25c55",
  "personalInformation": {
    "firstName": "Ulrich",
    "lastName": "Nielsen",
    "companyName": "E-ffoc",
    "email": "ulrichN@effoc.com",
    "phone": "+494341927420"
  },
  "address": [
    {
      "street": "Steinbrueckstrasse",
      "houseNumber": 114,
      "city": "Nuremberg",
      "country": "Germany",
      "postalCode": "90408"
    }
  ]
}

7. Additional requirements

While submitting code, please provide a guide or steps to perform above actions (something similar to readme.md).

Adhere to certain naming standards in RAML and Mule project.

