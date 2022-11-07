# Process Automation

Note that the code below is for a demo only (not production) and is subject to change.

### Custom Script, Call Web Service With Destination Options

```javascript
let url = "/sap/opu/odata/sap/API_SALES_ORDER_SRV/A_SalesOrder" + "('" + salesOrder + "')";

return {
  'method': 'GET',
  'url': url,
  'responseType': 'json', // parse the body of the result as a JSON object
  'resolveBodyOnly': true // get only the body of the response
};
```


### Custom Script

```javascript
var objValues = {SalesOrder:"", TotalNetAmount:0};
try {
  objValues.SalesOrder = obj.d.SalesOrder;
  objValues.TotalNetAmount = parseFloat(obj.d.TotalNetAmount,2);
  return(objValues);
} catch (error) {
    return(objValues);
}
```
