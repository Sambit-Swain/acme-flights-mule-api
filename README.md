# acme-flights
 
MuleSoft ACME Travel API (Mobile) exposes an end-point to perform below operations:
1. Retrieve all available flights scheduled
2. Search for all available flights scheduled on a date (ex- 2021-04-23)
3. Search for all destinations an airlines is allocated, and paginate the display having list size 10
4. Allow to purchase a ticket for a scheduled flight and reduce the seat availability by 1
5. Allow to allocate a new scheduled flight journey
6. Allow to amend the price of the flight travel

Development made:
1. mUnits has not been placed as its a PoC
2. Exception and error handling has been done where required
3. Error message would be passed in response in case of failure and added a sensible error description

Steps to set-up this PoC on local machine anypoint studio:
1. RAML API Specification has been added in src/main/resource/api path, and referred to this file in APIKit router
2. Secret key has been abstracted in mule-artifact.json
3. mUnit runtime container has been allocated in pom.xml for running mUnits during maven build process and perform direct deployment to cloudHub
4. All above business logic operations are set in different flows so that Mule would instantiate them separately.
5. Only meaningful logging has been added to each flow paths
6. Sensitive information is added to ${env}-secured.properties file with AES encrypted algo
7. Environment and Key token has been directly added on global.xml file for easy set-up
8. All configurations are added only to global.xml file
9. Basic error handler flow provided to handle common API error scenarios