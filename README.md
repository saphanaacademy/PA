# Process Automation

Note that the code below is for a demo only (not production) and is subject to change.

### Custom Script 1

```javascript
let url = "/sap/opu/odata/sap/API_SALES_ORDER_SRV/A_SalesOrder" + "('" + SalesOrderNumber + "')";

return {
  'method': 'GET',
  'url': url,
  'responseType':'json', // parse the body of the result as a JSON object
  'resolveBodyOnly':true // get only the body of the response
};
```


### Custom Script 2

```javascript
var salesOrder = {salesOrderId:"", salesOrderAmount:0};
try {
  salesOrder.salesOrderId = obj.d.SalesOrder;
  salesOrder.salesOrderAmount = parseFloat(obj.d.TotalNetAmount,2);
  return(salesOrder);
} catch (error) {
    return(salesOrder);
}
```
