# Introduction

Welcome to the Aggois! You can use our API to access Aggois API endpoints, which can get information on Customers, Bank accounts, Nach mandates and Land records in our database.

We have language bindings in Shell, Ruby, and Python! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.



# Authentication

> To authorize, use this code:

```ruby
require 'aggois'

api = aggois::APIClient.authorize!('RDFGKEW')
```

```python
import aggois

api = aggois.authorize('RDFGKEW')
```

```bash
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: RDFGKEW"
```

```javascript
const aggois = require('aggois');

let api = aggois.authorize('RDFGKEW');
```

> Make sure to replace `RDFGKEW` with your API key.

Aggois uses API keys to allow access to the API. You can register a new Aggois API key at our [developer portal](http://aggois.com/developers).

Aggois expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: RDFGKEW`

<aside class="notice">
You must replace <code>RDFGKEW</code> with your personal API key.
</aside>

# Customers

## Get All Customers

```ruby
require 'aggois'

api = Aggois::APIClient.authorize!('RDFGKEW')
api.customers.get
```

```python
import aggois

api = aggois.authorize('RDFGKEW')
api.customers.get()
```

```bash
curl "http://example.com/api/customers"
  -H "Authorization: RDFGKEW"
```

```javascript
const kittn = require('aggois');

let api = aggois.authorize('RDFGKEW');
let kittens = api.aggois.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Akhil",
    "region": "Bangalore"
  },
  {
    "id": 1,
    "name": "Paurush",
    "region": "Bangalore"
  },
  {
    "id": 1,
    "name": "Devansh",
    "region": "Bangalore"
  }
]
```

This endpoint retrieves all customers.

### HTTP Request

`GET http://aggois.com/api/customers`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_aadhaar | false | If set to true, the result will also include aadhaar.
available | true | If set to false, the result will include customers that have already been adopted.

<aside class="success">
Remember — a happy customer is an authenticated customer!
</aside>

## Get a Specific Customer

```ruby
require 'customer'

api = Customer::APIClient.authorize!('RDFGKEW')
api.customer.get(2)
```

```python
import aggois

api = customer.authorize('RDFGKEW')
api.customer.get(2)
```

```bash
curl "http://aggois.com/api/customer/2"
  -H "Authorization: RDFGKEW"
```

```javascript
const customer = require('aggois');

let api = customer.authorize('RDFGKEW');
let max = api.customer.get(2);
```

> The above command returns JSON structured like this:

```json
{
    "id": 1,
    "name": "Akhil",
    "region": "Bangalore"
  }
```

This endpoint retrieves a specific customer.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/customer/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the customer to retrieve
