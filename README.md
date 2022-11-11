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
### Test URL, S/4HANA Cloud Sales Order API

Top 5 Sales Orders by Total Net Amount

```javascript
https://<your system name>-api.s4hana.ondemand.com/sap/opu/odata/sap/API_SALES_ORDER_SRV/A_SalesOrder?$top=5&$orderby=TotalNetAmount%20desc
```

### Custom Script, Get Values from Response Object

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
