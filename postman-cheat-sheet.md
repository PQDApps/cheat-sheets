# Postman Cheat Sheet
Small Cheat Sheet for testing API's using Postman Tests section.
Official documentation can be found here -> https://learning.postman.com/docs/writing-scripts/intro-to-scripts/


```javascript
// Set, Get & Unset Environment Variable
pm.environment.get("variable_name");
pm.environment.set("variable_name", "variable_value");
pm.environment.unset("variable_name");

// Set, Get & Unset Globar Variable
pm.globals.get("variable_name");
pm.globals.set("variable_name", "variable_value");
pm.globals.unset("variable_name");

// Set, Get & Unset Variable
pm.collectionVariables.get("variable_name");
pm.collectionVariables.set("variable_name", "variable_value");
pm.collectionVariables.unset("variable_name");

// Get a Variable (Any Scope)
pm.variables.get("variable_name");

// Use a Variable (Var inside double curly braces)
{{variable_name}}

// Access JSON Response
var jsonResponse = pm.response.json();

// XML to JSON
var jsonObject = xml2Json(responseBody);

// Test Function
pm.test("Test Name", function () {
  /**
  * Below are possible test validations
  */

  // Status Code Check
  pm.response.to.have.status(200);

  // Status Code Check with multiple codes
  pm.expect(pm.response.code).to.be.oneOf([201,202]);

  // Status Code has string (OK, Created, Bad Request, etc.)
   pm.response.to.have.status("Created");

  // Response contains string
  pm.expect(pm.response.text()).to.include("string_you_are_looking_for"); 

  // JSON value equals something
  pm.expect(jsonResponse.value).to.eql(1988);

  // Verify response has a specific header
  pm.response.to.have.header("Content-Type");

  // Response time below amount of milliseconds (200ms in example)
  pm.expect(pm.response.responseTime).to.be.below(200);
});
```
