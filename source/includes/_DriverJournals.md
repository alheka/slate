# Driver Journals
## Get Driver Journals

```shell
curl "https://app.seventime.se/api/2/driverJournals/?limit=5&page=1" \
  -H "Client-Secret: thisismysecretkey" \
  -H "Content-type: application/json"
```

```javascript
/* Sample with the request library */

let url = "https://app.seventime.se/api/2/driverJournals/?limit=5&page=1";
let options = {
  url: url,
  headers: {
    "Client-Secret": "thisismysecretkey",
    "Content-Type": "application/json",
    "Accept": 'application/json'
  }
};

request(options, function(error, response, body) {
  if (!error && response.statusCode == 200) {
    let info = JSON.parse(body);
    // ...
  } else {
    console.error("Error when calling API! HTTP Code: " + response.statusCode + ", Error message: " + body.errorMessage);
  }  
});
```

> The above command returns JSON structured like this:

```json
{
  "meta": {
    "totalResources": 87,
    "totalPages": 18,
    "currentPage": 2
  },
  "data": [
    {
      "_id": "5613c0eabed82c732b54312",
      "name": "",
      "driverJournalItemType": "574ed84219e78125333213578b",
      "driverJournalItemTypeName": "4 kr/km",
      "car": null,
      "carRegistrationNumber": "ABC123",
      "description": "",
      "user": "5f48eb3e65d7eeb491836d",
      "userName": "Anna Andersson",
      "customer": "5bb26376c42fb9929932161",
      "customerName": "Company AB",
      "project": "5f924f4f533f103176210",
      "projectName": "Tester",
      "workOrder": "5bae34dca878bd7d0182b",
      "workOrderTitle": "20160525",
      "workOrderNumber": 1181,
      "startAddress": "Östra Gatan 129, Stockholm",
      "endAddress": "Västra Gatan 921, Stockholm",
      "travelPurpose": ".",
      "startOdometer": 156,
      "endOdometer": 178,
      "totalDistance": 22,
      "price": 4,
      "totalAmount": 88,
      "isInvoiced": true,
      "invoice": "5fab29b038bd33301751",
      "modifiedDate": "2016-06-17T09:29:01.958Z",
      "createDate": "2016-06-17T09:20:46.845Z",
      "isInvoiceable": true,
      "timestamp": "2016-06-17T09:20:10.254Z"
    },
    {
      // ...
    }
  ]
}
```

This endpoint retrieves driver journals.

### HTTP Request

`GET https://app.seventime.se/api/2/driverJournals`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
projectName                 |  | If specified, driver journals that match the parameter will be included.
customerName                |  | If specified, driver journals that match the parameter will be included.
driverJournalItemTypeName   |  | If specified, driver journals that match the parameter will be included.
isInvoiceable               |  | If specified, driver journals that match the parameter will be included.
workOrderTitle              |  | If specified, driver journals that match the parameter will be included.
workOrderNumber             |  | If specified, driver journals that match the parameter will be included.
carRegistrationNumber       |  | If specified, driver journals that match the parameter will be included.
startAddress                |  | If specified, driver journals that match the parameter will be included.
endAddress                  |  | If specified, driver journals that match the parameter will be included.
fromDate                    |  | If specified, driver journals registered after or on this date will be included. The date has to be in the format 'YYYY-MM-DD'
toDate                      |  | If specified, driver journals registered before or on this date will be included. The date has to be in the format 'YYYY-MM-DD'
sortBy                      |  | If specified, a sort will be made on the specified parameter
sortDirection               |  | "ascending" or "descending". If specified and sortBy is specified the sort order will be ascending or descending




## Get a specific Driver Journal

```shell
curl "https://app.seventime.se/api/2/driverJournals/5613c0eabed93172591b" \
  -H "Client-Secret: thisismysecretkey" \
  -H "Content-type: application/json"
```

```javascript
/* Sample with the request library */

let url = "https://app.seventime.se/api/2/driverJournals/5613c0eabed93172591b";
let options = {
  url: url,
  headers: {
    "Client-Secret": "thisismysecretkey",
    "Content-Type": "application/json",
    "Accept": 'application/json'
  }
};

request(options, function(error, response, body) {
  if (!error && response.statusCode == 200) {
    let info = JSON.parse(body);
    // ...
  } else {
    console.error("Error when calling API! HTTP Code: " + response.statusCode + ", Error message: " + body.errorMessage);
  }
});
```

> The above command returns JSON structured like this:

```json
{
  "data": {
    "isInvoiceable": true,
    "_id": "5613c0eabed93172591b",
    "name": "",
    "driverJournalItemType": "574ed84219e78125333201799",
    "driverJournalItemTypeName": "4 kr/km",
    "car": null,
    "carRegistrationNumber": "ABC123",
    "description": "",
    "user": "5f48eb3e65d7ee40317245d",
    "userName": "Anna Andersson",
    "customer": "5bb26376c42e07412b55",
    "customerName": "Company AB",
    "project": "5f924f4f533f102af784581",
    "projectName": "Tester",
    "workOrder": "5bae34dca878b237942",
    "workOrderTitle": "20160525",
    "workOrderNumber": 1181,
    "startAddress": "Östra Gatan 129, Stockholm",
    "endAddress": "Västra Gatan 921, Stockholm",
    "travelPurpose": ".",
    "startOdometer": 156,
    "endOdometer": 178,
    "totalDistance": 22,
    "price": 4,
    "totalAmount": 88,
    "isInvoiced": true,
    "invoice": "5fab29b0386134897",
    "modifiedDate": "2016-06-17T09:29:01.958Z",
    "createDate": "2016-06-17T09:20:46.845Z",
    "timestamp": "2016-06-17T09:20:10.254Z",
  }
}
```

This endpoint retrieves a specific driver journal.


### HTTP Request

`GET https://app.seventime.se/api/2/driverJournals/<_id>`

### URL Parameters

Parameter | Description
--------- | -----------
_id | The _id of the driver journal to retrieve

## Get Driver Journals Types

```shell
curl "https://app.seventime.se/api/2/driverJournalTypes" \
  -H "Client-Secret: thisismysecretkey" \
  -H "Content-type: application/json"
```

```javascript
/* Sample with the request library */

let url = "https://app.seventime.se/api/2/driverJournalTypes";
let options = {
  url: url,
  headers: {
    "Client-Secret": "thisismysecretkey",
    "Content-Type": "application/json",
    "Accept": 'application/json'
  }
};

request(options, function(error, response, body) {
  if (!error && response.statusCode == 200) {
    let info = JSON.parse(body);
    // ...
  } else {
    console.error("Error when calling API! HTTP Code: " + response.statusCode + ", Error message: " + body.errorMessage);
  }  
});
```

> The above command returns JSON structured like this:

```json
{
  "data": [
    {
      "_id": "5e5ef41f03481b466",
      "name": "Diesel - ej skt.fri",
      "articleNumber": "45",
      "cost": 0.5,
      "price": 0.65,
      "isInvoiceable": true,
      "isDefault": false,
      "salaryCompensationType": 20,
      "salaryType": "5e5cd96da2f5b64823791",
      "salaryTypeName": "Milersättning för diesel",
      "createDate": "2020-03-03T09:14:11.750Z",
      "isActive": true,
      "salaryCode": "9172"
    },
    {
      // ...
    }
  ]
}
```

This endpoint retrieves driver journals types.

### HTTP Request

`GET https://app.seventime.se/api/2/driverJournalTypes`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
sortBy                      |  | If specified, a sort will be made on the specified parameter
sortDirection               |  | "ascending" or "descending". If specified and sortBy is specified the sort order will be ascending or descending


## Create a Driver Journal

```shell
curl -X POST "https://app.seventime.se/api/2/driverJournals/" \
  -H "Client-Secret: thisismysecretkey" \
  -H "Content-Type: application/json" \
  -d '{"createdByUser":"5120314650548666171","user":"51203178219463791","expenseItem":"5de78aed13437891254"}'
```

```javascript
let jsonData = {
  createdByUser: '512031465648817e55b',
  user: '5f48eb3e65d7e5489134452',
  carRegistrationNumber: 'ABC123',
  driverJournalItemType: '5e5ef4124135975',
  startAddress: 'Address start, Stockholm',
  endAddress: 'Address end, Stockholm',
  travelPurpose: 'Delivery',
  startOdometer: '45',
  endOdometer: '60',
};

let options = {
  url: 'https://app.seventime.se/api/2/driverJournals',
  json: jsonData,
  headers: {
    "Client-Secret": "thisismysecretkey",
    "Content-Type": "application/json",
    "Accept": 'application/json'
  }
};

request.post(options, function (error, response, body) {
  if (!error && response.statusCode === 200) {
    console.log(body);
    console.log("Driver journal created: _id: " + body._id);

  } else {
    console.error("ERROR! Unable to create driver journal: " + error);
  }
});
```

> The above command returns JSON structured like this:

```json 
{
  "isInvoiceable": true,
  "_id": "5fc619b964579133",
  "timestamp": "2020-12-01T10:23:53.370Z",
  "createDate": "2020-12-01T10:23:53.370Z",
  "modifiedDate": "2020-12-01T10:23:53.370Z",
  "user": "5f48eb3e65d7ee457951b",
  "userName": "Anna Andersson",
  "carRegistrationNumber": "ABC123",
  "driverJournalItemType": "5e5ef41f0d5481125",
  "driverJournalItemTypeName": "Diesel - ej skt.fri",
  "startAddress": "Address start, Stockholm",
  "endAddress": "Address end, Stockholm",
  "travelPurpose": "Delivery",
  "startOdometer": 45,
  "endOdometer": 60,
  "totalDistance": 15,
  "isSalaryCompensated": false,
  "price": 0,
  "totalAmount": 0,
  "cost": 0,
  "totalCost": 0,
}
"Driver journal created: _id: 5fc619b9625789154"
```

This endpoint creates a driver journal

### HTTP Request

`POST https://app.seventime.se/api/2/driverJournals/`

### POST Parameters

Parameter | Type | Required? | Description
--------- | ----------- | ----------- | -----------
createdByUser           | String | Yes | Id of the user who created the driver journal
user                    | String | Yes | Id of the user on the driver journal
vehicle                 | String | Yes*| Id of the vehicle. *Required if carRegistrationNumber is not specified
carRegistrationNumber   | String | Yes*| Car registration number. *Required if vehicle is not specified. This will not be used if vehicle is specified
driverJournalItemType   | String | Yes | Type of trip
startAddress            | String | Yes | Start address of the driver journal
endAddress              | String | Yes | End address of the driver journal
travelPurpose           | String | Yes | Errand/position/Company/Contact person
startOdometer           | Number | Yes | Odometer reading at the start
endOdometer             | Number | Yes | Odometer reading at the end
customer                | String | No  | Id of the customer
project                 | String | No  | Id of the project
workOrder               | String | No  | Id of the work order. If project is specified, the work order must belong to the project. The customer from the work order will be used on the driver journal
price                   | Number | No  | Price/km
cost                    | Number | No  | Cost/km
description             | String | No  | Description or notes on the driver journal
isInvoiceable           | Boolean | No | Is the driver jounal invoiceable?
isSalaryCompensated     | Boolean | No | Is the driver jounal salary compensated?

## Update a Driver Journal

```shell
curl -X PUT "https://app.seventime.se/api/2/driverJournals/" \
  -H "Client-Secret: thisismysecretkey" \
  -H "Content-Type: application/json" \
  -d '{"_id":"5fc619b96294498231","modifiedByUser":"51203146506d96498312567","user":"5f48eb3e65d7ee44598912b"}'
```

```javascript
let jsonData = {
  _id: '5fc619b96294735fc7812458',
  modifiedByUser: '51203146506d94891377',
  user: '5f48eb3e65d7ee461288'
};

let options = {
  url: 'https://app.seventime.se/api/2/driverJournals',
  json: jsonData,
  headers: {
    "Client-Secret": "thisismysecretkey",
    "Content-Type": "application/json",
    "Accept": 'application/json'
  }
};

request.put(options, function (error, response, body) {
  if (!error && response.statusCode === 200) {
    console.log(body);
    console.log("Driver journal updated: _id: " + body._id);
  } else {
    console.error("ERROR! Unable to update driver journal: " + error);
    console.error(body);
  }
});
```

> The above command returns JSON structured like this:

```json 
{
  "isInvoiceable": true,
  "_id": "5fc619b96294735124544bd",
  "timestamp": "2020-12-01T10:23:53.370Z",
  "createDate": "2020-12-01T10:23:53.370Z",
  "modifiedDate": "2020-12-01T10:23:53.370Z",
  "user": "5f48eb3e65d7e2548412d",
  "userName": "Anna Andersson",
  "carRegistrationNumber": "ABC123",
  "driverJournalItemType": "5e5ef41f0d989125e",
  "driverJournalItemTypeName": "Diesel - ej skt.fri",
  "startAddress": "Address start, Stockholm",
  "endAddress": "Address end, Stockholm",
  "travelPurpose": "Delivery",
  "startOdometer": 45,
  "endOdometer": 60,
  "totalDistance": 15,
  "isSalaryCompensated": false,
  "price": 0,
  "totalAmount": 0,
  "cost": 0,
  "totalCost": 0
}
"Driver journal updated: _id: 5fc619b96294735124544bd"
```

This endpoint updates a driver journal

### HTTP Request

`PUT https://app.seventime.se/api/2/driverJournals/`

### PUT Parameters
The table below shows the required fields. Other available fields can be found in the section 'Create a Driver Journal'.

Parameter | Type | Required? | Description
--------- | ----------- | ----------- | -----------
_id            | String | Yes | Id of the driver journal
modifiedByUser | String | Yes | Id of the user who made the change
user           | String | Yes | Id of the user on the driver journal

## Delete a Driver Journal

```shell
curl -X DELETE "https://app.seventime.se/api/2/driverJournals/" \
  -H "Client-Secret: thisismysecretkey" \
  -H "Content-Type: application/json" \
  -d '{"_id":"5fc619b96294735fd458173","deletedByUser":"51203146506d961c1349691"}'
```

```javascript
let jsonData = {
  _id: '5fc619b96294735315489',
  deletedByUser: '51203146506d9611b895'
};

let options = {
  url: 'https://app.seventime.se/api/2/driverJournals',
  json: jsonData,
  headers: {
    "Client-Secret": "thisismysecretkey",
    "Content-Type": "application/json",
    "Accept": 'application/json'
  }
};

request.delete(options, function (error, response, body) {
  if (!error && response.statusCode === 200) {
    console.log(body);
    console.log("Driver journal deleted: _id: " + body._id);
  } else {
    console.error("ERROR! Unable to delete driver journal: " + error);
    console.error(body);
  }
});
```

> The above command returns JSON structured like this:

```json 
{
  "_id": "5fc619b96294735fc421d77a",
}
"Driver journal deleted: _id: 5fc619b962947312234894"
```

This endpoint deletes a driver journal

### HTTP Request

`DELETE https://app.seventime.se/api/2/driverJournals/`

### DELETE Parameters

Parameter | Type | Required? | Description
--------- | ----------- | ----------- | -----------
_id                    | String | Yes | Id of the driver journal
