---
title: API specification
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - javascript--nodejs: Node.JS
  - ruby: Ruby
  - python: Python
  - java: Java
  - go: Go
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<h1 id="API-specification">API specification v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

example API

Base URLs:

* <a href="https://api.gridscale.io/">https://api.gridscale.io/</a>

# Authentication

* API Key (ApiKeyAuth)
    - Parameter Name: **X-Auth-Token**, in: header. 

* API Key (ApiUserID)
    - Parameter Name: **X-Auth-UserId**, in: header. 

<h1 id="API-specification-Location">Location</h1>

## getLocations

<a id="opIdgetLocations"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/locations \
  -H 'Accept: */*' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/locations HTTP/1.1
Host: api.gridscale.io

Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/locations',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'*/*',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/locations',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/locations',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/locations', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/locations");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/locations", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/locations`

*get all locations*

GET https://api.gridscale.io/objects/locations

> Example responses

> 200 Response

<h3 id="getlocations-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[LocationsGetResponse](#schemalocationsgetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getLocation

<a id="opIdgetLocation"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/locations/{location_uuid} \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/locations/{location_uuid} HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/locations/{location_uuid}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/locations/{location_uuid}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/locations/{location_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/locations/{location_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/locations/{location_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/locations/{location_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/locations/{location_uuid}`

*get location*

GET https://api.gridscale.io/objects/locations/{location_uuid}

<h3 id="getlocation-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|location_uuid|path|string|true|ID of sshkey|

> Example responses

> 200 Response

```json
{
  "location": {
    "iata": "fra",
    "status": "active",
    "labels": [],
    "name": "de/fra",
    "object_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
    "country": "de"
  }
}
```

<h3 id="getlocation-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[LocationGetResponse](#schemalocationgetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getLocationIps

<a id="opIdgetLocationIps"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/locations/{location_uuid}/ips \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/locations/{location_uuid}/ips HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/locations/{location_uuid}/ips',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/locations/{location_uuid}/ips',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/locations/{location_uuid}/ips',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/locations/{location_uuid}/ips', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/locations/{location_uuid}/ips");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/locations/{location_uuid}/ips", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/locations/{location_uuid}/ips`

*get locations ips*

GET https://api.gridscale.io/objects/locations/{location_uuid}/ips

<h3 id="getlocationips-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|location_uuid|path|string|true|uuid of location|

> Example responses

> 200 Response

```json
{
  "ips": {
    "x123xx1x-123x-1x12-123x-123xxx123x1x": {
      "create_time": "2018-02-01T13:48:13Z",
      "status": "active",
      "relations": {
        "loadbalancers": [],
        "servers": [
          {
            "create_time": "2018-02-20T11:51:18Z",
            "server_name": "server with a new name2",
            "server_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x"
          }
        ]
      },
      "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
      "partner_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
      "location_country": "de",
      "prefix": "123.123.12.1/128",
      "delete_block": false,
      "failover": false,
      "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
      "location_name": "de/fra",
      "labels": [],
      "change_time": "2018-02-01T13:48:13Z",
      "ip": "123.123.12.1",
      "family": 6,
      "location_iata": "fra",
      "reverse_dns": "static-123-123-123-123.ipv6.exampleserver.com",
      "current_price": 0,
      "usage_in_minutes": 0,
      "name": "Default IP"
    }
  }
}
```

<h3 id="getlocationips-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[IpsGetResponse](#schemaipsgetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getLocationIsoimages

<a id="opIdgetLocationIsoimages"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/locations/{location_uuid}/isoimages \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/locations/{location_uuid}/isoimages HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/locations/{location_uuid}/isoimages',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/locations/{location_uuid}/isoimages',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/locations/{location_uuid}/isoimages',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/locations/{location_uuid}/isoimages', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/locations/{location_uuid}/isoimages");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/locations/{location_uuid}/isoimages", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/locations/{location_uuid}/isoimages`

*get locations isoimages*

GET https://api.gridscale.io/objects/locations/{location_uuid}/isoimages

<h3 id="getlocationisoimages-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|location_uuid|path|string|true|uuid of location|

> Example responses

> 200 Response

```json
{
  "isoimages": {
    "x123xx1x-123x-1x12-123x-123xxx123x1x": {
      "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
      "relations": {
        "servers": []
      },
      "description": null,
      "location_name": "de/fra",
      "source_url": "http://de.releases.ubuntu.com/16.04.3/ubuntu-16.04.3-server-amd64.iso",
      "labels": [],
      "location_iata": "fra",
      "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
      "status": "active",
      "create_time": "2017-10-25T12:39:23Z",
      "name": "Ubuntu 16.04.03 LTS",
      "version": null,
      "location_country": "de",
      "usage_in_minutes": 0,
      "private": false,
      "change_time": "2017-10-26T15:52:34Z",
      "capacity": 1,
      "current_price": 0
    }
  }
}
```

<h3 id="getlocationisoimages-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[IsoimagesGetResponse](#schemaisoimagesgetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getLocationNetworks

<a id="opIdgetLocationNetworks"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/locations/{location_uuid}/networks \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/locations/{location_uuid}/networks HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/locations/{location_uuid}/networks',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/locations/{location_uuid}/networks',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/locations/{location_uuid}/networks',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/locations/{location_uuid}/networks', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/locations/{location_uuid}/networks");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/locations/{location_uuid}/networks", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/locations/{location_uuid}/networks`

*get locations networks*

GET https://api.gridscale.io/objects/locations/{location_uuid}/networks

<h3 id="getlocationnetworks-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|location_uuid|path|string|true|uuid of location|

> Example responses

> 200 Response

```json
{
  "networks": {
    "x123xx1x-123x-1x12-123x-123xxx123x1x": {
      "location_country": "de",
      "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
      "public_net": false,
      "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
      "network_type": "network",
      "name": "test",
      "delete_block": false,
      "status": "active",
      "create_time": "2018-03-14T08:04:16Z",
      "l2security": false,
      "relations": {
        "vlans": [],
        "servers": []
      },
      "labels": [],
      "change_time": "2018-03-14T08:04:16Z",
      "location_iata": "fra",
      "location_name": "de/fra"
    }
  }
}
```

<h3 id="getlocationnetworks-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[NetworksGetResponse](#schemanetworksgetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getLocationServers

<a id="opIdgetLocationServers"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/locations/{location_uuid}/servers \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/locations/{location_uuid}/servers HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/locations/{location_uuid}/servers',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/locations/{location_uuid}/servers',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/locations/{location_uuid}/servers',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/locations/{location_uuid}/servers', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/locations/{location_uuid}/servers");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/locations/{location_uuid}/servers", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/locations/{location_uuid}/servers`

*get locations networks*

GET https://api.gridscale.io/objects/locations/{location_uuid}/servers

<h3 id="getlocationservers-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|location_uuid|path|string|true|uuid of location|

> Example responses

> 200 Response

```json
{
  "servers": {
    "x123xx1x-123x-1x12-123x-123xxx123x1x": {
      "auto_recovery": true,
      "availability_zone": null,
      "current_price": 9.491665,
      "power": true,
      "status": "active",
      "cores": 1,
      "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
      "name": "Ubunto 16.04",
      "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
      "usage_in_minutes_cores": 17476,
      "labels": [],
      "hardware_profile": "default",
      "location_iata": "fra",
      "location_name": "de/fra",
      "legacy": false,
      "memory": 2,
      "create_time": "2018-03-14T13:33:13Z",
      "relations": {
        "public_ips": [
          {
            "prefix": "1x:12:xx:12:12:12/32",
            "create_time": "2018-03-14T13:33:14Z",
            "family": 4,
            "ip": "123.123.12.1",
            "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x"
          },
          {
            "prefix": "123.123.12.1/128",
            "create_time": "2018-03-14T13:33:16Z",
            "family": 6,
            "ip": "123.123.12.1",
            "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x"
          }
        ],
        "isoimages": [],
        "networks": [
          {
            "bootdevice": false,
            "firewall_template_uuid": null,
            "vlan": null,
            "mcast": null,
            "vxlan": null,
            "public_net": true,
            "l2security": true,
            "object_name": "Public Network test",
            "network_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
            "create_time": "2018-03-14T13:33:13Z",
            "firewall": null,
            "network_type": "network",
            "mac": "16:f7:22:9e:56:01",
            "partner_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
            "l3security": [],
            "ordering": 0,
            "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x"
          }
        ],
        "storages": [
          {
            "bootdevice": true,
            "target": 0,
            "lun": 0,
            "capacity": 11,
            "object_name": "Ubunto 16.04 Storage",
            "controller": 0,
            "create_time": "2018-03-14T13:33:24Z",
            "storage_type": "storage",
            "bus": 0,
            "last_used_template": "ec4ef18f-84df-42bb-b7c4-c2957635ee53",
            "license_product_no": null,
            "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x"
          }
        ]
      },
      "usage_in_minutes_memory": 47331,
      "change_time": "2018-03-19T11:40:55Z",
      "console_token": "$console_token",
      "location_country": "de"
    }
  }
}
```

<h3 id="getlocationservers-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[ServersGetResponse](#schemaserversgetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getLocationSnapshots

<a id="opIdgetLocationSnapshots"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/locations/{location_uuid}/snapshots \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/locations/{location_uuid}/snapshots HTTP/1.1
Host: api.gridscale.io

```

```javascript
var headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/locations/{location_uuid}/snapshots',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/locations/{location_uuid}/snapshots',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/locations/{location_uuid}/snapshots',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/locations/{location_uuid}/snapshots', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/locations/{location_uuid}/snapshots");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/locations/{location_uuid}/snapshots", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/locations/{location_uuid}/snapshots`

*get locations snapshots*

GET https://api.gridscale.io/objects/locations/{location_uuid}/snapshots

<h3 id="getlocationsnapshots-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|location_uuid|path|string|true|uuid of location|

<h3 id="getlocationsnapshots-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|None|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getLocationStorage

<a id="opIdgetLocationStorage"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/locations/{location_uuid}/storages \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/locations/{location_uuid}/storages HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/locations/{location_uuid}/storages',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/locations/{location_uuid}/storages',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/locations/{location_uuid}/storages',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/locations/{location_uuid}/storages', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/locations/{location_uuid}/storages");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/locations/{location_uuid}/storages", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/locations/{location_uuid}/storages`

*get locations storages*

GET https://api.gridscale.io/objects/locations/{location_uuid}/storages

<h3 id="getlocationstorage-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|location_uuid|path|string|true|uuid of location|

> Example responses

> 200 Response

```json
{
  "storages": {
    "x123xx1x-123x-1x12-123x-123xxx123x1x": {
      "change_time": "2018-03-13T09:24:23Z",
      "location_iata": "fra",
      "status": "active",
      "license_product_no": null,
      "location_country": "de",
      "usage_in_minutes": 770,
      "last_used_template": null,
      "current_price": 0.003388,
      "capacity": 10,
      "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
      "storage_type": "storage",
      "parent_uuid": null,
      "name": "test Storage",
      "location_name": "de/fra",
      "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
      "snapshots": [],
      "relations": {
        "servers": [
          {
            "bootdevice": true,
            "target": 0,
            "controller": 0,
            "bus": 0,
            "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
            "lun": 0,
            "create_time": "2018-03-13T09:24:25Z",
            "object_name": "tes"
          }
        ],
        "snapshot_schedules": []
      },
      "labels": [],
      "create_time": "2018-03-13T09:24:23Z"
    }
  }
}
```

<h3 id="getlocationstorage-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[StoragesGetResponse](#schemastoragesgetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getLocationTemplates

<a id="opIdgetLocationTemplates"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/locations/{location_uuid}/templates \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/locations/{location_uuid}/templates HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/locations/{location_uuid}/templates',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/locations/{location_uuid}/templates',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/locations/{location_uuid}/templates',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/locations/{location_uuid}/templates', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/locations/{location_uuid}/templates");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/locations/{location_uuid}/templates", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/locations/{location_uuid}/templates`

*get locations templates*

GET https://api.gridscale.io/objects/locations/{location_uuid}/templates

<h3 id="getlocationtemplates-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|location_uuid|path|string|true|uuid of location|

> Example responses

> 200 Response

```json
{
  "locations": {
    "x123xx1x-123x-1x12-123x-123xxx123x1x": {
      "status": "active",
      "ostype": "windows",
      "version": "Windows Server 2016 Standard",
      "location_iata": "fra",
      "change_time": "2017-10-30T11:50:35Z",
      "private": false,
      "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
      "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
      "license_product_no": 800002,
      "create_time": "2016-10-24T14:50:23Z",
      "usage_in_minutes": 0,
      "name": "Windows Server 2016",
      "capacity": 32,
      "location_name": "de/fra",
      "distro": "Windows Server",
      "description": "SPLA-Licensed",
      "current_price": 0,
      "location_country": "de"
    }
  }
}
```

> successful operation

<h3 id="getlocationtemplates-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[TemplatesGetResponse](#schematemplatesgetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

<h1 id="API-specification-PaaS">PaaS</h1>

## getPaasServices

<a id="opIdgetPaasServices"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/paas/services \
  -H 'Accept: */*' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/paas/services HTTP/1.1
Host: api.gridscale.io

Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/paas/services',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'*/*',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/paas/services',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/paas/services',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/paas/services', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/paas/services");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/paas/services", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/paas/services`

*get all PaaS*

> Example responses

> 200 Response

<h3 id="getpaasservices-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[PaasServicesGetResponse](#schemapaasservicesgetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## createPaasServices

<a id="opIdcreatePaasServices"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://api.gridscale.io//objects/paas/services \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
POST https://api.gridscale.io//objects/paas/services HTTP/1.1
Host: api.gridscale.io
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/paas/services',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "name": "string",
  "paas_service_uuid": "string",
  "labels": [
    "string"
  ],
  "paas_security_zone_uuid": "string",
  "resource_limit": [
    {
      "resource": "string",
      "limit": 0
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/paas/services',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.post 'https://api.gridscale.io//objects/paas/services',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.post('https://api.gridscale.io//objects/paas/services', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/paas/services");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.gridscale.io//objects/paas/services", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /objects/paas/services`

*Add a new PaaS*

It only takes two parameters to create a Platform service, you will need to find the UUID of the Service you would like to create with a GET request to the /service_templates endpoint.

> Body parameter

```json
{
  "name": "string",
  "paas_service_uuid": "string",
  "labels": [
    "string"
  ],
  "paas_security_zone_uuid": "string",
  "resource_limit": [
    {
      "resource": "string",
      "limit": 0
    }
  ]
}
```

```yaml
name: string
paas_service_uuid: string
labels:
  - string
paas_security_zone_uuid: string
resource_limit:
  - resource: string
    limit: 0

```

<h3 id="createpaasservices-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[PaasCreate](#schemapaascreate)|true|Data for a new cas task|

> Example responses

> 200 Response

```json
{
  "request_uuid": "string",
  "listen_ports": {
    "IPv6": {
      "mysql": 0
    }
  },
  "paas_service_uuid": "string",
  "credentials": [
    {
      "password": "string",
      "username": "string",
      "type": "string"
    }
  ]
}
```

<h3 id="createpaasservices-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[PaasCreateResponse](#schemapaascreateresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getPaasService

<a id="opIdgetPaasService"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/paas/services/{object_uuid} \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/paas/services/{object_uuid} HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/paas/services/{object_uuid}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/paas/services/{object_uuid}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/paas/services/{object_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/paas/services/{object_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/paas/services/{object_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/paas/services/{object_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/paas/services/{object_uuid}`

*Find object by uuid*

Returns a single paas

<h3 id="getpaasservice-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|object_uuid|path|string|true|ID of paas|

> Example responses

> 200 Response

```json
{
  "task": {
    "object_uuid": "string",
    "labels": [
      "string"
    ],
    "credentials": [
      {
        "password": "string",
        "username": "string",
        "type": "string"
      }
    ],
    "create_time": "2018-08-28T08:15:36Z",
    "listen_ports": {},
    "security_zone_uuid": "string",
    "service_template_uuid": "string",
    "usage_in_minutes": 0,
    "current_price": 0,
    "change_time": "2018-08-28T08:15:36Z",
    "status": "string",
    "name": "string"
  }
}
```

<h3 id="getpaasservice-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[PaasServiceGetResponse](#schemapaasservicegetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## updatePaasService

<a id="opIdupdatePaasService"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH https://api.gridscale.io//objects/paas/services/{object_uuid} \
  -H 'Content-Type: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
PATCH https://api.gridscale.io//objects/paas/services/{object_uuid} HTTP/1.1
Host: api.gridscale.io
Content-Type: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/paas/services/{object_uuid}',
  method: 'patch',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "name": "string",
  "labels": [
    "string"
  ],
  "resource_limit": [
    {
      "resource": "string",
      "limit": 0
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/paas/services/{object_uuid}',
{
  method: 'PATCH',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.patch 'https://api.gridscale.io//objects/paas/services/{object_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.patch('https://api.gridscale.io//objects/paas/services/{object_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/paas/services/{object_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "https://api.gridscale.io//objects/paas/services/{object_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /objects/paas/services/{object_uuid}`

*Updated PaaS *

Once a service has been created, it's service type cannot be changed, we can only update the Name and labels of a service.

> Body parameter

```json
{
  "name": "string",
  "labels": [
    "string"
  ],
  "resource_limit": [
    {
      "resource": "string",
      "limit": 0
    }
  ]
}
```

<h3 id="updatepaasservice-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|object_uuid|path|string|true|object that need to be updated|
|body|body|[PaasUpdateRequest](#schemapaasupdaterequest)|true|Updated PaaS|

<h3 id="updatepaasservice-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|None|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|The request was successful, but the answer deliberately contains no data.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## deletePaasService

<a id="opIddeletePaasService"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE https://api.gridscale.io//objects/paas/services/{object_uuid} \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
DELETE https://api.gridscale.io//objects/paas/services/{object_uuid} HTTP/1.1
Host: api.gridscale.io

```

```javascript
var headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/paas/services/{object_uuid}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/paas/services/{object_uuid}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.delete 'https://api.gridscale.io//objects/paas/services/{object_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.delete('https://api.gridscale.io//objects/paas/services/{object_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/paas/services/{object_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://api.gridscale.io//objects/paas/services/{object_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /objects/paas/services/{object_uuid}`

*delete PaaS*

<h3 id="deletepaasservice-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|object_uuid|path|string|true|object that need to be deleted|

<h3 id="deletepaasservice-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|The request was successful, but the answer deliberately contains no data.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getServiceTemplates

<a id="opIdgetServiceTemplates"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/paas/service_templates \
  -H 'Accept: */*' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/paas/service_templates HTTP/1.1
Host: api.gridscale.io

Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/paas/service_templates',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'*/*',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/paas/service_templates',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/paas/service_templates',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/paas/service_templates', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/paas/service_templates");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/paas/service_templates", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/paas/service_templates`

*get all PaaS templates*

 Here is a list of Service Templates that you can use to create a service. You will need the object_uuid when creating a new Service.

> Example responses

> 200 Response

<h3 id="getservicetemplates-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[PaasServiceTemplatesGetResponse](#schemapaasservicetemplatesgetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getSecurityZones

<a id="opIdgetSecurityZones"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/paas/security_zones \
  -H 'Accept: */*' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/paas/security_zones HTTP/1.1
Host: api.gridscale.io

Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/paas/security_zones',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'*/*',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/paas/security_zones',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/paas/security_zones',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/paas/security_zones', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/paas/security_zones");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/paas/security_zones", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/paas/security_zones`

*get all PaaS security_zones*

GET https://api.gridscale.io/objects/paas/security_zones

> Example responses

> 200 Response

<h3 id="getsecurityzones-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[PaasSecurityZonesGetResponse](#schemapaassecurityzonesgetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## createSecurityZone

<a id="opIdcreateSecurityZone"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://api.gridscale.io//objects/paas/security_zones \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
POST https://api.gridscale.io//objects/paas/security_zones HTTP/1.1
Host: api.gridscale.io
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/paas/security_zones',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "name": "new psz",
  "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/paas/security_zones',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.post 'https://api.gridscale.io//objects/paas/security_zones',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.post('https://api.gridscale.io//objects/paas/security_zones', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/paas/security_zones");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.gridscale.io//objects/paas/security_zones", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /objects/paas/security_zones`

*Add a new PaaS security zone*

A security zone essentially works like a network. It connects services that are located within the zone with servers that are connected to the zone. The first security zone will be created by us on demand, and it will then be used by default. If you would like to use another zone, you would have to create it yourself first.

> Body parameter

```json
{
  "name": "new psz",
  "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950"
}
```

```yaml
name: new psz
location_uuid: 45ed677b-3702-4b36-be2a-a2eab9827950

```

<h3 id="createsecurityzone-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[PaasSecurityZoneCreate](#schemapaassecurityzonecreate)|true|Data for a new security_zones|

> Example responses

> 202 Response

```json
{
  "request_uuid": "0df82edc-b0b9-461f-a72c-f210ddaddfc8",
  "paas_security_zone_uuid": "da792f47-a2d2-48a5-974c-3446c8374e6d"
}
```

<h3 id="createsecurityzone-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|successful operation|[PaasSecurityZoneCreateResponse](#schemapaassecurityzonecreateresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getSecurityZone

<a id="opIdgetSecurityZone"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//paas/security_zones/{paas_security_zone_uuid} \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//paas/security_zones/{paas_security_zone_uuid} HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//paas/security_zones/{paas_security_zone_uuid}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//paas/security_zones/{paas_security_zone_uuid}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//paas/security_zones/{paas_security_zone_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//paas/security_zones/{paas_security_zone_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//paas/security_zones/{paas_security_zone_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//paas/security_zones/{paas_security_zone_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /paas/security_zones/{paas_security_zone_uuid}`

*Find object by uuid*

Returns a single paas security zone

<h3 id="getsecurityzone-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|paas_security_zone_uuid|path|string|true|ID of paas|

> Example responses

> 200 Response

```json
{
  "paas_security_zone": {
    "property1": {
      "location_country": "string",
      "relations": {
        "object1": [
          {}
        ]
      },
      "create_time": "2018-08-28T08:15:36Z",
      "location_iata": "string",
      "object_uuid": "string",
      "labels": [
        "string"
      ],
      "location_name": "string",
      "status": "string",
      "location_uuid": "string",
      "change_time": "2018-08-28T08:15:36Z",
      "name": "string"
    },
    "property2": {
      "location_country": "string",
      "relations": {
        "object1": [
          {}
        ]
      },
      "create_time": "2018-08-28T08:15:36Z",
      "location_iata": "string",
      "object_uuid": "string",
      "labels": [
        "string"
      ],
      "location_name": "string",
      "status": "string",
      "location_uuid": "string",
      "change_time": "2018-08-28T08:15:36Z",
      "name": "string"
    }
  }
}
```

<h3 id="getsecurityzone-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[PaasSecurityZoneGetResponse](#schemapaassecurityzonegetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## updateSecurityZone

<a id="opIdupdateSecurityZone"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH https://api.gridscale.io//paas/security_zones/{paas_security_zone_uuid} \
  -H 'Content-Type: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
PATCH https://api.gridscale.io//paas/security_zones/{paas_security_zone_uuid} HTTP/1.1
Host: api.gridscale.io
Content-Type: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//paas/security_zones/{paas_security_zone_uuid}',
  method: 'patch',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "name": "new zone",
  "labels": [
    "Test Zone"
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//paas/security_zones/{paas_security_zone_uuid}',
{
  method: 'PATCH',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.patch 'https://api.gridscale.io//paas/security_zones/{paas_security_zone_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.patch('https://api.gridscale.io//paas/security_zones/{paas_security_zone_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//paas/security_zones/{paas_security_zone_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "https://api.gridscale.io//paas/security_zones/{paas_security_zone_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /paas/security_zones/{paas_security_zone_uuid}`

*Updated PaaS security zone *

A security zone essentially works as a network. It connects services that are located within the zone with servers that are connected to the zone. The first security zone will be created by us on demand, and it will then be used by default. If you would like to use another zone, you would have to create it yourself first.

> Body parameter

```json
{
  "name": "new zone",
  "labels": [
    "Test Zone"
  ]
}
```

<h3 id="updatesecurityzone-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|paas_security_zone_uuid|path|string|true|object that need to be updated|
|body|body|[PaasSecurityZoneUpdate](#schemapaassecurityzoneupdate)|true|Updated PaaS|

<h3 id="updatesecurityzone-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|The request was successful, but the answer deliberately contains no data.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## deleteSecurityZone

<a id="opIddeleteSecurityZone"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE https://api.gridscale.io//paas/security_zones/{paas_security_zone_uuid} \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
DELETE https://api.gridscale.io//paas/security_zones/{paas_security_zone_uuid} HTTP/1.1
Host: api.gridscale.io

```

```javascript
var headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//paas/security_zones/{paas_security_zone_uuid}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//paas/security_zones/{paas_security_zone_uuid}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.delete 'https://api.gridscale.io//paas/security_zones/{paas_security_zone_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.delete('https://api.gridscale.io//paas/security_zones/{paas_security_zone_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//paas/security_zones/{paas_security_zone_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://api.gridscale.io//paas/security_zones/{paas_security_zone_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /paas/security_zones/{paas_security_zone_uuid}`

*delete PaaS security zone*

<h3 id="deletesecurityzone-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|paas_security_zone_uuid|path|string|true|object that need to be deleted|

<h3 id="deletesecurityzone-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|The request was successful, but the answer deliberately contains no data.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

<h1 id="API-specification-SSH-key">SSH key</h1>

## getSshKeys

<a id="opIdgetSshKeys"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/sshkeys \
  -H 'Accept: */*' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/sshkeys HTTP/1.1
Host: api.gridscale.io

Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/sshkeys',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'*/*',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/sshkeys',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/sshkeys',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/sshkeys', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/sshkeys");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/sshkeys", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/sshkeys`

*get all sshkeys*

GET https://api.gridscale.io/objects/sshkeys

> Example responses

> 200 Response

<h3 id="getsshkeys-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[SshkeysGetResponse](#schemasshkeysgetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## createSshKey

<a id="opIdcreateSshKey"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://api.gridscale.io//objects/sshkeys \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
POST https://api.gridscale.io//objects/sshkeys HTTP/1.1
Host: api.gridscale.io
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/sshkeys',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "name": "sshkey",
  "sshkey": "{sshkey}}"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/sshkeys',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.post 'https://api.gridscale.io//objects/sshkeys',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.post('https://api.gridscale.io//objects/sshkeys', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/sshkeys");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.gridscale.io//objects/sshkeys", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /objects/sshkeys`

*add new sshkeys*

POST https://api.gridscale.io/objects/sshkeys

> Body parameter

```json
{
  "name": "sshkey",
  "sshkey": "{sshkey}}"
}
```

```yaml
name: sshkey
sshkey: '{sshkey}}'

```

<h3 id="createsshkey-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[SshkeyCreate](#schemasshkeycreate)|true|Data for a new SSHkey|

> Example responses

> 200 Response

```json
{
  "request_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
  "object_uuid": "690de890-13c0-4e76-8a01-e10ba8786e53"
}
```

<h3 id="createsshkey-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[CreateResponse](#schemacreateresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getSshKey

<a id="opIdgetSshKey"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/sshkeys/{sshkey_uuid} \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/sshkeys/{sshkey_uuid} HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/sshkeys/{sshkey_uuid}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/sshkeys/{sshkey_uuid}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/sshkeys/{sshkey_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/sshkeys/{sshkey_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/sshkeys/{sshkey_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/sshkeys/{sshkey_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/sshkeys/{sshkey_uuid}`

*get sshkey*

GET https://api.gridscale.io/objects/sshkeys/{sshkey_uuid}

<h3 id="getsshkey-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|sshkey_uuid|path|string|true|ID of sshkey|

> Example responses

> 200 Response

```json
{
  "Sshkey": {
    "labels": [],
    "user_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
    "create_time": "2018-03-15T19:18:11Z",
    "status": "active",
    "change_time": "2018-03-15T19:18:11Z",
    "name": "test2",
    "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
    "sshkey": "{sshkey}"
  }
}
```

<h3 id="getsshkey-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[SshkeyGetResponse](#schemasshkeygetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## updateSshKey

<a id="opIdupdateSshKey"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH https://api.gridscale.io//objects/sshkeys/{sshkey_uuid} \
  -H 'Content-Type: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
PATCH https://api.gridscale.io//objects/sshkeys/{sshkey_uuid} HTTP/1.1
Host: api.gridscale.io
Content-Type: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/sshkeys/{sshkey_uuid}',
  method: 'patch',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "name": "new name"
}';
const headers = {
  'Content-Type':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/sshkeys/{sshkey_uuid}',
{
  method: 'PATCH',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.patch 'https://api.gridscale.io//objects/sshkeys/{sshkey_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.patch('https://api.gridscale.io//objects/sshkeys/{sshkey_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/sshkeys/{sshkey_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "https://api.gridscale.io//objects/sshkeys/{sshkey_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /objects/sshkeys/{sshkey_uuid}`

*update sshkey*

POST https://api.gridscale.io/objects/sshkeys/{sshkey_uuid}

> Body parameter

```json
{
  "name": "new name"
}
```

<h3 id="updatesshkey-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|sshkey_uuid|path|string|true|object that need to be updated|
|body|body|[SshkeyUpdate](#schemasshkeyupdate)|true|Updated user object|

<h3 id="updatesshkey-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|The request was successful, but the answer deliberately contains no data.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## deleteSshKey

<a id="opIddeleteSshKey"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE https://api.gridscale.io//objects/sshkeys/{sshkey_uuid} \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
DELETE https://api.gridscale.io//objects/sshkeys/{sshkey_uuid} HTTP/1.1
Host: api.gridscale.io

```

```javascript
var headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/sshkeys/{sshkey_uuid}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/sshkeys/{sshkey_uuid}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.delete 'https://api.gridscale.io//objects/sshkeys/{sshkey_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.delete('https://api.gridscale.io//objects/sshkeys/{sshkey_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/sshkeys/{sshkey_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://api.gridscale.io//objects/sshkeys/{sshkey_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /objects/sshkeys/{sshkey_uuid}`

*delete sshkey*

POST https://api.gridscale.io/objects/sshkeys/{sshkey_uuid}

<h3 id="deletesshkey-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|sshkey_uuid|path|string|true|object that need to be deleted|

<h3 id="deletesshkey-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|The request was successful, but the answer deliberately contains no data.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getSshKeyEvents

<a id="opIdgetSshKeyEvents"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/sshkeys/{sshkey_uuid}/events \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/sshkeys/{sshkey_uuid}/events HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/sshkeys/{sshkey_uuid}/events',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/sshkeys/{sshkey_uuid}/events',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/sshkeys/{sshkey_uuid}/events',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/sshkeys/{sshkey_uuid}/events', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/sshkeys/{sshkey_uuid}/events");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/sshkeys/{sshkey_uuid}/events", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/sshkeys/{sshkey_uuid}/events`

*delete sshkey*

POST https://api.gridscale.io/objects/sshkeys/{sshkey_uuid}

<h3 id="getsshkeyevents-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|sshkey_uuid|path|string|true|uuid of sshkey|

> Example responses

> 200 Response

```json
{
  "events": [
    {
      "object_type": "string",
      "request_uuid": "string",
      "object_uuid": "string",
      "activity": "string",
      "request_type": "string",
      "request_status": "string",
      "change": "string",
      "timestamp": "2018-08-28T08:15:36Z",
      "user_uuid": "string"
    }
  ]
}
```

> successful operation

<h3 id="getsshkeyevents-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[EventResponse](#schemaeventresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

<h1 id="API-specification-cas-task">cas task</h1>

## getCasTasks

<a id="opIdgetCasTasks"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/cas/tasks \
  -H 'Accept: */*' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/cas/tasks HTTP/1.1
Host: api.gridscale.io

Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/cas/tasks',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'*/*',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/cas/tasks',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/cas/tasks',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/cas/tasks', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/cas/tasks");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/cas/tasks", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/cas/tasks`

*get all cas tasks*

GET https://api.gridscale.io/objects/cas/tasks

> Example responses

> 200 Response

<h3 id="getcastasks-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[CasTasksGetResponse](#schemacastasksgetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## createCasTask

<a id="opIdcreateCasTask"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://api.gridscale.io//objects/cas/tasks \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
POST https://api.gridscale.io//objects/cas/tasks HTTP/1.1
Host: api.gridscale.io
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/cas/tasks',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "action_payload": {},
  "name": "string",
  "labels": [
    "string"
  ],
  "filters": [
    {
      "operator": "string",
      "field": "string",
      "comparison_value": 0
    }
  ],
  "status": "string",
  "active": true,
  "event_type": "string",
  "action_type": "send_email"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/cas/tasks',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.post 'https://api.gridscale.io//objects/cas/tasks',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.post('https://api.gridscale.io//objects/cas/tasks', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/cas/tasks");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.gridscale.io//objects/cas/tasks", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /objects/cas/tasks`

*Add a new cas task*

> Body parameter

```json
{
  "action_payload": {},
  "name": "string",
  "labels": [
    "string"
  ],
  "filters": [
    {
      "operator": "string",
      "field": "string",
      "comparison_value": 0
    }
  ],
  "status": "string",
  "active": true,
  "event_type": "string",
  "action_type": "send_email"
}
```

```yaml
action_payload: {}
name: string
labels:
  - string
filters:
  - operator: string
    field: string
    comparison_value: 0
status: string
active: true
event_type: string
action_type: send_email

```

<h3 id="createcastask-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[CasCreate](#schemacascreate)|true|Data for a new cas task|

> Example responses

> 200 Response

```json
{
  "request_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
  "object_uuid": "690de890-13c0-4e76-8a01-e10ba8786e53"
}
```

<h3 id="createcastask-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[CreateResponse](#schemacreateresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getCasTask

<a id="opIdgetCasTask"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/cas/tasks/{object_uuid} \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/cas/tasks/{object_uuid} HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/cas/tasks/{object_uuid}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/cas/tasks/{object_uuid}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/cas/tasks/{object_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/cas/tasks/{object_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/cas/tasks/{object_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/cas/tasks/{object_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/cas/tasks/{object_uuid}`

*Find object by uuid*

Returns a single cas task

<h3 id="getcastask-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|object_uuid|path|string|true|uuid of cas task|

> Example responses

> 200 Response

```json
{
  "task": {
    "action_type": "send_email",
    "change_time": "2018-08-28T08:15:36Z",
    "status": "string",
    "labels": [
      "string"
    ],
    "object_uuid": "string",
    "name": "string",
    "event_type": "string",
    "action_payload": {},
    "active": "string",
    "filters": [
      {
        "operator": "string",
        "field": "string",
        "comparison_value": 0
      }
    ],
    "create_time": "2018-08-28T08:15:36Z"
  }
}
```

<h3 id="getcastask-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[CasTaskGetResponse](#schemacastaskgetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## updateCasTask

<a id="opIdupdateCasTask"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH https://api.gridscale.io//objects/cas/tasks/{object_uuid} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
PATCH https://api.gridscale.io//objects/cas/tasks/{object_uuid} HTTP/1.1
Host: api.gridscale.io
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/cas/tasks/{object_uuid}',
  method: 'patch',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "action_payload": {},
  "name": "string",
  "labels": [
    "string"
  ],
  "filters": [
    {
      "operator": "string",
      "field": "string",
      "comparison_value": 0
    }
  ],
  "status": "string",
  "active": true,
  "event_type": "string",
  "action_type": "send_email"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/cas/tasks/{object_uuid}',
{
  method: 'PATCH',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.patch 'https://api.gridscale.io//objects/cas/tasks/{object_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.patch('https://api.gridscale.io//objects/cas/tasks/{object_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/cas/tasks/{object_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "https://api.gridscale.io//objects/cas/tasks/{object_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /objects/cas/tasks/{object_uuid}`

*Updated cas task*

PATCH https://api.gridscale.io/objects/cas/tasks/{cas_uuid}

> Body parameter

```json
{
  "action_payload": {},
  "name": "string",
  "labels": [
    "string"
  ],
  "filters": [
    {
      "operator": "string",
      "field": "string",
      "comparison_value": 0
    }
  ],
  "status": "string",
  "active": true,
  "event_type": "string",
  "action_type": "send_email"
}
```

<h3 id="updatecastask-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|object_uuid|path|string|true|object that need to be updated|
|body|body|[CasCreate](#schemacascreate)|true|Updated cas task|

> Example responses

> 202 Response

```json
{
  "request_uuid": "54be0369-9ef1-431f-b54b-cebc7cd8ff40"
}
```

<h3 id="updatecastask-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<h3 id="updatecastask-responseschema">Response Schema</h3>

Status Code **202**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» request_uuid|string(uuid)|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## deleteCasTask

<a id="opIddeleteCasTask"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE https://api.gridscale.io//objects/cas/tasks/{object_uuid} \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
DELETE https://api.gridscale.io//objects/cas/tasks/{object_uuid} HTTP/1.1
Host: api.gridscale.io

```

```javascript
var headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/cas/tasks/{object_uuid}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/cas/tasks/{object_uuid}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.delete 'https://api.gridscale.io//objects/cas/tasks/{object_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.delete('https://api.gridscale.io//objects/cas/tasks/{object_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/cas/tasks/{object_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://api.gridscale.io//objects/cas/tasks/{object_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /objects/cas/tasks/{object_uuid}`

*delete cas task*

DELETE https://api.gridscale.io/objects/cas/tasks/{cas_uuid}

<h3 id="deletecastask-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|object_uuid|path|string|true|object that need to be deleted|

<h3 id="deletecastask-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|The request was successful, but the answer deliberately contains no data.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getCasEvents

<a id="opIdgetCasEvents"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/cas/events \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/cas/events HTTP/1.1
Host: api.gridscale.io

```

```javascript
var headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/cas/events',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/cas/events',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/cas/events',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/cas/events', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/cas/events");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/cas/events", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/cas/events`

*Find cas events event*

Returns cas' event

<h3 id="getcasevents-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|None|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## get__objects_cas_actions

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/cas/actions \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/cas/actions HTTP/1.1
Host: api.gridscale.io

```

```javascript
var headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/cas/actions',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/cas/actions',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/cas/actions',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/cas/actions', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/cas/actions");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/cas/actions", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/cas/actions`

*Find cas action *

Returns cas' action

<h3 id="get__objects_cas_actions-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|None|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

<h1 id="API-specification-firewall">firewall</h1>

## getFirewalls

<a id="opIdgetFirewalls"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/firewalls \
  -H 'Accept: */*' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/firewalls HTTP/1.1
Host: api.gridscale.io

Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/firewalls',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'*/*',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/firewalls',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/firewalls',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/firewalls', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/firewalls");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/firewalls", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/firewalls`

*get all firewalls*

GET https://api.gridscale.io/objects/firewalls

> Example responses

> 200 Response

<h3 id="getfirewalls-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[FirewallsGetResponse](#schemafirewallsgetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## createFirewall

<a id="opIdcreateFirewall"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://api.gridscale.io//objects/firewalls \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
POST https://api.gridscale.io//objects/firewalls HTTP/1.1
Host: api.gridscale.io
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/firewalls',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "name": "test",
  "labels": [
    "webmail"
  ],
  "rules": {
    "rules-v4-in": [
      {
        "port": 20,
        "protocol": "tcp",
        "order": 0,
        "action": "accept"
      }
    ]
  }
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/firewalls',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.post 'https://api.gridscale.io//objects/firewalls',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.post('https://api.gridscale.io//objects/firewalls', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/firewalls");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.gridscale.io//objects/firewalls", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /objects/firewalls`

*Add a new firewall*

POST https://api.gridscale.io/objects/firewalls/

> Body parameter

```json
{
  "name": "test",
  "labels": [
    "webmail"
  ],
  "rules": {
    "rules-v4-in": [
      {
        "port": 20,
        "protocol": "tcp",
        "order": 0,
        "action": "accept"
      }
    ]
  }
}
```

```yaml
name: test
labels:
  - webmail
rules:
  rules-v4-in:
    - port: 20
      protocol: tcp
      order: 0
      action: accept

```

<h3 id="createfirewall-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[FirewallCreate](#schemafirewallcreate)|true|Data for a new firewall|

> Example responses

> 200 Response

```json
{
  "request_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
  "object_uuid": "690de890-13c0-4e76-8a01-e10ba8786e53"
}
```

<h3 id="createfirewall-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[CreateResponse](#schemacreateresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getFirewall

<a id="opIdgetFirewall"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/firewalls/{object_uuid} \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/firewalls/{object_uuid} HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/firewalls/{object_uuid}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/firewalls/{object_uuid}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/firewalls/{object_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/firewalls/{object_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/firewalls/{object_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/firewalls/{object_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/firewalls/{object_uuid}`

*Find object by uuid*

GET https://api.gridscale.io/objects/firewalls

<h3 id="getfirewall-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|object_uuid|path|string|true|ID of firewall|

> Example responses

> 200 Response

```json
{
  "firewall": {
    "status": "active",
    "labels": [],
    "object_uuid": "9a3fdd6e-fc2c-43a3-a8ac-6ec06898f9ce",
    "change_time": "2017-10-18T10:05:15Z",
    "rules": {
      "rules-v6-in": [
        {
          "order": 0,
          "protocol": "tcp",
          "action": "accept",
          "dst_port": "22"
        }
      ],
      "rules-v4-in": [
        {
          "order": 0,
          "protocol": "tcp",
          "action": "accept",
          "dst_port": "22"
        }
      ],
      "rules-v4-out": [],
      "rules-v6-out": []
    },
    "create_time": "2017-10-17T12:38:42Z",
    "private": false,
    "relations": {
      "networks": []
    },
    "name": "Webserver + SSH"
  }
}
```

<h3 id="getfirewall-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[FirewallGetResponse](#schemafirewallgetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## updateFirewall

<a id="opIdupdateFirewall"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH https://api.gridscale.io//objects/firewalls/{object_uuid} \
  -H 'Content-Type: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
PATCH https://api.gridscale.io//objects/firewalls/{object_uuid} HTTP/1.1
Host: api.gridscale.io
Content-Type: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/firewalls/{object_uuid}',
  method: 'patch',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "name": "Updated Name",
  "labels": [
    "webmail"
  ],
  "rules": {
    "rules-v4-in": [
      {
        "port": 20,
        "protocol": "tcp",
        "order": 0,
        "action": "accept"
      }
    ],
    "rules-v6-in": [
      {
        "port": 22,
        "protocol": "tcp",
        "order": 1,
        "action": "drop"
      }
    ]
  }
}';
const headers = {
  'Content-Type':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/firewalls/{object_uuid}',
{
  method: 'PATCH',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.patch 'https://api.gridscale.io//objects/firewalls/{object_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.patch('https://api.gridscale.io//objects/firewalls/{object_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/firewalls/{object_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "https://api.gridscale.io//objects/firewalls/{object_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /objects/firewalls/{object_uuid}`

*Updated firewall*

PATCH https://api.gridscale.io/objects/firewalls/{firewall_uuid}

> Body parameter

```json
{
  "name": "Updated Name",
  "labels": [
    "webmail"
  ],
  "rules": {
    "rules-v4-in": [
      {
        "port": 20,
        "protocol": "tcp",
        "order": 0,
        "action": "accept"
      }
    ],
    "rules-v6-in": [
      {
        "port": 22,
        "protocol": "tcp",
        "order": 1,
        "action": "drop"
      }
    ]
  }
}
```

<h3 id="updatefirewall-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|object_uuid|path|string|true|object that need to be updated|
|body|body|[FirewallUpdate](#schemafirewallupdate)|true|Updated user object|

<h3 id="updatefirewall-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|None|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## deleteId

<a id="opIddeleteId"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE https://api.gridscale.io//objects/firewalls/{object_uuid} \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
DELETE https://api.gridscale.io//objects/firewalls/{object_uuid} HTTP/1.1
Host: api.gridscale.io

```

```javascript
var headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/firewalls/{object_uuid}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/firewalls/{object_uuid}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.delete 'https://api.gridscale.io//objects/firewalls/{object_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.delete('https://api.gridscale.io//objects/firewalls/{object_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/firewalls/{object_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://api.gridscale.io//objects/firewalls/{object_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /objects/firewalls/{object_uuid}`

*delete firewall*

To delete a firewall just send a delete request to the /objects/firewalls/{firewall_uuid} endpoint.

<h3 id="deleteid-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|object_uuid|path|string|true|object that need to be deleted|

<h3 id="deleteid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|The request was successful, but the answer deliberately contains no data.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getFirewallEvents

<a id="opIdgetFirewallEvents"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/firewalls/{firewall_uuid}/events \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/firewalls/{firewall_uuid}/events HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/firewalls/{firewall_uuid}/events',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/firewalls/{firewall_uuid}/events',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/firewalls/{firewall_uuid}/events',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/firewalls/{firewall_uuid}/events', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/firewalls/{firewall_uuid}/events");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/firewalls/{firewall_uuid}/events", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/firewalls/{firewall_uuid}/events`

*Find firewall event by uuid*

GET https://api.gridscale.io/objects/firewalls/{firewall_uuid}

<h3 id="getfirewallevents-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|firewall_uuid|path|string|true|ID of storage|

> Example responses

> 200 Response

```json
{
  "events": [
    {
      "object_type": "string",
      "request_uuid": "string",
      "object_uuid": "string",
      "activity": "string",
      "request_type": "string",
      "request_status": "string",
      "change": "string",
      "timestamp": "2018-08-28T08:15:36Z",
      "user_uuid": "string"
    }
  ]
}
```

> successful operation

<h3 id="getfirewallevents-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[EventResponse](#schemaeventresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

<h1 id="API-specification-ip">ip</h1>

## getIps

<a id="opIdgetIps"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/ips \
  -H 'Accept: */*' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/ips HTTP/1.1
Host: api.gridscale.io

Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/ips',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'*/*',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/ips',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/ips',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/ips', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/ips");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/ips", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/ips`

*get all ips*

GET https://api.gridscale.io/objects/ips

> Example responses

> 200 Response

<h3 id="getips-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[IpsGetResponse](#schemaipsgetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## createIp

<a id="opIdcreateIp"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://api.gridscale.io//objects/ips \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
POST https://api.gridscale.io//objects/ips HTTP/1.1
Host: api.gridscale.io
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/ips',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "family": 4,
  "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
  "failover": true
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/ips',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.post 'https://api.gridscale.io//objects/ips',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.post('https://api.gridscale.io//objects/ips', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/ips");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.gridscale.io//objects/ips", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /objects/ips`

*Add a new ip*

POST https://api.gridscale.io/objects/ips

> Body parameter

```json
{
  "family": 4,
  "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
  "failover": true
}
```

```yaml
family: 4
location_uuid: 45ed677b-3702-4b36-be2a-a2eab9827950
failover: true

```

<h3 id="createip-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[IpCreate](#schemaipcreate)|true|Data for a new ip|

> Example responses

> 200 Response

```json
{
  "request_uuid": "8e9a4818-d145-4aa3-918a-60cc32b37e96",
  "ip": "123.123.12.1",
  "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
  "prefix": "123.123.12.1/32"
}
```

<h3 id="createip-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[IpCreateResponse](#schemaipcreateresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getIp

<a id="opIdgetIp"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/ips/{object_uuid} \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/ips/{object_uuid} HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/ips/{object_uuid}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/ips/{object_uuid}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/ips/{object_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/ips/{object_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/ips/{object_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/ips/{object_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/ips/{object_uuid}`

*Find object by uuid*

GET https://api.gridscale.io/objects/ips/{ip_uuid}

<h3 id="getip-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|object_uuid|path|string|true|uuid of ip|

> Example responses

> 200 Response

```json
{
  "ip": {
    "create_time": "2018-02-01T13:48:13Z",
    "status": "active",
    "relations": {
      "loadbalancers": [],
      "servers": [
        {
          "create_time": "2018-02-20T11:51:18Z",
          "server_name": "server with a new name2",
          "server_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x"
        }
      ]
    },
    "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
    "location_country": "de",
    "prefix": "123.123.12.1/128",
    "delete_block": false,
    "failover": false,
    "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
    "location_name": "de/fra",
    "labels": [],
    "change_time": "2018-02-01T13:48:13Z",
    "ip": "123.123.12.1",
    "family": 6,
    "location_iata": "fra",
    "reverse_dns": "static-123-123-123-123.ipv6.exampleserver.com",
    "current_price": 0,
    "usage_in_minutes": 0,
    "name": "Default IP"
  }
}
```

<h3 id="getip-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[IpGetResponse](#schemaipgetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## updateIp

<a id="opIdupdateIp"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH https://api.gridscale.io//objects/ips/{object_uuid} \
  -H 'Content-Type: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
PATCH https://api.gridscale.io//objects/ips/{object_uuid} HTTP/1.1
Host: api.gridscale.io
Content-Type: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/ips/{object_uuid}',
  method: 'patch',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "name": "update swagger ip",
  "l2security": true
}';
const headers = {
  'Content-Type':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/ips/{object_uuid}',
{
  method: 'PATCH',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.patch 'https://api.gridscale.io//objects/ips/{object_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.patch('https://api.gridscale.io//objects/ips/{object_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/ips/{object_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "https://api.gridscale.io//objects/ips/{object_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /objects/ips/{object_uuid}`

*Updated storage*

PATCH https://api.gridscale.io/objects/ips/{ip_uuid}

> Body parameter

```json
{
  "name": "update swagger ip",
  "l2security": true
}
```

<h3 id="updateip-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|object_uuid|path|string|true|object that need to be updated|
|body|body|[IpUpdate](#schemaipupdate)|true|Updated user object|

<h3 id="updateip-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## deleteIp

<a id="opIddeleteIp"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE https://api.gridscale.io//objects/ips/{object_uuid} \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
DELETE https://api.gridscale.io//objects/ips/{object_uuid} HTTP/1.1
Host: api.gridscale.io

```

```javascript
var headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/ips/{object_uuid}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/ips/{object_uuid}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.delete 'https://api.gridscale.io//objects/ips/{object_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.delete('https://api.gridscale.io//objects/ips/{object_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/ips/{object_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://api.gridscale.io//objects/ips/{object_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /objects/ips/{object_uuid}`

*delete storage*

DELETE https://api.gridscale.io/objects/ips/{ip_uuid}

<h3 id="deleteip-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|object_uuid|path|string|true|object that need to be deleted|

<h3 id="deleteip-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|The request was successful, but the answer deliberately contains no data.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getIpEvents

<a id="opIdgetIpEvents"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//ips/{ip_uuid}/events \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//ips/{ip_uuid}/events HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//ips/{ip_uuid}/events',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//ips/{ip_uuid}/events',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//ips/{ip_uuid}/events',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//ips/{ip_uuid}/events', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//ips/{ip_uuid}/events");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//ips/{ip_uuid}/events", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /ips/{ip_uuid}/events`

*Find ip event by uuid*

GET https://api.gridscale.io/objects/ips/{ip_uuid}/events

<h3 id="getipevents-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ip_uuid|path|string|true|uuid of ip|

> Example responses

> 200 Response

```json
{
  "events": [
    {
      "object_type": "string",
      "request_uuid": "string",
      "object_uuid": "string",
      "activity": "string",
      "request_type": "string",
      "request_status": "string",
      "change": "string",
      "timestamp": "2018-08-28T08:15:36Z",
      "user_uuid": "string"
    }
  ]
}
```

> successful operation

<h3 id="getipevents-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[EventResponse](#schemaeventresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

<h1 id="API-specification-isoimage">isoimage</h1>

## getIsoimages

<a id="opIdgetIsoimages"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/isoimages \
  -H 'Accept: */*' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/isoimages HTTP/1.1
Host: api.gridscale.io

Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/isoimages',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'*/*',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/isoimages',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/isoimages',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/isoimages', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/isoimages");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/isoimages", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/isoimages`

*get all isoimages*

POST https://api.gridscale.io/objects/isoimages

> Example responses

> 200 Response

<h3 id="getisoimages-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[IsoimagesGetResponse](#schemaisoimagesgetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## createIsoimages

<a id="opIdcreateIsoimages"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://api.gridscale.io//objects/isoimages \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
POST https://api.gridscale.io//objects/isoimages HTTP/1.1
Host: api.gridscale.io
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/isoimages',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "name": "swagger iso new",
  "source_url": "http://releases.ubuntu.com/16.04.4/ubuntu-16.04.4-server-amd64.iso?_ga=2.188975915.108704605.1521033305-403279979.1521033305",
  "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/isoimages',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.post 'https://api.gridscale.io//objects/isoimages',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.post('https://api.gridscale.io//objects/isoimages', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/isoimages");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.gridscale.io//objects/isoimages", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /objects/isoimages`

*Add a new isoimage*

POST https://api.gridscale.io/objects/isoimages

> Body parameter

```json
{
  "name": "swagger iso new",
  "source_url": "http://releases.ubuntu.com/16.04.4/ubuntu-16.04.4-server-amd64.iso?_ga=2.188975915.108704605.1521033305-403279979.1521033305",
  "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950"
}
```

```yaml
name: swagger iso new
source_url: >-
  http://releases.ubuntu.com/16.04.4/ubuntu-16.04.4-server-amd64.iso?_ga=2.188975915.108704605.1521033305-403279979.1521033305
location_uuid: 45ed677b-3702-4b36-be2a-a2eab9827950

```

<h3 id="createisoimages-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[IsoimageCreate](#schemaisoimagecreate)|true|Data for a new isoimage|

> Example responses

> 200 Response

```json
{
  "request_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
  "object_uuid": "690de890-13c0-4e76-8a01-e10ba8786e53"
}
```

<h3 id="createisoimages-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[CreateResponse](#schemacreateresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getIsoimage

<a id="opIdgetIsoimage"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/isoimages/{object_uuid} \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/isoimages/{object_uuid} HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/isoimages/{object_uuid}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/isoimages/{object_uuid}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/isoimages/{object_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/isoimages/{object_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/isoimages/{object_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/isoimages/{object_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/isoimages/{object_uuid}`

*Find object by uuid*

GET https://api.gridscale.io/objects/isoimages/{isoimage_uuid}

<h3 id="getisoimage-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|object_uuid|path|string|true|ID of isoimage|

> Example responses

> 200 Response

```json
{
  "isoimage": {
    "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
    "relations": {
      "servers": []
    },
    "description": null,
    "location_name": "de/fra",
    "source_url": "http://de.releases.ubuntu.com/16.04.3/ubuntu-16.04.3-server-amd64.iso",
    "labels": [],
    "location_iata": "fra",
    "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
    "status": "active",
    "create_time": "2017-10-25T12:39:23Z",
    "name": "Ubuntu 16.04.03 LTS",
    "version": null,
    "location_country": "de",
    "usage_in_minutes": 0,
    "private": false,
    "change_time": "2017-10-26T15:52:34Z",
    "capacity": 1,
    "current_price": 0
  }
}
```

<h3 id="getisoimage-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[IsoimageGetResponse](#schemaisoimagegetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## updateIsoimage

<a id="opIdupdateIsoimage"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH https://api.gridscale.io//objects/isoimages/{object_uuid} \
  -H 'Content-Type: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
PATCH https://api.gridscale.io//objects/isoimages/{object_uuid} HTTP/1.1
Host: api.gridscale.io
Content-Type: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/isoimages/{object_uuid}',
  method: 'patch',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "name": "swagger iso update"
}';
const headers = {
  'Content-Type':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/isoimages/{object_uuid}',
{
  method: 'PATCH',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.patch 'https://api.gridscale.io//objects/isoimages/{object_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.patch('https://api.gridscale.io//objects/isoimages/{object_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/isoimages/{object_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "https://api.gridscale.io//objects/isoimages/{object_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /objects/isoimages/{object_uuid}`

*Updated isoimage*

PATCH https://api.gridscale.io/objects/isoimages/{isoimage_uuid}

> Body parameter

```json
{
  "name": "swagger iso update"
}
```

<h3 id="updateisoimage-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|object_uuid|path|string|true|object that need to be updated|
|body|body|[IsoimageUpdate](#schemaisoimageupdate)|true|Updated user object|

<h3 id="updateisoimage-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|The request was successful, but the answer deliberately contains no data.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## deleteIsoimage

<a id="opIddeleteIsoimage"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE https://api.gridscale.io//objects/isoimages/{object_uuid} \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
DELETE https://api.gridscale.io//objects/isoimages/{object_uuid} HTTP/1.1
Host: api.gridscale.io

```

```javascript
var headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/isoimages/{object_uuid}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/isoimages/{object_uuid}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.delete 'https://api.gridscale.io//objects/isoimages/{object_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.delete('https://api.gridscale.io//objects/isoimages/{object_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/isoimages/{object_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://api.gridscale.io//objects/isoimages/{object_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /objects/isoimages/{object_uuid}`

*delete isoimage*

DELETE https://api.gridscale.io/objects/isoimages/{isoimage_uuid}

<h3 id="deleteisoimage-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|object_uuid|path|string|true|object that need to be deleted|

<h3 id="deleteisoimage-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|The request was successful, but the answer deliberately contains no data.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getIsoimageEvents

<a id="opIdgetIsoimageEvents"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/isoimages/{isoimage_uuid}/events \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/isoimages/{isoimage_uuid}/events HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/isoimages/{isoimage_uuid}/events',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/isoimages/{isoimage_uuid}/events',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/isoimages/{isoimage_uuid}/events',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/isoimages/{isoimage_uuid}/events', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/isoimages/{isoimage_uuid}/events");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/isoimages/{isoimage_uuid}/events", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/isoimages/{isoimage_uuid}/events`

*Find isoimage event by uuid*

GET https://api.gridscale.io/objects/isoimages/{isoimage_uuid}/events

<h3 id="getisoimageevents-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|isoimage_uuid|path|string|true|uuid of Isoimage|

> Example responses

> 200 Response

```json
{
  "events": [
    {
      "object_type": "string",
      "request_uuid": "string",
      "object_uuid": "string",
      "activity": "string",
      "request_type": "string",
      "request_status": "string",
      "change": "string",
      "timestamp": "2018-08-28T08:15:36Z",
      "user_uuid": "string"
    }
  ]
}
```

> successful operation

<h3 id="getisoimageevents-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[EventResponse](#schemaeventresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

<h1 id="API-specification-network">network</h1>

## getNetworks

<a id="opIdgetNetworks"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/networks \
  -H 'Accept: */*' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/networks HTTP/1.1
Host: api.gridscale.io

Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/networks',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'*/*',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/networks',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/networks',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/networks', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/networks");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/networks", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/networks`

*Get all Networks*

GET https://api.gridscale.io/objects/networks

> Example responses

> 200 Response

<h3 id="getnetworks-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[NetworksGetResponse](#schemanetworksgetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## createNetworks

<a id="opIdcreateNetworks"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://api.gridscale.io//objects/networks \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
POST https://api.gridscale.io//objects/networks HTTP/1.1
Host: api.gridscale.io
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/networks',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "name": "string",
  "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
  "l2security": true
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/networks',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.post 'https://api.gridscale.io//objects/networks',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.post('https://api.gridscale.io//objects/networks', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/networks");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.gridscale.io//objects/networks", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /objects/networks`

*create Networks*

POST https://api.gridscale.io/objects/networks

> Body parameter

```json
{
  "name": "string",
  "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
  "l2security": true
}
```

```yaml
name: string
location_uuid: 45ed677b-3702-4b36-be2a-a2eab9827950
l2security: true

```

<h3 id="createnetworks-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[NetworkCreate](#schemanetworkcreate)|true|Data for a new Network|

> Example responses

> 202 Response

```json
{
  "request_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
  "object_uuid": "690de890-13c0-4e76-8a01-e10ba8786e53"
}
```

<h3 id="createnetworks-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|successful operation|[CreateResponse](#schemacreateresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getNetwork

<a id="opIdgetNetwork"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/networks/{network_uuid} \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/networks/{network_uuid} HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/networks/{network_uuid}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/networks/{network_uuid}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/networks/{network_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/networks/{network_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/networks/{network_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/networks/{network_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/networks/{network_uuid}`

*Get a network*

GET https://api.gridscale.io/objects/networks/{network_uuid}

<h3 id="getnetwork-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|network_uuid|path|string|true|The UUID of an object is always unique, and refers to a specific object.|

> Example responses

> 200 Response

```json
{
  "network": {
    "location_country": "de",
    "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
    "public_net": false,
    "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
    "network_type": "network",
    "name": "test",
    "delete_block": false,
    "status": "active",
    "create_time": "2018-03-14T08:04:16Z",
    "l2security": false,
    "relations": {
      "vlans": [],
      "servers": []
    },
    "labels": [],
    "change_time": "2018-03-14T08:04:16Z",
    "location_iata": "fra",
    "location_name": "de/fra"
  }
}
```

<h3 id="getnetwork-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[NetworkGetResponse](#schemanetworkgetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## updateNetwork

<a id="opIdupdateNetwork"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH https://api.gridscale.io//objects/networks/{network_uuid} \
  -H 'Content-Type: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
PATCH https://api.gridscale.io//objects/networks/{network_uuid} HTTP/1.1
Host: api.gridscale.io
Content-Type: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/networks/{network_uuid}',
  method: 'patch',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "name": "new_name",
  "l2security": false
}';
const headers = {
  'Content-Type':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/networks/{network_uuid}',
{
  method: 'PATCH',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.patch 'https://api.gridscale.io//objects/networks/{network_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.patch('https://api.gridscale.io//objects/networks/{network_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/networks/{network_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "https://api.gridscale.io//objects/networks/{network_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /objects/networks/{network_uuid}`

*Update a network*

PATCH https://api.gridscale.io/objects/networks/{network_uuid}

> Body parameter

```json
{
  "name": "new_name",
  "l2security": false
}
```

<h3 id="updatenetwork-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|network_uuid|path|string|true|object that need to be updated|
|body|body|[NetworkUpdate](#schemanetworkupdate)|true|Updated user object|

<h3 id="updatenetwork-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|The request was successful, but the answer deliberately contains no data.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## deleteNetwork

<a id="opIddeleteNetwork"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE https://api.gridscale.io//objects/networks/{network_uuid} \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
DELETE https://api.gridscale.io//objects/networks/{network_uuid} HTTP/1.1
Host: api.gridscale.io

```

```javascript
var headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/networks/{network_uuid}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/networks/{network_uuid}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.delete 'https://api.gridscale.io//objects/networks/{network_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.delete('https://api.gridscale.io//objects/networks/{network_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/networks/{network_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://api.gridscale.io//objects/networks/{network_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /objects/networks/{network_uuid}`

*delete network*

DELETE https://api.gridscale.io/objects/networks/{network_uuid}

<h3 id="deletenetwork-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|network_uuid|path|string|true|object that need to be deleted|

<h3 id="deletenetwork-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|The request was successful, but the answer deliberately contains no data.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getNetworkEvents

<a id="opIdgetNetworkEvents"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/networks/{network_uuid}/events \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/networks/{network_uuid}/events HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/networks/{network_uuid}/events',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/networks/{network_uuid}/events',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/networks/{network_uuid}/events',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/networks/{network_uuid}/events', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/networks/{network_uuid}/events");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/networks/{network_uuid}/events", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/networks/{network_uuid}/events`

*Find network event by uuid*

GET https://api.gridscale.io/objects/networks/{network_uuid}/events

<h3 id="getnetworkevents-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|network_uuid|path|string|true|ID of storage|

> Example responses

> 200 Response

```json
{
  "events": [
    {
      "object_type": "string",
      "request_uuid": "string",
      "object_uuid": "string",
      "activity": "string",
      "request_type": "string",
      "request_status": "string",
      "change": "string",
      "timestamp": "2018-08-28T08:15:36Z",
      "user_uuid": "string"
    }
  ]
}
```

> successful operation

<h3 id="getnetworkevents-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[EventResponse](#schemaeventresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

<h1 id="API-specification-object-storage">object storage</h1>

## getAccessKeys

<a id="opIdgetAccessKeys"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/objectstorages/access_keys \
  -H 'Accept: */*' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/objectstorages/access_keys HTTP/1.1
Host: api.gridscale.io

Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/objectstorages/access_keys',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'*/*',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/objectstorages/access_keys',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/objectstorages/access_keys',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/objectstorages/access_keys', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/objectstorages/access_keys");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/objectstorages/access_keys", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/objectstorages/access_keys`

*get all access_keys*

GET https://api.gridscale.io/objects/objectstorages/access_keys

> Example responses

> 200 Response

<h3 id="getaccesskeys-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[AccessKeysGetResponse](#schemaaccesskeysgetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## createAccessKey

<a id="opIdcreateAccessKey"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://api.gridscale.io//objects/objectstorages/access_keys \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
POST https://api.gridscale.io//objects/objectstorages/access_keys HTTP/1.1
Host: api.gridscale.io
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/objectstorages/access_keys',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "secret_key": "string",
  "access_key": "string",
  "user": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/objectstorages/access_keys',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.post 'https://api.gridscale.io//objects/objectstorages/access_keys',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.post('https://api.gridscale.io//objects/objectstorages/access_keys', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/objectstorages/access_keys");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.gridscale.io//objects/objectstorages/access_keys", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /objects/objectstorages/access_keys`

*Add a new access key*

POST https://api.gridscale.io/objects/fobjectstorages/access_keys

> Body parameter

```json
{
  "secret_key": "string",
  "access_key": "string",
  "user": "string"
}
```

```yaml
secret_key: string
access_key: string
user: string

```

<h3 id="createaccesskey-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[AccessKeyCreate](#schemaaccesskeycreate)|true|Data for a new Accesss key|

> Example responses

> 200 Response

```json
{
  "access_key": {
    "secret_key": "string",
    "access_key": "string"
  },
  "request_uuid": "string"
}
```

<h3 id="createaccesskey-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[AccessKeyCreateResponse](#schemaaccesskeycreateresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getAccessKey

<a id="opIdgetAccessKey"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/objectstorages/access_keys/{accesskey} \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/objectstorages/access_keys/{accesskey} HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/objectstorages/access_keys/{accesskey}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/objectstorages/access_keys/{accesskey}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/objectstorages/access_keys/{accesskey}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/objectstorages/access_keys/{accesskey}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/objectstorages/access_keys/{accesskey}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/objectstorages/access_keys/{accesskey}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/objectstorages/access_keys/{accesskey}`

*Find access key*

GET https://api.gridscale.io/objects/objectstorages/access_keys/{accesskey}

<h3 id="getaccesskey-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|accesskey|path|string|true|ID of firewall|

> Example responses

> 200 Response

```json
{
  "access_key": {
    "secret_key": "{secret_key}",
    "access_key": "{access_key}"
  }
}
```

<h3 id="getaccesskey-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[AccessKeyGetResponse](#schemaaccesskeygetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## deleteAccessKey

<a id="opIddeleteAccessKey"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE https://api.gridscale.io//objects/objectstorages/access_keys/{accesskey} \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
DELETE https://api.gridscale.io//objects/objectstorages/access_keys/{accesskey} HTTP/1.1
Host: api.gridscale.io

```

```javascript
var headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/objectstorages/access_keys/{accesskey}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/objectstorages/access_keys/{accesskey}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.delete 'https://api.gridscale.io//objects/objectstorages/access_keys/{accesskey}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.delete('https://api.gridscale.io//objects/objectstorages/access_keys/{accesskey}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/objectstorages/access_keys/{accesskey}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://api.gridscale.io//objects/objectstorages/access_keys/{accesskey}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /objects/objectstorages/access_keys/{accesskey}`

*delete access key*

GET https://api.gridscale.io/objects/objectstorages/access_keys/{accesskey}

<h3 id="deleteaccesskey-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|accesskey|path|string|true|object that need to be deleted|

<h3 id="deleteaccesskey-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|The request was successful, but the answer deliberately contains no data.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getBuckets

<a id="opIdgetBuckets"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/objectstorages/buckets \
  -H 'Accept: */*' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/objectstorages/buckets HTTP/1.1
Host: api.gridscale.io

Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/objectstorages/buckets',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'*/*',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/objectstorages/buckets',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/objectstorages/buckets',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/objectstorages/buckets', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/objectstorages/buckets");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/objectstorages/buckets", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/objectstorages/buckets`

*get all buckets*

GET https://api.gridscale.io/objects/objectstorages/buckets

> Example responses

> 200 Response

<h3 id="getbuckets-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[BucketsGetResponse](#schemabucketsgetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getBucket

<a id="opIdgetBucket"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/objectstorages/buckets/{bucket_name} \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/objectstorages/buckets/{bucket_name} HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/objectstorages/buckets/{bucket_name}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/objectstorages/buckets/{bucket_name}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/objectstorages/buckets/{bucket_name}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/objectstorages/buckets/{bucket_name}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/objectstorages/buckets/{bucket_name}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/objectstorages/buckets/{bucket_name}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/objectstorages/buckets/{bucket_name}`

*Find a bucket*

GET https://api.gridscale.io/objects/objectstorages/buckets/{bucket_name}

<h3 id="getbucket-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|bucket_name|path|string|true|ID of firewall|

> Example responses

> 200 Response

```json
{
  "Bucket": {
    "name": "string",
    "ussage": {
      "size_kb": 0,
      "num_objects": 0
    }
  }
}
```

<h3 id="getbucket-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[BucketGetResponse](#schemabucketgetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

<h1 id="API-specification-request">request</h1>

## getRequest

<a id="opIdgetRequest"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//requests/{request_uuid} \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//requests/{request_uuid} HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//requests/{request_uuid}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//requests/{request_uuid}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//requests/{request_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//requests/{request_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//requests/{request_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//requests/{request_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /requests/{request_uuid}`

*get a request*

GET https://api.gridscale.io/requests/{request_uuid} To receive detailed information regarding a specific server, just append the server_uuid onto the /servers endpoint.

<h3 id="getrequest-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|request_uuid|path|string|true|uuid of server|

> Example responses

> 200 Response

```json
{
  "4e10fb40-47e3-4fd0-aaf3-c16335757f93": {
    "create_time": "2018-06-04T11:51:34Z",
    "status": "done",
    "message": "Success."
  }
}
```

<h3 id="getrequest-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[RequestGetResponse](#schemarequestgetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

<h1 id="API-specification-server">server</h1>

## getServers

<a id="opIdgetServers"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/servers \
  -H 'Accept: */*' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/servers HTTP/1.1
Host: api.gridscale.io

Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/servers',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'*/*',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/servers',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/servers',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/servers', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/servers");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/servers", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/servers`

*Get all servers*

GET https://api.gridscale.io/objects/servers

> Example responses

> 200 Response

<h3 id="getservers-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[ServersGetResponse](#schemaserversgetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## createServer

<a id="opIdcreateServer"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://api.gridscale.io//objects/servers \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
POST https://api.gridscale.io//objects/servers HTTP/1.1
Host: api.gridscale.io
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/servers',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "name": "string",
  "cores": 1,
  "memory": 2,
  "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/servers',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.post 'https://api.gridscale.io//objects/servers',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.post('https://api.gridscale.io//objects/servers', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/servers");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.gridscale.io//objects/servers", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /objects/servers`

*create a server*

POST https://api.gridscale.io/objects/servers Creating a simple server with our API is easy, you can use the code to the right, to create a server.

> Body parameter

```json
{
  "name": "string",
  "cores": 1,
  "memory": 2,
  "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950"
}
```

<h3 id="createserver-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[ServerCreate](#schemaservercreate)|true|Data for a new serve  r|

> Example responses

> 200 Response

```json
{
  "request_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
  "object_uuid": "690de890-13c0-4e76-8a01-e10ba8786e53"
}
```

<h3 id="createserver-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[CreateResponse](#schemacreateresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getServer

<a id="opIdgetServer"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/servers/{server_uuid} \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/servers/{server_uuid} HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/servers/{server_uuid}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/servers/{server_uuid}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/servers/{server_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/servers/{server_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/servers/{server_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/servers/{server_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/servers/{server_uuid}`

*get a server*

GET https://api.gridscale.io/objects/servers/{server_uuid} To receive detailed information regarding a specific server, just append the server_uuid onto the /servers endpoint.

<h3 id="getserver-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|server_uuid|path|string|true|uuid of server|

> Example responses

> 200 Response

```json
{
  "server": {
    "cores": 1,
    "relations": {
      "storages": [
        {
          "capacity": 11,
          "server_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
          "last_used_template": "ec4ef18f-84df-42bb-b7c4-c2957635ee53",
          "controller": 0,
          "license_product_no": null,
          "bus": 0,
          "target": 0,
          "create_time": "2018-03-14T13:33:24Z",
          "lun": 0,
          "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
          "bootdevice": true,
          "object_name": "Ubunto 16.04 Storage",
          "storage_type": "storage"
        }
      ],
      "public_ips": [
        {
          "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
          "prefix": "1x:12:xx:12:12:12/32",
          "ip": "123.123.12.1",
          "server_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
          "create_time": "2018-03-14T13:33:14Z",
          "family": 4
        },
        {
          "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
          "prefix": "123.123.12.1/128",
          "ip": "123.123.12.1",
          "server_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
          "create_time": "2018-03-14T13:33:16Z",
          "family": 6
        }
      ],
      "networks": [
        {
          "network_type": "network",
          "vlan": null,
          "create_time": "2018-03-14T13:33:13Z",
          "ordering": 0,
          "bootdevice": false,
          "mac": "16:f7:22:9e:56:01",
          "vxlan": null,
          "mcast": null,
          "server_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
          "l3security": [],
          "firewall_template_uuid": null,
          "partner_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
          "object_name": "Public Network test",
          "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
          "network_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
          "public_net": true,
          "firewall": null,
          "l2security": true
        }
      ],
      "isoimages": []
    },
    "legacy": false,
    "memory": 2,
    "console_token": "$console_token",
    "usage_in_minutes_memory": 47331,
    "auto_recovery": true,
    "create_time": "2018-03-14T13:33:13Z",
    "current_price": 9.491665,
    "location_country": "de",
    "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
    "usage_in_minutes_cores": 0,
    "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
    "change_time": "2018-03-19T11:40:55Z",
    "availability_zone": null,
    "location_iata": "fra",
    "labels": [],
    "hardware_profile": "default",
    "location_name": "de/fra",
    "power": true,
    "name": "Ubunto 16.04",
    "status": "active"
  }
}
```

<h3 id="getserver-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[ServerGetResponse](#schemaservergetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## update Server

<a id="opIdupdate Server"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH https://api.gridscale.io//objects/servers/{server_uuid} \
  -H 'Content-Type: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
PATCH https://api.gridscale.io//objects/servers/{server_uuid} HTTP/1.1
Host: api.gridscale.io
Content-Type: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/servers/{server_uuid}',
  method: 'patch',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "name": "Updated Name"
}';
const headers = {
  'Content-Type':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/servers/{server_uuid}',
{
  method: 'PATCH',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.patch 'https://api.gridscale.io//objects/servers/{server_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.patch('https://api.gridscale.io//objects/servers/{server_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/servers/{server_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "https://api.gridscale.io//objects/servers/{server_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /objects/servers/{server_uuid}`

*update a server*

PATCH https://api.gridscale.io/objects/servers/{server_uuid} Updating a server with our API is easy, you can use the code to the right, to rename a server, and much more by adding new parameters to your request

> Body parameter

```json
{
  "name": "Updated Name"
}
```

<h3 id="update-server-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|server_uuid|path|string|true|object that need to be updated|
|body|body|[ServerUpdate](#schemaserverupdate)|true|Updated user object|

<h3 id="update-server-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|The request was successful, but the answer deliberately contains no data.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## deleteServer

<a id="opIddeleteServer"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE https://api.gridscale.io//objects/servers/{server_uuid} \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
DELETE https://api.gridscale.io//objects/servers/{server_uuid} HTTP/1.1
Host: api.gridscale.io

```

```javascript
var headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/servers/{server_uuid}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/servers/{server_uuid}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.delete 'https://api.gridscale.io//objects/servers/{server_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.delete('https://api.gridscale.io//objects/servers/{server_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/servers/{server_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://api.gridscale.io//objects/servers/{server_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /objects/servers/{server_uuid}`

*delete a server*

DELETE https://api.gridscale.io/objects/servers/{server_uuid} o Delete a server, just append the server_uuid onto the /servers endpoint and send a DELETE request along with your authentication credentials

<h3 id="deleteserver-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|server_uuid|path|string|true|object that need to be deleted|

<h3 id="deleteserver-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|The request was successful, but the answer deliberately contains no data.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getServerEvents

<a id="opIdgetServerEvents"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/servers/{server_uuid}/events \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/servers/{server_uuid}/events HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/servers/{server_uuid}/events',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/servers/{server_uuid}/events',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/servers/{server_uuid}/events',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/servers/{server_uuid}/events', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/servers/{server_uuid}/events");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/servers/{server_uuid}/events", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/servers/{server_uuid}/events`

*Find server event by uuid*

GET https://api.gridscale.io/objects/servers/{server_uuid}/events

<h3 id="getserverevents-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|server_uuid|path|string|true|The events endpoint for a server, returns a list of all the events on that object. You can alternatively find them as Audit Logs in your expert panel.|

> Example responses

> 200 Response

```json
{
  "events": [
    {
      "object_type": "string",
      "request_uuid": "string",
      "object_uuid": "string",
      "activity": "string",
      "request_type": "string",
      "request_status": "string",
      "change": "string",
      "timestamp": "2018-08-28T08:15:36Z",
      "user_uuid": "string"
    }
  ]
}
```

> successful operation

<h3 id="getserverevents-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[EventResponse](#schemaeventresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getServerPower

<a id="opIdgetServerPower"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/servers/{server_uuid}/power \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/servers/{server_uuid}/power HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/servers/{server_uuid}/power',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/servers/{server_uuid}/power',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/servers/{server_uuid}/power',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/servers/{server_uuid}/power', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/servers/{server_uuid}/power");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/servers/{server_uuid}/power", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/servers/{server_uuid}/power`

*get power status*

GET https://api.gridscale.io/objects/servers/{server_uuid}/power To find out the status of your sever just send a GET request to the /power endpoint for the specified server.

<h3 id="getserverpower-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|server_uuid|path|string|true|ID of storage|

> Example responses

> 200 Response

```json
{
  "power": true
}
```

<h3 id="getserverpower-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[ServerPowerStatus](#schemaserverpowerstatus)|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|The request was successful, but the answer deliberately contains no data.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## updateServerPower

<a id="opIdupdateServerPower"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH https://api.gridscale.io//objects/servers/{server_uuid}/power \
  -H 'Content-Type: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
PATCH https://api.gridscale.io//objects/servers/{server_uuid}/power HTTP/1.1
Host: api.gridscale.io
Content-Type: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/servers/{server_uuid}/power',
  method: 'patch',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "power": true
}';
const headers = {
  'Content-Type':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/servers/{server_uuid}/power',
{
  method: 'PATCH',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.patch 'https://api.gridscale.io//objects/servers/{server_uuid}/power',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.patch('https://api.gridscale.io//objects/servers/{server_uuid}/power', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/servers/{server_uuid}/power");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "https://api.gridscale.io//objects/servers/{server_uuid}/power", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /objects/servers/{server_uuid}/power`

*toogle the power*

PATCH https://api.gridscale.io/objects/servers/{server_uuid}/power To turn on and off a server, we need to send a PATCH request to the /power endpoint, with a JSON object, defining the status we want. If power = true, the server will be turned on, and visa-versa.

> Body parameter

```json
{
  "power": true
}
```

<h3 id="updateserverpower-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|server_uuid|path|string|true|ID of server|
|body|body|object|true|Updated user object|
|» power|body|boolean|false|none|

<h3 id="updateserverpower-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|None|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|The request was successful, but the answer deliberately contains no data.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getLinkedIps

<a id="opIdgetLinkedIps"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/servers/{server_uuid}/ips \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/servers/{server_uuid}/ips HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/servers/{server_uuid}/ips',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/servers/{server_uuid}/ips',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/servers/{server_uuid}/ips',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/servers/{server_uuid}/ips', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/servers/{server_uuid}/ips");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/servers/{server_uuid}/ips", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/servers/{server_uuid}/ips`

*get linked ips*

GET https://api.gridscale.io/objects/servers/{server_uuid}/ips

<h3 id="getlinkedips-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|server_uuid|path|string|true|ID of server|

> Example responses

> 200 Response

```json
{
  "ip_relations": [
    {
      "object_uuid": "string",
      "family": 4,
      "prefix": 0,
      "create_time": "2018-08-28T08:15:36Z",
      "server_uuid": "string",
      "ip": "string"
    }
  ]
}
```

<h3 id="getlinkedips-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[LinkedIpsGetResponse](#schemalinkedipsgetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## linkIp

<a id="opIdlinkIp"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://api.gridscale.io//objects/servers/{server_uuid}/ips \
  -H 'Content-Type: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
POST https://api.gridscale.io//objects/servers/{server_uuid}/ips HTTP/1.1
Host: api.gridscale.io
Content-Type: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/servers/{server_uuid}/ips',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "object_uuid": "77ddfb4a-5b50-430d-99bf-4c4dec1e8d0b"
}';
const headers = {
  'Content-Type':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/servers/{server_uuid}/ips',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.post 'https://api.gridscale.io//objects/servers/{server_uuid}/ips',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.post('https://api.gridscale.io//objects/servers/{server_uuid}/ips', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/servers/{server_uuid}/ips");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.gridscale.io//objects/servers/{server_uuid}/ips", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /objects/servers/{server_uuid}/ips`

*link ip*

POST https://api.gridscale.io/objects/servers/{server_uuid}/ips You will need the UUID of the IP Address and of the server, which you would like to join the IP Address to.

> Body parameter

```json
{
  "object_uuid": "77ddfb4a-5b50-430d-99bf-4c4dec1e8d0b"
}
```

<h3 id="linkip-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|server_uuid|path|string|true|server uuid|
|body|body|[LinkIp](#schemalinkip)|true|IP uuid which going to be linked|

<h3 id="linkip-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getLinkedIp

<a id="opIdgetLinkedIp"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/servers/{server_uuid}/ips/{ip_uuid} \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/servers/{server_uuid}/ips/{ip_uuid} HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/servers/{server_uuid}/ips/{ip_uuid}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/servers/{server_uuid}/ips/{ip_uuid}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/servers/{server_uuid}/ips/{ip_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/servers/{server_uuid}/ips/{ip_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/servers/{server_uuid}/ips/{ip_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/servers/{server_uuid}/ips/{ip_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/servers/{server_uuid}/ips/{ip_uuid}`

*Find linked ip*

GET https://api.gridscale.io/objects/servers/{server_uuid}/ips/{ip_uuid}

<h3 id="getlinkedip-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|server_uuid|path|string|true|The UUID of the server, that relates to the IP you are requesting.|
|ip_uuid|path|string|true|The UUID of the IP Address you're requesting.|

> Example responses

> 200 Response

```json
{
  "ip_relation": {
    "object_uuid": "string",
    "family": 4,
    "prefix": 0,
    "create_time": "2018-08-28T08:15:36Z",
    "ip": "string"
  }
}
```

<h3 id="getlinkedip-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[LinkedIpGetResponse](#schemalinkedipgetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## unlinkIp

<a id="opIdunlinkIp"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE https://api.gridscale.io//objects/servers/{server_uuid}/ips/{ip_uuid} \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
DELETE https://api.gridscale.io//objects/servers/{server_uuid}/ips/{ip_uuid} HTTP/1.1
Host: api.gridscale.io

```

```javascript
var headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/servers/{server_uuid}/ips/{ip_uuid}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/servers/{server_uuid}/ips/{ip_uuid}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.delete 'https://api.gridscale.io//objects/servers/{server_uuid}/ips/{ip_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.delete('https://api.gridscale.io//objects/servers/{server_uuid}/ips/{ip_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/servers/{server_uuid}/ips/{ip_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://api.gridscale.io//objects/servers/{server_uuid}/ips/{ip_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /objects/servers/{server_uuid}/ips/{ip_uuid}`

*delete ip relation*

DELETE https://api.gridscale.io/objects/servers/{server_uuid}/ips/{ip_uuid}

<h3 id="unlinkip-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|server_uuid|path|string|true|server uuid|
|ip_uuid|path|string|true|ip uuid|

<h3 id="unlinkip-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|None|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getLInkedStorages

<a id="opIdgetLInkedStorages"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/servers/{server_uuid}/storages \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/servers/{server_uuid}/storages HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/servers/{server_uuid}/storages',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/servers/{server_uuid}/storages',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/servers/{server_uuid}/storages',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/servers/{server_uuid}/storages', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/servers/{server_uuid}/storages");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/servers/{server_uuid}/storages", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/servers/{server_uuid}/storages`

*Get linked storages*

GET https://api.gridscale.io/objects/servers/{server_uuid}/storages

<h3 id="getlinkedstorages-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|server_uuid|path|string|true|ID of server|

> Example responses

> 200 Response

```json
{
  "storage_relations": [
    {
      "storage_type": "string",
      "target": 0,
      "bus": 0,
      "capacity": 0,
      "license_product_no": 0,
      "object_uuid": "string",
      "controller": 0,
      "lun": 0,
      "create_time": "2018-08-28T08:15:36Z",
      "server_uuid": "string",
      "last_used_template": "string",
      "bootdevice": true,
      "object_name": "string"
    }
  ]
}
```

<h3 id="getlinkedstorages-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[LinkedStoragesGetResponse](#schemalinkedstoragesgetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## linkStorage

<a id="opIdlinkStorage"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://api.gridscale.io//objects/servers/{server_uuid}/storages \
  -H 'Content-Type: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
POST https://api.gridscale.io//objects/servers/{server_uuid}/storages HTTP/1.1
Host: api.gridscale.io
Content-Type: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/servers/{server_uuid}/storages',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "object_uuid": "081b3a38-e4c0-419f-a7b3-58e3d9383fe5",
  "bootdevice": true
}';
const headers = {
  'Content-Type':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/servers/{server_uuid}/storages',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.post 'https://api.gridscale.io//objects/servers/{server_uuid}/storages',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.post('https://api.gridscale.io//objects/servers/{server_uuid}/storages', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/servers/{server_uuid}/storages");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.gridscale.io//objects/servers/{server_uuid}/storages", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /objects/servers/{server_uuid}/storages`

*link storage*

POST https://api.gridscale.io/objects/servers/{server_uuid}/storages Once the storage is linked, you'll receive an empty body, with a 202 response

> Body parameter

```json
{
  "object_uuid": "081b3a38-e4c0-419f-a7b3-58e3d9383fe5",
  "bootdevice": true
}
```

<h3 id="linkstorage-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|server_uuid|path|string|true|server uuid|
|body|body|[LinkStorage](#schemalinkstorage)|true|storage uuid which going to be linked|

<h3 id="linkstorage-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getLinkedStorage

<a id="opIdgetLinkedStorage"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/servers/{server_uuid}/storages/{storage_uuid} \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/servers/{server_uuid}/storages/{storage_uuid} HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/servers/{server_uuid}/storages/{storage_uuid}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/servers/{server_uuid}/storages/{storage_uuid}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/servers/{server_uuid}/storages/{storage_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/servers/{server_uuid}/storages/{storage_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/servers/{server_uuid}/storages/{storage_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/servers/{server_uuid}/storages/{storage_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/servers/{server_uuid}/storages/{storage_uuid}`

*Find linked storage*

GET https://api.gridscale.io/objects/servers/{server_uuid}/storages/{storage_uuid}

<h3 id="getlinkedstorage-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|server_uuid|path|string|true|ID of server|
|storage_uuid|path|string|true|ID of storage|

> Example responses

> 200 Response

```json
{
  "storage_relation": {
    "storage_type": "string",
    "target": 0,
    "bus": 0,
    "capacity": 0,
    "license_product_no": 0,
    "object_uuid": "string",
    "controller": 0,
    "lun": 0,
    "create_time": "2018-08-28T08:15:36Z",
    "last_used_template": "string",
    "bootdevice": true,
    "object_name": "string"
  }
}
```

<h3 id="getlinkedstorage-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[LinkedStorageGetResponse](#schemalinkedstoragegetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## updateLinkedStrorage

<a id="opIdupdateLinkedStrorage"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH https://api.gridscale.io//objects/servers/{server_uuid}/storages/{storage_uuid} \
  -H 'Content-Type: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
PATCH https://api.gridscale.io//objects/servers/{server_uuid}/storages/{storage_uuid} HTTP/1.1
Host: api.gridscale.io
Content-Type: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/servers/{server_uuid}/storages/{storage_uuid}',
  method: 'patch',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "bootdevice": true
}';
const headers = {
  'Content-Type':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/servers/{server_uuid}/storages/{storage_uuid}',
{
  method: 'PATCH',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.patch 'https://api.gridscale.io//objects/servers/{server_uuid}/storages/{storage_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.patch('https://api.gridscale.io//objects/servers/{server_uuid}/storages/{storage_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/servers/{server_uuid}/storages/{storage_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "https://api.gridscale.io//objects/servers/{server_uuid}/storages/{storage_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /objects/servers/{server_uuid}/storages/{storage_uuid}`

*linked storage patch*

linked storage patch

> Body parameter

```json
{
  "bootdevice": true
}
```

<h3 id="updatelinkedstrorage-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|server_uuid|path|string|true|ID of server|
|storage_uuid|path|string|true|ID of storage|
|body|body|[LinkedStorageUpdate](#schemalinkedstorageupdate)|true|Updated user object|

<h3 id="updatelinkedstrorage-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|None|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## unlinkStorage

<a id="opIdunlinkStorage"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE https://api.gridscale.io//objects/servers/{server_uuid}/storages/{storage_uuid} \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
DELETE https://api.gridscale.io//objects/servers/{server_uuid}/storages/{storage_uuid} HTTP/1.1
Host: api.gridscale.io

```

```javascript
var headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/servers/{server_uuid}/storages/{storage_uuid}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/servers/{server_uuid}/storages/{storage_uuid}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.delete 'https://api.gridscale.io//objects/servers/{server_uuid}/storages/{storage_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.delete('https://api.gridscale.io//objects/servers/{server_uuid}/storages/{storage_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/servers/{server_uuid}/storages/{storage_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://api.gridscale.io//objects/servers/{server_uuid}/storages/{storage_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /objects/servers/{server_uuid}/storages/{storage_uuid}`

*unlink storages*

DELETE https://api.gridscale.io/objects/servers/{server_uuid}/storages/{storage_uuid}

<h3 id="unlinkstorage-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|server_uuid|path|string|true|The UUID of the server, that relates to the Storage you are removing.|
|storage_uuid|path|string|true|The UUID of the Storage you are removing.|

<h3 id="unlinkstorage-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getLinkedNetworks

<a id="opIdgetLinkedNetworks"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/servers/{server_uuid}/networks \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/servers/{server_uuid}/networks HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/servers/{server_uuid}/networks',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/servers/{server_uuid}/networks',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/servers/{server_uuid}/networks',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/servers/{server_uuid}/networks', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/servers/{server_uuid}/networks");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/servers/{server_uuid}/networks", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/servers/{server_uuid}/networks`

*Get linked networks*

GET https://api.gridscale.io/objects/servers/{server_uuid}/networks

<h3 id="getlinkednetworks-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|server_uuid|path|string|true|ID of server|

> Example responses

> 200 Response

```json
{
  "network_relations": [
    {
      "network_type": "string",
      "l3security": [
        "string"
      ],
      "mcast": "string",
      "bootdevice": true,
      "network_uuid": "string",
      "l2security": "string",
      "vlan": "string",
      "server_uuid": "string",
      "mac": "string",
      "ordering": "string",
      "firewall": "string",
      "firewall_template_uuid": "string",
      "object_name": "string",
      "create_time": "2018-08-28T08:15:36Z",
      "object_uuid": "string",
      "public_net": true,
      "vxlan": "string"
    }
  ]
}
```

<h3 id="getlinkednetworks-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[LinkedNetworksGetResponse](#schemalinkednetworksgetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## linkNetwork

<a id="opIdlinkNetwork"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://api.gridscale.io//objects/servers/{server_uuid}/networks \
  -H 'Content-Type: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
POST https://api.gridscale.io//objects/servers/{server_uuid}/networks HTTP/1.1
Host: api.gridscale.io
Content-Type: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/servers/{server_uuid}/networks',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "object_uuid": "e753aa01-7f99-4325-9724-625c78e741b0"
}';
const headers = {
  'Content-Type':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/servers/{server_uuid}/networks',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.post 'https://api.gridscale.io//objects/servers/{server_uuid}/networks',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.post('https://api.gridscale.io//objects/servers/{server_uuid}/networks', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/servers/{server_uuid}/networks");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.gridscale.io//objects/servers/{server_uuid}/networks", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /objects/servers/{server_uuid}/networks`

*link network*

POST https://api.gridscale.io/objects/servers/{server_uuid}/networks

> Body parameter

```json
{
  "object_uuid": "e753aa01-7f99-4325-9724-625c78e741b0"
}
```

<h3 id="linknetwork-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|server_uuid|path|string|true|server uuid|
|body|body|[LinkNetwork](#schemalinknetwork)|true|Network UUID which is going to be linked|

<h3 id="linknetwork-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getLinkedNetwork

<a id="opIdgetLinkedNetwork"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/servers/{server_uuid}/networks/{network_uuid} \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/servers/{server_uuid}/networks/{network_uuid} HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/servers/{server_uuid}/networks/{network_uuid}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/servers/{server_uuid}/networks/{network_uuid}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/servers/{server_uuid}/networks/{network_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/servers/{server_uuid}/networks/{network_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/servers/{server_uuid}/networks/{network_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/servers/{server_uuid}/networks/{network_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/servers/{server_uuid}/networks/{network_uuid}`

*Get linked network*

GET https://api.gridscale.io/objects/servers/{server_uuid}/networks/{network_uuid}

<h3 id="getlinkednetwork-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|server_uuid|path|string|true|The UUID of the server, that relates to the Network you are requesting.|
|network_uuid|path|string|true|The UUID of the network you're requesting.|

> Example responses

> 200 Response

```json
{
  "network_relation": {
    "network_type": "string",
    "l3security": [
      "string"
    ],
    "mcast": "string",
    "bootdevice": true,
    "network_uuid": "string",
    "l2security": "string",
    "vlan": "string",
    "mac": "string",
    "ordering": "string",
    "firewall": "string",
    "firewall_template_uuid": "string",
    "object_name": "string",
    "create_time": "2018-08-28T08:15:36Z",
    "object_uuid": "string",
    "public_net": true,
    "vxlan": "string"
  }
}
```

<h3 id="getlinkednetwork-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[LinkedNetworkGetResponse](#schemalinkednetworkgetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## updateLinkedNetwork

<a id="opIdupdateLinkedNetwork"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH https://api.gridscale.io//objects/servers/{server_uuid}/networks/{network_uuid} \
  -H 'Content-Type: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
PATCH https://api.gridscale.io//objects/servers/{server_uuid}/networks/{network_uuid} HTTP/1.1
Host: api.gridscale.io
Content-Type: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/servers/{server_uuid}/networks/{network_uuid}',
  method: 'patch',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "ordering": 3,
  "bootdevice": false,
  "l3security": null
}';
const headers = {
  'Content-Type':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/servers/{server_uuid}/networks/{network_uuid}',
{
  method: 'PATCH',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.patch 'https://api.gridscale.io//objects/servers/{server_uuid}/networks/{network_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.patch('https://api.gridscale.io//objects/servers/{server_uuid}/networks/{network_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/servers/{server_uuid}/networks/{network_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "https://api.gridscale.io//objects/servers/{server_uuid}/networks/{network_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /objects/servers/{server_uuid}/networks/{network_uuid}`

*linked network patch*

PATCH https://api.gridscale.io/objects/servers/{server_uuid}/networks/{network_uuid}

> Body parameter

```json
{
  "ordering": 3,
  "bootdevice": false,
  "l3security": null
}
```

<h3 id="updatelinkednetwork-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|server_uuid|path|string|true|The UUID of the server, that relates to the network you are requesting.|
|network_uuid|path|string|true|The UUID of the network you're requesting.|
|body|body|[LinkedNetworkUpdate](#schemalinkednetworkupdate)|true|Updated user object|

<h3 id="updatelinkednetwork-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|The request was successful, but the answer deliberately contains no data.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## unlinkNetwork

<a id="opIdunlinkNetwork"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE https://api.gridscale.io//objects/servers/{server_uuid}/networks/{network_uuid} \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
DELETE https://api.gridscale.io//objects/servers/{server_uuid}/networks/{network_uuid} HTTP/1.1
Host: api.gridscale.io

```

```javascript
var headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/servers/{server_uuid}/networks/{network_uuid}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/servers/{server_uuid}/networks/{network_uuid}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.delete 'https://api.gridscale.io//objects/servers/{server_uuid}/networks/{network_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.delete('https://api.gridscale.io//objects/servers/{server_uuid}/networks/{network_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/servers/{server_uuid}/networks/{network_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://api.gridscale.io//objects/servers/{server_uuid}/networks/{network_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /objects/servers/{server_uuid}/networks/{network_uuid}`

*unlink network*

DELETE https://api.gridscale.io/objects/servers/{server_uuid}/isoiamges/{object_uuid}

<h3 id="unlinknetwork-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|server_uuid|path|string|true|The UUID of the server, that relates to the IP you are requesting.|
|network_uuid|path|string|true|The UUID of the IP Address you're requesting.|

<h3 id="unlinknetwork-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getLinkedIsoimages

<a id="opIdgetLinkedIsoimages"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/servers/{server_uuid}/isoimages \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/servers/{server_uuid}/isoimages HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/servers/{server_uuid}/isoimages',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/servers/{server_uuid}/isoimages',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/servers/{server_uuid}/isoimages',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/servers/{server_uuid}/isoimages', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/servers/{server_uuid}/isoimages");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/servers/{server_uuid}/isoimages", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/servers/{server_uuid}/isoimages`

*Find linked isoimages*

GET https://api.gridscale.io/objects/servers/{server_uuid}/isoimages

<h3 id="getlinkedisoimages-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|server_uuid|path|string|true|ID of server|

> Example responses

> 200 Response

```json
{
  "network_relations": [
    {
      "bootdevice": true,
      "object_name": "string",
      "create_time": "2018-08-28T08:15:36Z",
      "object_uuid": "string"
    }
  ]
}
```

<h3 id="getlinkedisoimages-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[LinkedIsoimagesGetResponse](#schemalinkedisoimagesgetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## linkIsoimage

<a id="opIdlinkIsoimage"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://api.gridscale.io//objects/servers/{server_uuid}/isoimages \
  -H 'Content-Type: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
POST https://api.gridscale.io//objects/servers/{server_uuid}/isoimages HTTP/1.1
Host: api.gridscale.io
Content-Type: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/servers/{server_uuid}/isoimages',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "object_uuid": "22f06c53-27a1-482f-94ed-1e464d259adf"
}';
const headers = {
  'Content-Type':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/servers/{server_uuid}/isoimages',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.post 'https://api.gridscale.io//objects/servers/{server_uuid}/isoimages',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.post('https://api.gridscale.io//objects/servers/{server_uuid}/isoimages', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/servers/{server_uuid}/isoimages");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.gridscale.io//objects/servers/{server_uuid}/isoimages", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /objects/servers/{server_uuid}/isoimages`

*link isoimage*

POST https://api.gridscale.io/objects/servers/{server_uuid}/isoimages

> Body parameter

```json
{
  "object_uuid": "22f06c53-27a1-482f-94ed-1e464d259adf"
}
```

<h3 id="linkisoimage-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|server_uuid|path|string|true|The UUID of the server, that relates to the Iso image you are requesting.|
|body|body|[LinkIsoimage](#schemalinkisoimage)|true|iso image uuid which is going to be linked|

<h3 id="linkisoimage-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getLInkedIsoimage

<a id="opIdgetLInkedIsoimage"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/servers/{server_uuid}/isoimages/{isoimage_uuid} \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/servers/{server_uuid}/isoimages/{isoimage_uuid} HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/servers/{server_uuid}/isoimages/{isoimage_uuid}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/servers/{server_uuid}/isoimages/{isoimage_uuid}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/servers/{server_uuid}/isoimages/{isoimage_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/servers/{server_uuid}/isoimages/{isoimage_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/servers/{server_uuid}/isoimages/{isoimage_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/servers/{server_uuid}/isoimages/{isoimage_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/servers/{server_uuid}/isoimages/{isoimage_uuid}`

*Find linked isoimage*

GET https://api.gridscale.io/objects/servers/{server_uuid}/isoimages/{object_uuid}

<h3 id="getlinkedisoimage-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|server_uuid|path|string|true|The UUID of the server, that relates to the ISO Image you are requesting.|
|isoimage_uuid|path|string|true|The UUID of the ISO-Image you're requesting.|

> Example responses

> 200 Response

```json
{
  "network_relation": {
    "bootdevice": true,
    "object_name": "string",
    "create_time": "2018-08-28T08:15:36Z",
    "object_uuid": "string",
    "private": "2018-08-28T08:15:36Z",
    "server_uuid": "string"
  }
}
```

<h3 id="getlinkedisoimage-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[LinkedIsoimageGetResponse](#schemalinkedisoimagegetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## updateLinkedIsoimage

<a id="opIdupdateLinkedIsoimage"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH https://api.gridscale.io//objects/servers/{server_uuid}/isoimages/{isoimage_uuid} \
  -H 'Content-Type: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
PATCH https://api.gridscale.io//objects/servers/{server_uuid}/isoimages/{isoimage_uuid} HTTP/1.1
Host: api.gridscale.io
Content-Type: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/servers/{server_uuid}/isoimages/{isoimage_uuid}',
  method: 'patch',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "bootdevice": false,
  "name": "update name"
}';
const headers = {
  'Content-Type':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/servers/{server_uuid}/isoimages/{isoimage_uuid}',
{
  method: 'PATCH',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.patch 'https://api.gridscale.io//objects/servers/{server_uuid}/isoimages/{isoimage_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.patch('https://api.gridscale.io//objects/servers/{server_uuid}/isoimages/{isoimage_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/servers/{server_uuid}/isoimages/{isoimage_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "https://api.gridscale.io//objects/servers/{server_uuid}/isoimages/{isoimage_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /objects/servers/{server_uuid}/isoimages/{isoimage_uuid}`

*linked isoimage patch*

PATCH https://api.gridscale.io/objects/servers/{server_uuid}/isoimages/{object_uuid}

> Body parameter

```json
{
  "bootdevice": false,
  "name": "update name"
}
```

<h3 id="updatelinkedisoimage-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|server_uuid|path|string|true|The UUID of the server, that relates to the ISO Image you are requesting.|
|isoimage_uuid|path|string|true|The UUID of the ISO-Image you're requesting.|
|body|body|[LinkedIsoimageUpdate](#schemalinkedisoimageupdate)|true|Updated user object|

<h3 id="updatelinkedisoimage-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|The request was successful, but the answer deliberately contains no data.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## delete__objects_servers_{server_uuid}_isoimages_{isoimage_uuid}

> Code samples

```shell
# You can also use wget
curl -X DELETE https://api.gridscale.io//objects/servers/{server_uuid}/isoimages/{isoimage_uuid} \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
DELETE https://api.gridscale.io//objects/servers/{server_uuid}/isoimages/{isoimage_uuid} HTTP/1.1
Host: api.gridscale.io

```

```javascript
var headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/servers/{server_uuid}/isoimages/{isoimage_uuid}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/servers/{server_uuid}/isoimages/{isoimage_uuid}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.delete 'https://api.gridscale.io//objects/servers/{server_uuid}/isoimages/{isoimage_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.delete('https://api.gridscale.io//objects/servers/{server_uuid}/isoimages/{isoimage_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/servers/{server_uuid}/isoimages/{isoimage_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://api.gridscale.io//objects/servers/{server_uuid}/isoimages/{isoimage_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /objects/servers/{server_uuid}/isoimages/{isoimage_uuid}`

*GET https://api.gridscale.io/objects/servers/{server_uuid}/isoiamges/{object_uuid}*

<h3 id="delete__objects_servers_{server_uuid}_isoimages_{isoimage_uuid}-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|server_uuid|path|string|true|The UUID of the server, that relates to the ISO-Image you are requesting.|
|isoimage_uuid|path|string|true|The UUID of the ISO-Image you're requesting.|

<h3 id="delete__objects_servers_{server_uuid}_isoimages_{isoimage_uuid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

<h1 id="API-specification-storage">storage</h1>

## getStorages

<a id="opIdgetStorages"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/storages \
  -H 'Accept: */*' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/storages HTTP/1.1
Host: api.gridscale.io

Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/storages',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'*/*',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/storages',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/storages',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/storages', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/storages");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/storages", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/storages`

*get all storages*

GET https://api.gridscale.io/objects/storages

> Example responses

> 200 Response

<h3 id="getstorages-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[StoragesGetResponse](#schemastoragesgetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## createStorage

<a id="opIdcreateStorage"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://api.gridscale.io//objects/storages \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
POST https://api.gridscale.io//objects/storages HTTP/1.1
Host: api.gridscale.io
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/storages',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "name": "string",
  "capacity": 1,
  "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/storages',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.post 'https://api.gridscale.io//objects/storages',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.post('https://api.gridscale.io//objects/storages', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/storages");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.gridscale.io//objects/storages", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /objects/storages`

*Add a new storage*

POST https://api.gridscale.io/objects/storages

> Body parameter

```json
{
  "name": "string",
  "capacity": 1,
  "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950"
}
```

```yaml
name: string
capacity: 1
location_uuid: 45ed677b-3702-4b36-be2a-a2eab9827950

```

<h3 id="createstorage-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[StorageCreate](#schemastoragecreate)|true|none|

> Example responses

> 200 Response

```json
{
  "request_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
  "object_uuid": "690de890-13c0-4e76-8a01-e10ba8786e53"
}
```

<h3 id="createstorage-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[CreateResponse](#schemacreateresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getStorage

<a id="opIdgetStorage"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/storages/{object_uuid} \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/storages/{object_uuid} HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/storages/{object_uuid}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/storages/{object_uuid}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/storages/{object_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/storages/{object_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/storages/{object_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/storages/{object_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/storages/{object_uuid}`

*get a storage*

GET https://api.gridscale.io/objects/storages/{storage_uuid}

<h3 id="getstorage-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|object_uuid|path|string|true|The UUID of an object is always unique, and refers to a specific object.|

> Example responses

> 200 Response

```json
{
  "storage": {
    "parent_uuid": "null",
    "labels": [],
    "snapshots": [],
    "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
    "relations": {
      "servers": [],
      "snapshot_schedules": []
    },
    "name": "test",
    "status": "active",
    "location_country": "de",
    "usage_in_minutes": 370,
    "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
    "change_time": "2018-03-13T12:09:12Z",
    "storage_type": "storage",
    "license_product_no": "null",
    "current_price": 0.001628,
    "create_time": "2018-03-13T12:09:12Z",
    "last_used_template": "null",
    "capacity": 10,
    "location_name": "de/fra",
    "location_iata": "fra"
  }
}
```

<h3 id="getstorage-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[StorageGetResponse](#schemastoragegetresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## updateStorage

<a id="opIdupdateStorage"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH https://api.gridscale.io//objects/storages/{object_uuid} \
  -H 'Content-Type: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
PATCH https://api.gridscale.io//objects/storages/{object_uuid} HTTP/1.1
Host: api.gridscale.io
Content-Type: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/storages/{object_uuid}',
  method: 'patch',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "name": "test",
  "capacity": 10,
  "labels": [
    "backup"
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/storages/{object_uuid}',
{
  method: 'PATCH',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.patch 'https://api.gridscale.io//objects/storages/{object_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.patch('https://api.gridscale.io//objects/storages/{object_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/storages/{object_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "https://api.gridscale.io//objects/storages/{object_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /objects/storages/{object_uuid}`

*Update storage*

PATCH https://api.gridscale.io/objects/storages/{storage_uuid}

> Body parameter

```json
{
  "name": "test",
  "capacity": 10,
  "labels": [
    "backup"
  ]
}
```

<h3 id="updatestorage-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|object_uuid|path|string|true|object that need to be updated|
|body|body|[StorageUpdate](#schemastorageupdate)|true|Updated user object|

<h3 id="updatestorage-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|The request was successful, but the answer deliberately contains no data.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## deleteStorage

<a id="opIddeleteStorage"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE https://api.gridscale.io//objects/storages/{object_uuid} \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
DELETE https://api.gridscale.io//objects/storages/{object_uuid} HTTP/1.1
Host: api.gridscale.io

```

```javascript
var headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/storages/{object_uuid}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/storages/{object_uuid}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.delete 'https://api.gridscale.io//objects/storages/{object_uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.delete('https://api.gridscale.io//objects/storages/{object_uuid}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/storages/{object_uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://api.gridscale.io//objects/storages/{object_uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /objects/storages/{object_uuid}`

*delete storage*

DELETE https://api.gridscale.io/objects/storages/{storage_uuid}

<h3 id="deletestorage-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|object_uuid|path|string|true|object that need to be deleted|

<h3 id="deletestorage-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|The request was successful, but the answer deliberately contains no data.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

## getStorageEvents

<a id="opIdgetStorageEvents"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.gridscale.io//objects/storages/{storage_uuid}/events \
  -H 'Accept: application/json' \
  -H 'X-Auth-Token: API_KEY' \
  -H 'X-Auth-UserId: API_KEY'

```

```http
GET https://api.gridscale.io//objects/storages/{storage_uuid}/events HTTP/1.1
Host: api.gridscale.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

$.ajax({
  url: 'https://api.gridscale.io//objects/storages/{storage_uuid}/events',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'X-Auth-Token':'API_KEY',
  'X-Auth-UserId':'API_KEY'

};

fetch('https://api.gridscale.io//objects/storages/{storage_uuid}/events',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Auth-Token' => 'API_KEY',
  'X-Auth-UserId' => 'API_KEY'
}

result = RestClient.get 'https://api.gridscale.io//objects/storages/{storage_uuid}/events',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Auth-Token': 'API_KEY',
  'X-Auth-UserId': 'API_KEY'
}

r = requests.get('https://api.gridscale.io//objects/storages/{storage_uuid}/events', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.gridscale.io//objects/storages/{storage_uuid}/events");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Auth-Token": []string{"API_KEY"},
        "X-Auth-UserId": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.gridscale.io//objects/storages/{storage_uuid}/events", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /objects/storages/{storage_uuid}/events`

*Find storage event by uuid*

Returns a single storage

<h3 id="getstorageevents-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|storage_uuid|path|string|true|uuid of storage|

> Example responses

> 200 Response

```json
{
  "events": [
    {
      "object_type": "string",
      "request_uuid": "string",
      "object_uuid": "string",
      "activity": "string",
      "request_type": "string",
      "request_status": "string",
      "change": "string",
      "timestamp": "2018-08-28T08:15:36Z",
      "user_uuid": "string"
    }
  ]
}
```

> successful operation

<h3 id="getstorageevents-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[EventResponse](#schemaeventresponse)|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The request has been accepted, but will run at a later date. The success of the request can not be guaranteed.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request message was built incorrectly.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|The request can not be performed without a valid authentication. X-Auth UserId or X-Auth token HTTP header is not set or the userID / token is invalid.|None|
|402|[Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)|Action can not be executed - not provided any or invalid payment methods.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The request was not carried out due to lack of authorization of the user or because an impossible action was requested.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The requested resource was not found. Will also be used if you do a resource exists, but the user does not have permission for it.|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|The request may be made only with other HTTP methods (eg GET rather than POST).|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|The request was made under false assumptions. For example, a user can not be created twice with the same email.|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The contents of the request have been submitted with an invalid media type. All POST or PATCH requests must have 'Content-Type : application / json' as a header, and send a JSON object as a payload.|None|
|424|[Failed Dependency](https://tools.ietf.org/html/rfc2518#section-10.5)|The request could not be performed because the object is in the wrong status.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth & ApiUserID
</aside>

# Schemas

<h2 id="tocSrelation">relation</h2>

<a id="schemarelation"></a>

```json
{
  "object1": [
    {}
  ]
}

```

*Objects related to this object*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|object1|[object]|false|none|none|

<h2 id="tocSservercreate">ServerCreate</h2>

<a id="schemaservercreate"></a>

```json
{
  "name": "string",
  "cores": 1,
  "memory": 2,
  "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|[name](#schemaname)|true|none|none|
|cores|integer|true|none|The number of server cores.|
|memory|integer|true|none|The amount of server memory in GB.|
|location_uuid|string|true|none|The UUID of the datacenter you would like to hold your server. A list of available data centres can be found with a GET request on the /locations endpoint.|
|labels|[labels](#schemalabels)|false|none|none|
|status|[status](#schemastatus)|false|none|none|
|availability_zone|string|false|none|Defines which Availability-Zone the Server is placed.|
|auto_recovery|string|false|none|If the server should be auto-started in case of a failure (default=true).|

<h2 id="tocSserverupdate">ServerUpdate</h2>

<a id="schemaserverupdate"></a>

```json
{
  "name": "Updated Name"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|[name](#schemaname)|false|none|none|
|cores|integer|false|none|The number of server cores.|
|memory|integer|false|none|The amount of server memory in GB.|
|labels|[labels](#schemalabels)|false|none|none|
|availability_zone|string|false|none|Defines which Availability-Zone the Server is placed.|
|auto_recovery|string|false|none|If the server should be auto-started in case of a failure (default=true).|

<h2 id="tocSserver">Server</h2>

<a id="schemaserver"></a>

```json
{
  "cores": 1,
  "relations": {
    "storages": [
      {
        "capacity": 11,
        "server_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
        "last_used_template": "ec4ef18f-84df-42bb-b7c4-c2957635ee53",
        "controller": 0,
        "license_product_no": null,
        "bus": 0,
        "target": 0,
        "create_time": "2018-03-14T13:33:24Z",
        "lun": 0,
        "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
        "bootdevice": true,
        "object_name": "Ubunto 16.04 Storage",
        "storage_type": "storage"
      }
    ],
    "public_ips": [
      {
        "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
        "prefix": "1x:12:xx:12:12:12/32",
        "ip": "123.123.12.1",
        "server_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
        "create_time": "2018-03-14T13:33:14Z",
        "family": 4
      },
      {
        "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
        "prefix": "123.123.12.1/128",
        "ip": "123.123.12.1",
        "server_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
        "create_time": "2018-03-14T13:33:16Z",
        "family": 6
      }
    ],
    "networks": [
      {
        "network_type": "network",
        "vlan": null,
        "create_time": "2018-03-14T13:33:13Z",
        "ordering": 0,
        "bootdevice": false,
        "mac": "16:f7:22:9e:56:01",
        "vxlan": null,
        "mcast": null,
        "server_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
        "l3security": [],
        "firewall_template_uuid": null,
        "partner_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
        "object_name": "Public Network test",
        "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
        "network_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
        "public_net": true,
        "firewall": null,
        "l2security": true
      }
    ],
    "isoimages": []
  },
  "legacy": false,
  "memory": 2,
  "console_token": "$console_token",
  "usage_in_minutes_memory": 47331,
  "auto_recovery": true,
  "create_time": "2018-03-14T13:33:13Z",
  "current_price": 9.491665,
  "location_country": "de",
  "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
  "usage_in_minutes_cores": 0,
  "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
  "change_time": "2018-03-19T11:40:55Z",
  "availability_zone": null,
  "location_iata": "fra",
  "labels": [],
  "hardware_profile": "default",
  "location_name": "de/fra",
  "power": true,
  "name": "Ubunto 16.04",
  "status": "active"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|cores|integer|false|none|Number of server cores|
|relations|[relation](#schemarelation)|false|none|none|
|legacy|boolean|false|none|Legacy-Hardware emulation instead of virtio hardware. If enabled, hotplugging cores, memory, storage, network, etc. will not work, but the server will most likely run every x86 compatible operating system. This mode comes with a performance penalty, as emulated hardware does not benefit from the virtio driver infrastructure|
|memory|integer|false|none|Indicates the amount of memory in GB.|
|console_token|string|false|none|The token used by the panel to open the websocket VNC connection to the server console|
|usage_in_minutes_memory|integer|false|none|Total minutes of memory used|
|auto_recovery|boolean|false|none|If the server should be auto-started in case of a failure (default=true).|
|create_time|[create_time](#schemacreate_time)|false|none|none|
|current_price|[current_price](#schemacurrent_price)|false|none|none|
|location_country|[location_country](#schemalocation_country)|false|none|none|
|location_uuid|[location_uuid](#schemalocation_uuid)|false|none|none|
|usage_in_minutes_cores|integer|false|none|Total minutes of cores used|
|object_uuid|[object_uuid](#schemaobject_uuid)|false|none|none|
|change_time|[change_time](#schemachange_time)|false|none|none|
|availability_zone|string|false|none|Which Availability-Zone the Server is placed|
|location_iata|[location_iata](#schemalocation_iata)|false|none|none|
|labels|[labels](#schemalabels)|false|none|none|
|hardware_profile|string|false|none|none|
|location_name|[location_name](#schemalocation_name)|false|none|none|
|power|boolean|false|none|The power status of the server|
|name|[name](#schemaname)|false|none|none|
|status|[status](#schemastatus)|false|none|none|

<h2 id="tocSserverbriefindex">ServerBriefIndex</h2>

<a id="schemaserverbriefindex"></a>

```json
{
  "x123xx1x-123x-1x12-123x-123xxx123x1x": {
    "auto_recovery": true,
    "availability_zone": null,
    "current_price": 9.491665,
    "power": true,
    "status": "active",
    "cores": 1,
    "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
    "name": "Ubunto 16.04",
    "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
    "usage_in_minutes_cores": 17476,
    "labels": [],
    "hardware_profile": "default",
    "location_iata": "fra",
    "location_name": "de/fra",
    "legacy": false,
    "memory": 2,
    "create_time": "2018-03-14T13:33:13Z",
    "relations": {
      "public_ips": [
        {
          "prefix": "1x:12:xx:12:12:12/32",
          "create_time": "2018-03-14T13:33:14Z",
          "family": 4,
          "ip": "123.123.12.1",
          "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x"
        },
        {
          "prefix": "123.123.12.1/128",
          "create_time": "2018-03-14T13:33:16Z",
          "family": 6,
          "ip": "123.123.12.1",
          "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x"
        }
      ],
      "isoimages": [],
      "networks": [
        {
          "bootdevice": false,
          "firewall_template_uuid": null,
          "vlan": null,
          "mcast": null,
          "vxlan": null,
          "public_net": true,
          "l2security": true,
          "object_name": "Public Network test",
          "network_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
          "create_time": "2018-03-14T13:33:13Z",
          "firewall": null,
          "network_type": "network",
          "mac": "16:f7:22:9e:56:01",
          "partner_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
          "l3security": [],
          "ordering": 0,
          "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x"
        }
      ],
      "storages": [
        {
          "bootdevice": true,
          "target": 0,
          "lun": 0,
          "capacity": 11,
          "object_name": "Ubunto 16.04 Storage",
          "controller": 0,
          "create_time": "2018-03-14T13:33:24Z",
          "storage_type": "storage",
          "bus": 0,
          "last_used_template": "ec4ef18f-84df-42bb-b7c4-c2957635ee53",
          "license_product_no": null,
          "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x"
        }
      ]
    },
    "usage_in_minutes_memory": 47331,
    "change_time": "2018-03-19T11:40:55Z",
    "console_token": "$console_token",
    "location_country": "de"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|**additionalProperties**|[Server](#schemaserver)|false|none|none|

<h2 id="tocSservergetresponse">ServerGetResponse</h2>

<a id="schemaservergetresponse"></a>

```json
{
  "server": {
    "cores": 1,
    "relations": {
      "storages": [
        {
          "capacity": 11,
          "server_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
          "last_used_template": "ec4ef18f-84df-42bb-b7c4-c2957635ee53",
          "controller": 0,
          "license_product_no": null,
          "bus": 0,
          "target": 0,
          "create_time": "2018-03-14T13:33:24Z",
          "lun": 0,
          "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
          "bootdevice": true,
          "object_name": "Ubunto 16.04 Storage",
          "storage_type": "storage"
        }
      ],
      "public_ips": [
        {
          "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
          "prefix": "1x:12:xx:12:12:12/32",
          "ip": "123.123.12.1",
          "server_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
          "create_time": "2018-03-14T13:33:14Z",
          "family": 4
        },
        {
          "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
          "prefix": "123.123.12.1/128",
          "ip": "123.123.12.1",
          "server_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
          "create_time": "2018-03-14T13:33:16Z",
          "family": 6
        }
      ],
      "networks": [
        {
          "network_type": "network",
          "vlan": null,
          "create_time": "2018-03-14T13:33:13Z",
          "ordering": 0,
          "bootdevice": false,
          "mac": "16:f7:22:9e:56:01",
          "vxlan": null,
          "mcast": null,
          "server_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
          "l3security": [],
          "firewall_template_uuid": null,
          "partner_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
          "object_name": "Public Network test",
          "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
          "network_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
          "public_net": true,
          "firewall": null,
          "l2security": true
        }
      ],
      "isoimages": []
    },
    "legacy": false,
    "memory": 2,
    "console_token": "$console_token",
    "usage_in_minutes_memory": 47331,
    "auto_recovery": true,
    "create_time": "2018-03-14T13:33:13Z",
    "current_price": 9.491665,
    "location_country": "de",
    "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
    "usage_in_minutes_cores": 0,
    "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
    "change_time": "2018-03-19T11:40:55Z",
    "availability_zone": null,
    "location_iata": "fra",
    "labels": [],
    "hardware_profile": "default",
    "location_name": "de/fra",
    "power": true,
    "name": "Ubunto 16.04",
    "status": "active"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|server|[Server](#schemaserver)|false|none|none|

<h2 id="tocSserversgetresponse">ServersGetResponse</h2>

<a id="schemaserversgetresponse"></a>

```json
{
  "servers": {
    "x123xx1x-123x-1x12-123x-123xxx123x1x": {
      "auto_recovery": true,
      "availability_zone": null,
      "current_price": 9.491665,
      "power": true,
      "status": "active",
      "cores": 1,
      "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
      "name": "Ubunto 16.04",
      "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
      "usage_in_minutes_cores": 17476,
      "labels": [],
      "hardware_profile": "default",
      "location_iata": "fra",
      "location_name": "de/fra",
      "legacy": false,
      "memory": 2,
      "create_time": "2018-03-14T13:33:13Z",
      "relations": {
        "public_ips": [
          {
            "prefix": "1x:12:xx:12:12:12/32",
            "create_time": "2018-03-14T13:33:14Z",
            "family": 4,
            "ip": "123.123.12.1",
            "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x"
          },
          {
            "prefix": "123.123.12.1/128",
            "create_time": "2018-03-14T13:33:16Z",
            "family": 6,
            "ip": "123.123.12.1",
            "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x"
          }
        ],
        "isoimages": [],
        "networks": [
          {
            "bootdevice": false,
            "firewall_template_uuid": null,
            "vlan": null,
            "mcast": null,
            "vxlan": null,
            "public_net": true,
            "l2security": true,
            "object_name": "Public Network test",
            "network_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
            "create_time": "2018-03-14T13:33:13Z",
            "firewall": null,
            "network_type": "network",
            "mac": "16:f7:22:9e:56:01",
            "partner_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
            "l3security": [],
            "ordering": 0,
            "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x"
          }
        ],
        "storages": [
          {
            "bootdevice": true,
            "target": 0,
            "lun": 0,
            "capacity": 11,
            "object_name": "Ubunto 16.04 Storage",
            "controller": 0,
            "create_time": "2018-03-14T13:33:24Z",
            "storage_type": "storage",
            "bus": 0,
            "last_used_template": "ec4ef18f-84df-42bb-b7c4-c2957635ee53",
            "license_product_no": null,
            "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x"
          }
        ]
      },
      "usage_in_minutes_memory": 47331,
      "change_time": "2018-03-19T11:40:55Z",
      "console_token": "$console_token",
      "location_country": "de"
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|servers|[ServerBriefIndex](#schemaserverbriefindex)|false|none|none|

<h2 id="tocSserverpowerstatus">ServerPowerStatus</h2>

<a id="schemaserverpowerstatus"></a>

```json
{
  "power": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|power|boolean|false|none|none|

<h2 id="tocSstoragecreate">StorageCreate</h2>

<a id="schemastoragecreate"></a>

```json
{
  "name": "string",
  "capacity": 1,
  "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|[name](#schemaname)|true|none|none|
|capacity|integer|true|none|required (integer - minimum: 1 - maximum: 4096)|
|location_uuid|[location_uuid](#schemalocation_uuid)|true|none|none|
|template|object|false|none|An object holding important values such as hostnames, passwords, and SSH keys.|
|hostname|string|false|none|Hostname to set for the installed storage. The running server will use this as its hostname. Valid only for public Linux and Windows templates.|
|template_uuid|string(uuid)|false|none|The UUID of a template (public or private).|
|password|string|false|none|The root (Linux) or Administrator (Windows) password to set for the installed storage. Valid only for public templates. The password has to be either plaintext or a crypt string (modular crypt format - MCF)..|
|password_type|string|false|none|(one of plain, crypt)|
|shkeys|string|false|none|(array of any - minItems: 0)|
|labels|[labels](#schemalabels)|false|none|none|
|storage_type|string|false|none|(one of storage, storage_high, storage_insane)|

#### Enumerated Values

|Property|Value|
|---|---|
|storage_type|storage|
|storage_type|storage_high|
|storage_type|storage_insane|

<h2 id="tocSstorageupdate">StorageUpdate</h2>

<a id="schemastorageupdate"></a>

```json
{
  "name": "test",
  "capacity": 10,
  "labels": [
    "backup"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|[name](#schemaname)|false|none|none|
|capacity|string|false|none|none|
|labels|[labels](#schemalabels)|false|none|none|

<h2 id="tocSstorage">Storage</h2>

<a id="schemastorage"></a>

```json
{
  "parent_uuid": "null",
  "labels": [],
  "snapshots": [],
  "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
  "relations": {
    "servers": [],
    "snapshot_schedules": []
  },
  "name": "test",
  "status": "active",
  "location_country": "de",
  "usage_in_minutes": 370,
  "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
  "change_time": "2018-03-13T12:09:12Z",
  "storage_type": "storage",
  "license_product_no": "null",
  "current_price": 0.001628,
  "create_time": "2018-03-13T12:09:12Z",
  "last_used_template": "null",
  "capacity": 10,
  "location_name": "de/fra",
  "location_iata": "fra"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|parent_uuid|string(uuid)|false|none|none|
|labels|[labels](#schemalabels)|false|none|none|
|snapshots|[string]|false|none|none|
|object_uuid|[object_uuid](#schemaobject_uuid)|false|none|none|
|relations|[relation](#schemarelation)|false|none|none|
|name|[name](#schemaname)|false|none|none|
|status|[status](#schemastatus)|false|none|none|
|location_country|[location_country](#schemalocation_country)|false|none|none|
|usage_in_minutes|[usage_in_minutes](#schemausage_in_minutes)|false|none|none|
|location_uuid|[location_uuid](#schemalocation_uuid)|false|none|none|
|change_time|[change_time](#schemachange_time)|false|none|none|
|storage_type|string|false|none|(one of storage, storage_high, storage_insane)|
|license_product_no|string|false|none|If a template has been used that requires a license key (e.g. Windows Servers) this shows the product_no of the license (see the /prices endpoint for more details).|
|current_price|[current_price](#schemacurrent_price)|false|none|none|
|create_time|[create_time](#schemacreate_time)|false|none|none|
|last_used_template|string|false|none|Indicates the UUID of the last used template on this storage|
|capacity|integer|false|none|The capacity of a storage/ISO-Image/template/snapshot in GB.|
|location_name|[location_name](#schemalocation_name)|false|none|none|
|location_iata|[location_iata](#schemalocation_iata)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|storage_type|storage|
|storage_type|storage_high|
|storage_type|storage_insane|

<h2 id="tocSstoragebriefindex">StorageBriefIndex</h2>

<a id="schemastoragebriefindex"></a>

```json
{
  "x123xx1x-123x-1x12-123x-123xxx123x1x": {
    "change_time": "2018-03-13T09:24:23Z",
    "location_iata": "fra",
    "status": "active",
    "license_product_no": null,
    "location_country": "de",
    "usage_in_minutes": 770,
    "last_used_template": null,
    "current_price": 0.003388,
    "capacity": 10,
    "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
    "storage_type": "storage",
    "parent_uuid": null,
    "name": "test Storage",
    "location_name": "de/fra",
    "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
    "snapshots": [],
    "relations": {
      "servers": [
        {
          "bootdevice": true,
          "target": 0,
          "controller": 0,
          "bus": 0,
          "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
          "lun": 0,
          "create_time": "2018-03-13T09:24:25Z",
          "object_name": "tes"
        }
      ],
      "snapshot_schedules": []
    },
    "labels": [],
    "create_time": "2018-03-13T09:24:23Z"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|**additionalProperties**|[Storage](#schemastorage)|false|none|none|

<h2 id="tocSstoragegetresponse">StorageGetResponse</h2>

<a id="schemastoragegetresponse"></a>

```json
{
  "storage": {
    "parent_uuid": "null",
    "labels": [],
    "snapshots": [],
    "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
    "relations": {
      "servers": [],
      "snapshot_schedules": []
    },
    "name": "test",
    "status": "active",
    "location_country": "de",
    "usage_in_minutes": 370,
    "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
    "change_time": "2018-03-13T12:09:12Z",
    "storage_type": "storage",
    "license_product_no": "null",
    "current_price": 0.001628,
    "create_time": "2018-03-13T12:09:12Z",
    "last_used_template": "null",
    "capacity": 10,
    "location_name": "de/fra",
    "location_iata": "fra"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|storage|[Storage](#schemastorage)|false|none|none|

<h2 id="tocSstoragesgetresponse">StoragesGetResponse</h2>

<a id="schemastoragesgetresponse"></a>

```json
{
  "storages": {
    "x123xx1x-123x-1x12-123x-123xxx123x1x": {
      "change_time": "2018-03-13T09:24:23Z",
      "location_iata": "fra",
      "status": "active",
      "license_product_no": null,
      "location_country": "de",
      "usage_in_minutes": 770,
      "last_used_template": null,
      "current_price": 0.003388,
      "capacity": 10,
      "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
      "storage_type": "storage",
      "parent_uuid": null,
      "name": "test Storage",
      "location_name": "de/fra",
      "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
      "snapshots": [],
      "relations": {
        "servers": [
          {
            "bootdevice": true,
            "target": 0,
            "controller": 0,
            "bus": 0,
            "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
            "lun": 0,
            "create_time": "2018-03-13T09:24:25Z",
            "object_name": "tes"
          }
        ],
        "snapshot_schedules": []
      },
      "labels": [],
      "create_time": "2018-03-13T09:24:23Z"
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|storages|[StorageBriefIndex](#schemastoragebriefindex)|false|none|none|

<h2 id="tocScreateresponse">CreateResponse</h2>

<a id="schemacreateresponse"></a>

```json
{
  "request_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
  "object_uuid": "690de890-13c0-4e76-8a01-e10ba8786e53"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|request_uuid|string(uuid)|false|none|request user ID.|
|object_uuid|string(uuid)|false|none|The user name.|

<h2 id="tocSnetworkcreate">NetworkCreate</h2>

<a id="schemanetworkcreate"></a>

```json
{
  "name": "string",
  "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
  "l2security": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|[name](#schemaname)|true|none|none|
|location_uuid|[location_uuid](#schemalocation_uuid)|true|none|none|
|l2security|boolean|false|none|Defines information about MAC spoofing protection (filters layer2 and ARP traffic based on MAC source). It can only be (de-)activated on a private network - the public network always has l2security enabled. It will be true if the network is public, and false if the network is private.|
|labels|[string]|false|none|List of labels.|

<h2 id="tocSnetworkupdate">NetworkUpdate</h2>

<a id="schemanetworkupdate"></a>

```json
{
  "name": "new_name",
  "l2security": false
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|[name](#schemaname)|false|none|none|
|l2security|boolean|false|none|Defines information about MAC spoofing protection (filters layer2 and ARP traffic based on MAC source). It can only be (de-)activated on a private network - the public network always has l2security enabled. It will be true if the network is public, and false if the network is private.|

<h2 id="tocSnetwork">Network</h2>

<a id="schemanetwork"></a>

```json
{
  "location_country": "de",
  "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
  "public_net": false,
  "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
  "network_type": "network",
  "name": "test",
  "delete_block": false,
  "status": "active",
  "create_time": "2018-03-14T08:04:16Z",
  "l2security": false,
  "relations": {
    "vlans": [],
    "servers": []
  },
  "labels": [],
  "change_time": "2018-03-14T08:04:16Z",
  "location_iata": "fra",
  "location_name": "de/fra"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|location_country|[location_country](#schemalocation_country)|false|none|none|
|location_uuid|[location_uuid](#schemalocation_uuid)|false|none|none|
|public_net|boolean|false|none|True if the network is public. If private it will be false. Each private network is a secure and fully transparent 2-Layer network between servers. There is no limit on how many servers can be connected to the same private network.|
|object_uuid|[object_uuid](#schemaobject_uuid)|false|none|none|
|network_type|string|false|none|(one of network, network_high, network_insane)|
|name|[name](#schemaname)|false|none|none|
|delete_block|boolean|false|none|Defines if the object is administratively blocked. If true, it can not be deleted by the user.|
|status|[status](#schemastatus)|false|none|none|
|create_time|[create_time](#schemacreate_time)|false|none|none|
|l2security|boolean|false|none|Defines information about MAC spoofing protection (filters layer2 and ARP traffic based on MAC source). It can only be (de-)activated on a private network - the public network always has l2security enabled. It will be true if the network is public, and false if the network is private.|
|relations|[relation](#schemarelation)|false|none|none|
|labels|[labels](#schemalabels)|false|none|none|
|change_time|[change_time](#schemachange_time)|false|none|none|
|location_iata|[location_iata](#schemalocation_iata)|false|none|none|
|location_name|[location_name](#schemalocation_name)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|network_type|network|
|network_type|network_high|
|network_type|network_insane|

<h2 id="tocSnetworkbriefindex">NetworkBriefIndex</h2>

<a id="schemanetworkbriefindex"></a>

```json
{
  "x123xx1x-123x-1x12-123x-123xxx123x1x": {
    "location_country": "de",
    "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
    "public_net": false,
    "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
    "network_type": "network",
    "name": "test",
    "delete_block": false,
    "status": "active",
    "create_time": "2018-03-14T08:04:16Z",
    "l2security": false,
    "relations": {
      "vlans": [],
      "servers": []
    },
    "labels": [],
    "change_time": "2018-03-14T08:04:16Z",
    "location_iata": "fra",
    "location_name": "de/fra"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|**additionalProperties**|[Storage](#schemastorage)|false|none|none|

<h2 id="tocSnetworkgetresponse">NetworkGetResponse</h2>

<a id="schemanetworkgetresponse"></a>

```json
{
  "network": {
    "location_country": "de",
    "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
    "public_net": false,
    "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
    "network_type": "network",
    "name": "test",
    "delete_block": false,
    "status": "active",
    "create_time": "2018-03-14T08:04:16Z",
    "l2security": false,
    "relations": {
      "vlans": [],
      "servers": []
    },
    "labels": [],
    "change_time": "2018-03-14T08:04:16Z",
    "location_iata": "fra",
    "location_name": "de/fra"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|network|[Network](#schemanetwork)|false|none|none|

<h2 id="tocSnetworksgetresponse">NetworksGetResponse</h2>

<a id="schemanetworksgetresponse"></a>

```json
{
  "networks": {
    "x123xx1x-123x-1x12-123x-123xxx123x1x": {
      "location_country": "de",
      "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
      "public_net": false,
      "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
      "network_type": "network",
      "name": "test",
      "delete_block": false,
      "status": "active",
      "create_time": "2018-03-14T08:04:16Z",
      "l2security": false,
      "relations": {
        "vlans": [],
        "servers": []
      },
      "labels": [],
      "change_time": "2018-03-14T08:04:16Z",
      "location_iata": "fra",
      "location_name": "de/fra"
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|networks|[NetworkBriefIndex](#schemanetworkbriefindex)|false|none|none|

<h2 id="tocSeventresponse">EventResponse</h2>

<a id="schemaeventresponse"></a>

```json
{
  "events": [
    {
      "object_type": "string",
      "request_uuid": "string",
      "object_uuid": "string",
      "activity": "string",
      "request_type": "string",
      "request_status": "string",
      "change": "string",
      "timestamp": "2018-08-28T08:15:36Z",
      "user_uuid": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|events|[object]|false|none|none|
|» object_type|string|false|none|Type of object (server, storage, IP) etc.|
|» request_uuid|string(uuid)|false|none|The UUID of the event.|
|» object_uuid|string(uuid)|false|none|The UUID of the objects the event was executed on.|
|» activity|string|false|none|The type of change.|
|» request_type|string|false|none|The type of request.|
|» request_status|string|false|none|True or false, whether the request was successful or not.|
|» change|string|false|none|A detailed description of the change.|
|» timestamp|string(date-time)|false|none|Time the event was triggered.|
|» user_uuid|string(uuid)|false|none|The UUID of the user that triggered the event.|

<h2 id="tocSipcreate">IpCreate</h2>

<a id="schemaipcreate"></a>

```json
{
  "family": 4,
  "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
  "failover": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|family|integer|true|none|Defines the IP Address family (v4 or v6).|
|location_uuid|[location_uuid](#schemalocation_uuid)|true|none|none|
|failover|boolean|false|none|Sets failover mode for this IP. If true, then this IP is no longer available for DHCP and can no longer be related to any server.|
|reverse_dns|string|false|none|Defines the reverse DNS entry for the IP Address (PTR Resource Record).|
|labels|[labels](#schemalabels)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|family|4|
|family|6|

<h2 id="tocSipcreateresponse">IpCreateResponse</h2>

<a id="schemaipcreateresponse"></a>

```json
{
  "request_uuid": "8e9a4818-d145-4aa3-918a-60cc32b37e96",
  "ip": "123.123.12.1",
  "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
  "prefix": "123.123.12.1/32"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|request_uuid|string|false|none|request user ID.|
|ip|string|false|none|ip_address defines the IP Address (v4 or v6).|
|object_uuid|[object_uuid](#schemaobject_uuid)|false|none|none|
|prefix|string|false|none|ip_prefix defines the IP prefix.|

<h2 id="tocSipupdate">IpUpdate</h2>

<a id="schemaipupdate"></a>

```json
{
  "name": "update swagger ip",
  "l2security": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|failover|boolean|false|none|Sets failover mode for this IP. If true, then this IP is no longer available for DHCP and can no longer be related to any server.|
|reverse_dns|string|false|none|Defines the reverse DNS entry for the IP Address (PTR Resource Record).|
|labels|[labels](#schemalabels)|false|none|none|

<h2 id="tocSip">Ip</h2>

<a id="schemaip"></a>

```json
{
  "create_time": "2018-02-01T13:48:13Z",
  "status": "active",
  "relations": {
    "loadbalancers": [],
    "servers": [
      {
        "create_time": "2018-02-20T11:51:18Z",
        "server_name": "server with a new name2",
        "server_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x"
      }
    ]
  },
  "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
  "location_country": "de",
  "prefix": "123.123.12.1/128",
  "delete_block": false,
  "failover": false,
  "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
  "location_name": "de/fra",
  "labels": [],
  "change_time": "2018-02-01T13:48:13Z",
  "ip": "123.123.12.1",
  "family": 6,
  "location_iata": "fra",
  "reverse_dns": "static-123-123-123-123.ipv6.exampleserver.com",
  "current_price": 0,
  "usage_in_minutes": 0,
  "name": "Default IP"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|create_time|[create_time](#schemacreate_time)|false|none|none|
|status|[status](#schemastatus)|false|none|none|
|relations|[relation](#schemarelation)|false|none|none|
|object_uuid|[object_uuid](#schemaobject_uuid)|false|none|none|
|location_country|[location_country](#schemalocation_country)|false|none|none|
|prefix|string|false|none|ip_prefix defines the IP prefix.|
|delete_block|boolean|false|none|Defines if the object is administratively blocked. If true, it can not be deleted by the user.|
|failover|boolean|false|none|Sets failover mode for this IP. If true, then this IP is no longer available for DHCP and can no longer be related to any server.|
|location_uuid|[location_uuid](#schemalocation_uuid)|false|none|none|
|location_name|[location_name](#schemalocation_name)|false|none|none|
|labels|[labels](#schemalabels)|false|none|none|
|change_time|[change_time](#schemachange_time)|false|none|none|
|ip|string|false|none|Defines the IP Address (v4 or v6).|
|family|string|false|none|The IP Address family (v4 or v6).|
|location_iata|[location_iata](#schemalocation_iata)|false|none|none|
|reverse_dns|string|false|none|Defines the reverse DNS entry for the IP Address (PTR Resource Record).|
|current_price|[current_price](#schemacurrent_price)|false|none|none|
|usage_in_minutes|[usage_in_minutes](#schemausage_in_minutes)|false|none|none|
|name|[name](#schemaname)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|family|4|
|family|6|

<h2 id="tocSipbrief">IpBrief</h2>

<a id="schemaipbrief"></a>

```json
{
  "create_time": "2018-08-28T08:15:36Z",
  "status": "string",
  "relations": {
    "object1": [
      {}
    ]
  },
  "object_uuid": "string",
  "location_country": "string",
  "prefix": "string",
  "delete_block": true,
  "failover": true,
  "location_uuid": "string",
  "location_name": "string",
  "labels": [
    "string"
  ],
  "change_time": "2018-08-28T08:15:36Z",
  "ip": "string",
  "family": 4,
  "location_iata": "string",
  "reverse_dns": "string",
  "current_price": 0,
  "usage_in_minutes": 0,
  "name": "string",
  "partner_uuid": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|create_time|[create_time](#schemacreate_time)|false|none|none|
|status|[status](#schemastatus)|false|none|none|
|relations|[relation](#schemarelation)|false|none|none|
|object_uuid|[object_uuid](#schemaobject_uuid)|false|none|none|
|location_country|[location_country](#schemalocation_country)|false|none|none|
|prefix|string|false|none|ip_prefix defines the IP prefix.|
|delete_block|boolean|false|none|Defines if the object is administratively blocked. If true, it can not be deleted by the user.|
|failover|boolean|false|none|Sets failover mode for this IP. If true, then this IP is no longer available for DHCP and can no longer be related to any server.|
|location_uuid|[location_uuid](#schemalocation_uuid)|false|none|none|
|location_name|[location_name](#schemalocation_name)|false|none|none|
|labels|[labels](#schemalabels)|false|none|none|
|change_time|[change_time](#schemachange_time)|false|none|none|
|ip|string|false|none|Defines the IP Address (v4 or v6).|
|family|string|false|none|The IP Address family (v4 or v6).|
|location_iata|[location_iata](#schemalocation_iata)|false|none|none|
|reverse_dns|string|false|none|Defines the reverse DNS entry for the IP Address (PTR Resource Record).|
|current_price|[current_price](#schemacurrent_price)|false|none|none|
|usage_in_minutes|[usage_in_minutes](#schemausage_in_minutes)|false|none|none|
|name|[name](#schemaname)|false|none|none|
|partner_uuid|string(uuid)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|family|4|
|family|6|

<h2 id="tocSipbriefindex">IpBriefIndex</h2>

<a id="schemaipbriefindex"></a>

```json
{
  "x123xx1x-123x-1x12-123x-123xxx123x1x": {
    "create_time": "2018-02-01T13:48:13Z",
    "status": "active",
    "relations": {
      "loadbalancers": [],
      "servers": [
        {
          "create_time": "2018-02-20T11:51:18Z",
          "server_name": "server with a new name2",
          "server_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x"
        }
      ]
    },
    "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
    "partner_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
    "location_country": "de",
    "prefix": "123.123.12.1/128",
    "delete_block": false,
    "failover": false,
    "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
    "location_name": "de/fra",
    "labels": [],
    "change_time": "2018-02-01T13:48:13Z",
    "ip": "123.123.12.1",
    "family": 6,
    "location_iata": "fra",
    "reverse_dns": "static-123-123-123-123.ipv6.exampleserver.com",
    "current_price": 0,
    "usage_in_minutes": 0,
    "name": "Default IP"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|**additionalProperties**|[IpBrief](#schemaipbrief)|false|none|none|

<h2 id="tocSipgetresponse">IpGetResponse</h2>

<a id="schemaipgetresponse"></a>

```json
{
  "ip": {
    "create_time": "2018-02-01T13:48:13Z",
    "status": "active",
    "relations": {
      "loadbalancers": [],
      "servers": [
        {
          "create_time": "2018-02-20T11:51:18Z",
          "server_name": "server with a new name2",
          "server_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x"
        }
      ]
    },
    "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
    "location_country": "de",
    "prefix": "123.123.12.1/128",
    "delete_block": false,
    "failover": false,
    "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
    "location_name": "de/fra",
    "labels": [],
    "change_time": "2018-02-01T13:48:13Z",
    "ip": "123.123.12.1",
    "family": 6,
    "location_iata": "fra",
    "reverse_dns": "static-123-123-123-123.ipv6.exampleserver.com",
    "current_price": 0,
    "usage_in_minutes": 0,
    "name": "Default IP"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|ip|[Ip](#schemaip)|false|none|none|

<h2 id="tocSipsgetresponse">IpsGetResponse</h2>

<a id="schemaipsgetresponse"></a>

```json
{
  "ips": {
    "x123xx1x-123x-1x12-123x-123xxx123x1x": {
      "create_time": "2018-02-01T13:48:13Z",
      "status": "active",
      "relations": {
        "loadbalancers": [],
        "servers": [
          {
            "create_time": "2018-02-20T11:51:18Z",
            "server_name": "server with a new name2",
            "server_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x"
          }
        ]
      },
      "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
      "partner_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
      "location_country": "de",
      "prefix": "123.123.12.1/128",
      "delete_block": false,
      "failover": false,
      "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
      "location_name": "de/fra",
      "labels": [],
      "change_time": "2018-02-01T13:48:13Z",
      "ip": "123.123.12.1",
      "family": 6,
      "location_iata": "fra",
      "reverse_dns": "static-123-123-123-123.ipv6.exampleserver.com",
      "current_price": 0,
      "usage_in_minutes": 0,
      "name": "Default IP"
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|ips|[IpBriefIndex](#schemaipbriefindex)|false|none|none|

<h2 id="tocSfirewallcreate">FirewallCreate</h2>

<a id="schemafirewallcreate"></a>

```json
{
  "name": "test",
  "labels": [
    "webmail"
  ],
  "rules": {
    "rules-v4-in": [
      {
        "port": 20,
        "protocol": "tcp",
        "order": 0,
        "action": "accept"
      }
    ]
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|none|
|labels|string|false|none|none|
|rules|object|false|none|none|

<h2 id="tocSfirewallupdate">FirewallUpdate</h2>

<a id="schemafirewallupdate"></a>

```json
{
  "name": "Updated Name",
  "labels": [
    "webmail"
  ],
  "rules": {
    "rules-v4-in": [
      {
        "port": 20,
        "protocol": "tcp",
        "order": 0,
        "action": "accept"
      }
    ],
    "rules-v6-in": [
      {
        "port": 22,
        "protocol": "tcp",
        "order": 1,
        "action": "drop"
      }
    ]
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|[name](#schemaname)|false|none|none|
|labels|[labels](#schemalabels)|false|none|none|
|rules|object|false|none|none|
|private|string|false|none|If this is a private or public Firewall-Template|

<h2 id="tocSfirewall">Firewall</h2>

<a id="schemafirewall"></a>

```json
{
  "status": "active",
  "labels": [],
  "object_uuid": "9a3fdd6e-fc2c-43a3-a8ac-6ec06898f9ce",
  "change_time": "2017-10-18T10:05:15Z",
  "rules": {
    "rules-v6-in": [
      {
        "order": 0,
        "protocol": "tcp",
        "action": "accept",
        "dst_port": "22"
      }
    ],
    "rules-v4-in": [
      {
        "order": 0,
        "protocol": "tcp",
        "action": "accept",
        "dst_port": "22"
      }
    ],
    "rules-v4-out": [],
    "rules-v6-out": []
  },
  "create_time": "2017-10-17T12:38:42Z",
  "private": false,
  "relations": {
    "networks": []
  },
  "name": "Webserver + SSH"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|status|[status](#schemastatus)|false|none|none|
|labels|[labels](#schemalabels)|false|none|none|
|object_uuid|[object_uuid](#schemaobject_uuid)|false|none|none|
|change_time|[change_time](#schemachange_time)|false|none|none|
|rules|object|false|none|none|
|create_time|[create_time](#schemacreate_time)|false|none|none|
|private|boolean|false|none|If this is a private or public Firewall-Template|
|relations|[relation](#schemarelation)|false|none|none|
|description|string|false|none|Description of the ISO-Image release|
|location_name|[location_name](#schemalocation_name)|false|none|none|
|name|[name](#schemaname)|false|none|none|

<h2 id="tocSfirewallbriefindex">FirewallBriefIndex</h2>

<a id="schemafirewallbriefindex"></a>

```json
{
  "x123xx1x-123x-1x12-123x-123xxx123x1x": {
    "status": "active",
    "labels": [],
    "object_uuid": "9a3fdd6e-fc2c-43a3-a8ac-6ec06898f9ce",
    "change_time": "2017-10-18T10:05:15Z",
    "rules": {
      "rules-v6-in": [
        {
          "order": 0,
          "protocol": "tcp",
          "action": "accept",
          "dst_port": "22"
        }
      ],
      "rules-v4-in": [
        {
          "order": 0,
          "protocol": "tcp",
          "action": "accept",
          "dst_port": "22"
        }
      ],
      "rules-v4-out": [],
      "rules-v6-out": []
    },
    "create_time": "2017-10-17T12:38:42Z",
    "private": false,
    "relations": {
      "networks": []
    },
    "name": "Webserver + SSH"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|**additionalProperties**|[Firewall](#schemafirewall)|false|none|none|

<h2 id="tocSfirewallgetresponse">FirewallGetResponse</h2>

<a id="schemafirewallgetresponse"></a>

```json
{
  "firewall": {
    "status": "active",
    "labels": [],
    "object_uuid": "9a3fdd6e-fc2c-43a3-a8ac-6ec06898f9ce",
    "change_time": "2017-10-18T10:05:15Z",
    "rules": {
      "rules-v6-in": [
        {
          "order": 0,
          "protocol": "tcp",
          "action": "accept",
          "dst_port": "22"
        }
      ],
      "rules-v4-in": [
        {
          "order": 0,
          "protocol": "tcp",
          "action": "accept",
          "dst_port": "22"
        }
      ],
      "rules-v4-out": [],
      "rules-v6-out": []
    },
    "create_time": "2017-10-17T12:38:42Z",
    "private": false,
    "relations": {
      "networks": []
    },
    "name": "Webserver + SSH"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|firewall|[Firewall](#schemafirewall)|false|none|none|

<h2 id="tocSfirewallsgetresponse">FirewallsGetResponse</h2>

<a id="schemafirewallsgetresponse"></a>

```json
{
  "firewalls": {
    "x123xx1x-123x-1x12-123x-123xxx123x1x": {
      "status": "active",
      "labels": [],
      "object_uuid": "9a3fdd6e-fc2c-43a3-a8ac-6ec06898f9ce",
      "change_time": "2017-10-18T10:05:15Z",
      "rules": {
        "rules-v6-in": [
          {
            "order": 0,
            "protocol": "tcp",
            "action": "accept",
            "dst_port": "22"
          }
        ],
        "rules-v4-in": [
          {
            "order": 0,
            "protocol": "tcp",
            "action": "accept",
            "dst_port": "22"
          }
        ],
        "rules-v4-out": [],
        "rules-v6-out": []
      },
      "create_time": "2017-10-17T12:38:42Z",
      "private": false,
      "relations": {
        "networks": []
      },
      "name": "Webserver + SSH"
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|firewalls|[FirewallBriefIndex](#schemafirewallbriefindex)|false|none|none|

<h2 id="tocSisoimagecreate">IsoimageCreate</h2>

<a id="schemaisoimagecreate"></a>

```json
{
  "name": "swagger iso new",
  "source_url": "http://releases.ubuntu.com/16.04.4/ubuntu-16.04.4-server-amd64.iso?_ga=2.188975915.108704605.1521033305-403279979.1521033305",
  "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|[name](#schemaname)|true|none|none|
|source_url|string|true|none|network_source_url contains the source URL of the ISO-Image that it was originally fetched from.|
|labels|[labels](#schemalabels)|false|none|none|
|location_uuid|[location_uuid](#schemalocation_uuid)|true|none|none|

<h2 id="tocSisoimageupdate">IsoimageUpdate</h2>

<a id="schemaisoimageupdate"></a>

```json
{
  "name": "swagger iso update"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|[name](#schemaname)|false|none|none|
|labels|[labels](#schemalabels)|false|none|none|

<h2 id="tocSisoimage">Isoimage</h2>

<a id="schemaisoimage"></a>

```json
{
  "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
  "relations": {
    "servers": []
  },
  "description": null,
  "location_name": "de/fra",
  "source_url": "http://de.releases.ubuntu.com/16.04.3/ubuntu-16.04.3-server-amd64.iso",
  "labels": [],
  "location_iata": "fra",
  "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
  "status": "active",
  "create_time": "2017-10-25T12:39:23Z",
  "name": "Ubuntu 16.04.03 LTS",
  "version": null,
  "location_country": "de",
  "usage_in_minutes": 0,
  "private": false,
  "change_time": "2017-10-26T15:52:34Z",
  "capacity": 1,
  "current_price": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|object_uuid|[object_uuid](#schemaobject_uuid)|false|none|none|
|relations|[relation](#schemarelation)|false|none|none|
|description|string|false|none|Description of the ISO-Image release|
|location_name|[location_name](#schemalocation_name)|false|none|none|
|source_url|string|false|none|network_source_url contains the source URL of the ISO-Image that it was originally fetched from.|
|labels|[labels](#schemalabels)|false|none|none|
|location_iata|[location_iata](#schemalocation_iata)|false|none|none|
|location_uuid|[location_uuid](#schemalocation_uuid)|false|none|none|
|status|[status](#schemastatus)|false|none|none|
|create_time|[create_time](#schemacreate_time)|false|none|none|
|name|[name](#schemaname)|false|none|none|
|version|string|false|none|Upstream version of the ISO-Image release|
|location_country|[location_country](#schemalocation_country)|false|none|none|
|usage_in_minutes|[usage_in_minutes](#schemausage_in_minutes)|false|none|none|
|private|boolean|false|none|Whether the ISO-Image is private or not.|
|change_time|[change_time](#schemachange_time)|false|none|none|
|capacity|integer|false|none|The capacity of a storage/ISO-Image/template/snapshot in GB.|
|current_price|[current_price](#schemacurrent_price)|false|none|none|

<h2 id="tocSisoimagebriefindex">IsoimageBriefIndex</h2>

<a id="schemaisoimagebriefindex"></a>

```json
{
  "x123xx1x-123x-1x12-123x-123xxx123x1x": {
    "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
    "relations": {
      "servers": []
    },
    "description": null,
    "location_name": "de/fra",
    "source_url": "http://de.releases.ubuntu.com/16.04.3/ubuntu-16.04.3-server-amd64.iso",
    "labels": [],
    "location_iata": "fra",
    "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
    "status": "active",
    "create_time": "2017-10-25T12:39:23Z",
    "name": "Ubuntu 16.04.03 LTS",
    "version": null,
    "location_country": "de",
    "usage_in_minutes": 0,
    "private": false,
    "change_time": "2017-10-26T15:52:34Z",
    "capacity": 1,
    "current_price": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|**additionalProperties**|[Isoimage](#schemaisoimage)|false|none|none|

<h2 id="tocSisoimagegetresponse">IsoimageGetResponse</h2>

<a id="schemaisoimagegetresponse"></a>

```json
{
  "isoimage": {
    "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
    "relations": {
      "servers": []
    },
    "description": null,
    "location_name": "de/fra",
    "source_url": "http://de.releases.ubuntu.com/16.04.3/ubuntu-16.04.3-server-amd64.iso",
    "labels": [],
    "location_iata": "fra",
    "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
    "status": "active",
    "create_time": "2017-10-25T12:39:23Z",
    "name": "Ubuntu 16.04.03 LTS",
    "version": null,
    "location_country": "de",
    "usage_in_minutes": 0,
    "private": false,
    "change_time": "2017-10-26T15:52:34Z",
    "capacity": 1,
    "current_price": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isoimage|[Isoimage](#schemaisoimage)|false|none|none|

<h2 id="tocSisoimagesgetresponse">IsoimagesGetResponse</h2>

<a id="schemaisoimagesgetresponse"></a>

```json
{
  "isoimages": {
    "x123xx1x-123x-1x12-123x-123xxx123x1x": {
      "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
      "relations": {
        "servers": []
      },
      "description": null,
      "location_name": "de/fra",
      "source_url": "http://de.releases.ubuntu.com/16.04.3/ubuntu-16.04.3-server-amd64.iso",
      "labels": [],
      "location_iata": "fra",
      "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
      "status": "active",
      "create_time": "2017-10-25T12:39:23Z",
      "name": "Ubuntu 16.04.03 LTS",
      "version": null,
      "location_country": "de",
      "usage_in_minutes": 0,
      "private": false,
      "change_time": "2017-10-26T15:52:34Z",
      "capacity": 1,
      "current_price": 0
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isoimages|[IsoimageBriefIndex](#schemaisoimagebriefindex)|false|none|none|

<h2 id="tocSsshkeycreate">SshkeyCreate</h2>

<a id="schemasshkeycreate"></a>

```json
{
  "name": "sshkey",
  "sshkey": "{sshkey}}"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|[name](#schemaname)|true|none|none|
|labels|[labels](#schemalabels)|false|none|none|
|sshkey|string|true|none|sshkey_string is the OpenSSH public key string (all key types are supported => ed25519, ecdsa, dsa, rsa, rsa1)|

<h2 id="tocSsshkeyupdate">SshkeyUpdate</h2>

<a id="schemasshkeyupdate"></a>

```json
{
  "name": "new name"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|[name](#schemaname)|false|none|none|
|labels|[labels](#schemalabels)|false|none|none|
|sshkey|string|false|none|sshkey_string is the OpenSSH public key string (all key types are supported => ed25519, ecdsa, dsa, rsa, rsa1)|

<h2 id="tocSsshkey">Sshkey</h2>

<a id="schemasshkey"></a>

```json
{
  "labels": [],
  "user_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
  "create_time": "2018-03-15T19:18:11Z",
  "status": "active",
  "change_time": "2018-03-15T19:18:11Z",
  "name": "test2",
  "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
  "sshkey": "{sshkey}"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|labels|[labels](#schemalabels)|false|none|none|
|user_uuid|string(uuid)|false|none|none|
|create_time|[create_time](#schemacreate_time)|false|none|none|
|status|[status](#schemastatus)|false|none|none|
|change_time|[change_time](#schemachange_time)|false|none|none|
|name|[name](#schemaname)|false|none|none|
|object_uuid|[object_uuid](#schemaobject_uuid)|false|none|none|
|sshkey|string|false|none|sshkey_string is the OpenSSH public key string (all key types are supported => ed25519, ecdsa, dsa, rsa, rsa1).|

<h2 id="tocSsshkeybriefindex">SshkeyBriefIndex</h2>

<a id="schemasshkeybriefindex"></a>

```json
{
  "x123xx1x-123x-1x12-123x-123xxx123x1x": {
    "change_time": "2018-03-15T18:13:07Z",
    "status": "active",
    "sshkey": "{sshkey}",
    "name": "test",
    "labels": [],
    "user_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
    "create_time": "2018-03-15T18:13:07Z",
    "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|**additionalProperties**|[Sshkey](#schemasshkey)|false|none|none|

<h2 id="tocSsshkeygetresponse">SshkeyGetResponse</h2>

<a id="schemasshkeygetresponse"></a>

```json
{
  "Sshkey": {
    "labels": [],
    "user_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
    "create_time": "2018-03-15T19:18:11Z",
    "status": "active",
    "change_time": "2018-03-15T19:18:11Z",
    "name": "test2",
    "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
    "sshkey": "{sshkey}"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Sshkey|[Sshkey](#schemasshkey)|false|none|none|

<h2 id="tocSsshkeysgetresponse">SshkeysGetResponse</h2>

<a id="schemasshkeysgetresponse"></a>

```json
{
  "Sshkeys": {
    "x123xx1x-123x-1x12-123x-123xxx123x1x": {
      "change_time": "2018-03-15T18:13:07Z",
      "status": "active",
      "sshkey": "{sshkey}",
      "name": "test",
      "labels": [],
      "user_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
      "create_time": "2018-03-15T18:13:07Z",
      "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x"
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Sshkeys|[SshkeyBriefIndex](#schemasshkeybriefindex)|false|none|none|

<h2 id="tocSlocation">Location</h2>

<a id="schemalocation"></a>

```json
{
  "iata": "fra",
  "status": "active",
  "labels": [],
  "name": "de/fra",
  "object_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
  "country": "de"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|iata|[location_iata](#schemalocation_iata)|false|none|none|
|status|[status](#schemastatus)|false|none|none|
|labels|[labels](#schemalabels)|false|none|none|
|name|[location_name](#schemalocation_name)|false|none|none|
|object_uuid|[object_uuid](#schemaobject_uuid)|false|none|none|
|country|[location_country](#schemalocation_country)|false|none|none|

<h2 id="tocSlocationbriefindex">LocationBriefIndex</h2>

<a id="schemalocationbriefindex"></a>

```json
{
  "45ed677b-3702-4b36-be2a-a2eab9827950": {
    "status": "active",
    "country": "de",
    "labels": [],
    "name": "de/fra",
    "object_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
    "iata": "fra"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|**additionalProperties**|[Location](#schemalocation)|false|none|none|

<h2 id="tocSlocationgetresponse">LocationGetResponse</h2>

<a id="schemalocationgetresponse"></a>

```json
{
  "location": {
    "iata": "fra",
    "status": "active",
    "labels": [],
    "name": "de/fra",
    "object_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
    "country": "de"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|location|[Location](#schemalocation)|false|none|none|

<h2 id="tocSlocationsgetresponse">LocationsGetResponse</h2>

<a id="schemalocationsgetresponse"></a>

```json
{
  "locations": {
    "45ed677b-3702-4b36-be2a-a2eab9827950": {
      "status": "active",
      "country": "de",
      "labels": [],
      "name": "de/fra",
      "object_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
      "iata": "fra"
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|locations|[LocationBriefIndex](#schemalocationbriefindex)|false|none|none|

<h2 id="tocStemplate">Template</h2>

<a id="schematemplate"></a>

```json
{
  "status": "active",
  "ostype": "windows",
  "version": "Windows Server 2016 Standard",
  "location_iata": "fra",
  "change_time": "2017-10-30T11:50:35Z",
  "private": false,
  "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
  "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
  "license_product_no": 800002,
  "create_time": "2016-10-24T14:50:23Z",
  "usage_in_minutes": 0,
  "name": "Windows Server 2016",
  "capacity": 32,
  "location_name": "de/fra",
  "distro": "Windows Server",
  "description": "SPLA-Licensed",
  "current_price": 0,
  "location_country": "de"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|status|[status](#schemastatus)|false|none|none|
|ostype|string|false|none|The operating system installed in the template.|
|location_uuid|[location_uuid](#schemalocation_uuid)|false|none|none|
|version|string|false|none|Description of the Template|
|location_iata|[location_iata](#schemalocation_iata)|false|none|none|
|change_time|[change_time](#schemachange_time)|false|none|none|
|private|boolean|false|none|the object is private, the value will be true. Otherwise the value will be false.|
|object_uuid|[object_uuid](#schemaobject_uuid)|false|none|none|
|license_product_no|integer|false|none|If a template has been used that requires a license key (e.g. Windows Servers) this shows the product_no of the license (see the /prices endpoint for more details)|
|create_time|[create_time](#schemacreate_time)|false|none|none|
|usage_in_minutes|[usage_in_minutes](#schemausage_in_minutes)|false|none|none|
|capacity|integer|false|none|The capacity of a storage/ISO-Image/template/snapshot in GB.|
|location_name|[location_name](#schemalocation_name)|false|none|none|
|distro|string|false|none|none|
|description|string|false|none|Description of the Template|
|current_price|[current_price](#schemacurrent_price)|false|none|none|
|location_country|[location_country](#schemalocation_country)|false|none|none|

<h2 id="tocStemplatebriefindex">TemplateBriefIndex</h2>

<a id="schematemplatebriefindex"></a>

```json
{
  "x123xx1x-123x-1x12-123x-123xxx123x1x": {
    "status": "active",
    "ostype": "windows",
    "version": "Windows Server 2016 Standard",
    "location_iata": "fra",
    "change_time": "2017-10-30T11:50:35Z",
    "private": false,
    "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
    "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
    "license_product_no": 800002,
    "create_time": "2016-10-24T14:50:23Z",
    "usage_in_minutes": 0,
    "name": "Windows Server 2016",
    "capacity": 32,
    "location_name": "de/fra",
    "distro": "Windows Server",
    "description": "SPLA-Licensed",
    "current_price": 0,
    "location_country": "de"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|**additionalProperties**|[Template](#schematemplate)|false|none|none|

<h2 id="tocStemplategetresponse">TemplateGetResponse</h2>

<a id="schematemplategetresponse"></a>

```json
{
  "location": {
    "status": "active",
    "ostype": "windows",
    "version": "Windows Server 2016 Standard",
    "location_iata": "fra",
    "change_time": "2017-10-30T11:50:35Z",
    "private": false,
    "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
    "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
    "license_product_no": 800002,
    "create_time": "2016-10-24T14:50:23Z",
    "usage_in_minutes": 0,
    "name": "Windows Server 2016",
    "capacity": 32,
    "location_name": "de/fra",
    "distro": "Windows Server",
    "description": "SPLA-Licensed",
    "current_price": 0,
    "location_country": "de"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|location|[Template](#schematemplate)|false|none|none|

<h2 id="tocStemplatesgetresponse">TemplatesGetResponse</h2>

<a id="schematemplatesgetresponse"></a>

```json
{
  "locations": {
    "x123xx1x-123x-1x12-123x-123xxx123x1x": {
      "status": "active",
      "ostype": "windows",
      "version": "Windows Server 2016 Standard",
      "location_iata": "fra",
      "change_time": "2017-10-30T11:50:35Z",
      "private": false,
      "object_uuid": "x123xx1x-123x-1x12-123x-123xxx123x1x",
      "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950",
      "license_product_no": 800002,
      "create_time": "2016-10-24T14:50:23Z",
      "usage_in_minutes": 0,
      "name": "Windows Server 2016",
      "capacity": 32,
      "location_name": "de/fra",
      "distro": "Windows Server",
      "description": "SPLA-Licensed",
      "current_price": 0,
      "location_country": "de"
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|locations|[TemplateBriefIndex](#schematemplatebriefindex)|false|none|none|

<h2 id="tocSaccesskeycreate">AccessKeyCreate</h2>

<a id="schemaaccesskeycreate"></a>

```json
{
  "secret_key": "string",
  "access_key": "string",
  "user": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|secret_key|string|false|none|The object storage secret_key|
|access_key|string|false|none|The object storage access_key|
|user|string|false|none|Account this credentials belong to.|

<h2 id="tocSaccesskeycreateresponse">AccessKeyCreateResponse</h2>

<a id="schemaaccesskeycreateresponse"></a>

```json
{
  "access_key": {
    "secret_key": "string",
    "access_key": "string"
  },
  "request_uuid": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|access_key|object|false|none|none|
|» secret_key|string|false|none|The object storage secret_key|
|» access_key|string|false|none|The object storage access_key|
|request_uuid|string|false|none|The unique id for the request.|

<h2 id="tocSaccesskey">AccessKey</h2>

<a id="schemaaccesskey"></a>

```json
{
  "secret_key": "string",
  "access_key": "string",
  "user": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|secret_key|string|false|none|The object storage secret_key|
|access_key|string|false|none|The object storage access_key|
|user|string|false|none|Account this credentials belong to.|

<h2 id="tocSaccesskeybriefindex">AccessKeyBriefIndex</h2>

<a id="schemaaccesskeybriefindex"></a>

```json
[
  {
    "secret_key": "string",
    "access_key": "string",
    "user": "string"
  }
]

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[AccessKey](#schemaaccesskey)]|false|none|none|

<h2 id="tocSaccesskeygetresponse">AccessKeyGetResponse</h2>

<a id="schemaaccesskeygetresponse"></a>

```json
{
  "access_key": {
    "secret_key": "{secret_key}",
    "access_key": "{access_key}"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|access_key|[AccessKey](#schemaaccesskey)|false|none|none|

<h2 id="tocSaccesskeysgetresponse">AccessKeysGetResponse</h2>

<a id="schemaaccesskeysgetresponse"></a>

```json
{
  "access_keys": [
    {
      "secret_key": "{secret_key}",
      "access_key": "{access_key}"
    },
    {
      "secret_key": "{secret_key}",
      "access_key": "{access_key}"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|access_keys|[AccessKeyBriefIndex](#schemaaccesskeybriefindex)|false|none|none|

<h2 id="tocSbucket">Bucket</h2>

<a id="schemabucket"></a>

```json
{
  "name": "string",
  "ussage": {
    "size_kb": 0,
    "num_objects": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|[name](#schemaname)|false|none|none|
|ussage|object|false|none|The current usage of the bucket.|
|» size_kb|integer|false|none|The size of the the bucket (in kb)|
|» num_objects|integer|false|none|The number of files in the bucket|

<h2 id="tocSbucketbriefindex">BucketBriefIndex</h2>

<a id="schemabucketbriefindex"></a>

```json
[
  {
    "name": "string",
    "ussage": {
      "size_kb": 0,
      "num_objects": 0
    }
  }
]

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Bucket](#schemabucket)]|false|none|none|

<h2 id="tocSbucketgetresponse">BucketGetResponse</h2>

<a id="schemabucketgetresponse"></a>

```json
{
  "Bucket": {
    "name": "string",
    "ussage": {
      "size_kb": 0,
      "num_objects": 0
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Bucket|[Bucket](#schemabucket)|false|none|none|

<h2 id="tocSbucketsgetresponse">BucketsGetResponse</h2>

<a id="schemabucketsgetresponse"></a>

```json
{
  "Buckets": [
    {
      "name": "string",
      "ussage": {
        "size_kb": 0,
        "num_objects": 0
      }
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Buckets|[BucketBriefIndex](#schemabucketbriefindex)|false|none|none|

<h2 id="tocSrequest">Request</h2>

<a id="schemarequest"></a>

```json
{
  "create_time": "2018-08-28T08:15:36Z",
  "status": "string",
  "message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|create_time|[create_time](#schemacreate_time)|false|none|none|
|status|[status](#schemastatus)|false|none|none|
|message|string|false|none|none|

<h2 id="tocSrequestgetresponse">RequestGetResponse</h2>

<a id="schemarequestgetresponse"></a>

```json
{
  "4e10fb40-47e3-4fd0-aaf3-c16335757f93": {
    "create_time": "2018-06-04T11:51:34Z",
    "status": "done",
    "message": "Success."
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|**additionalProperties**|[Request](#schemarequest)|false|none|none|

<h2 id="tocSfilters">filters</h2>

<a id="schemafilters"></a>

```json
[
  {
    "operator": "string",
    "field": "string",
    "comparison_value": 0
  }
]

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|operator|string|false|none|none|
|field|string|false|none|none|
|comparison_value|integer|false|none|none|

<h2 id="tocSaction_payload">action_payload</h2>

<a id="schemaaction_payload"></a>

```json
{}

```

### Properties

*None*

<h2 id="tocScascreate">CasCreate</h2>

<a id="schemacascreate"></a>

```json
{
  "action_payload": {},
  "name": "string",
  "labels": [
    "string"
  ],
  "filters": [
    {
      "operator": "string",
      "field": "string",
      "comparison_value": 0
    }
  ],
  "status": "string",
  "active": true,
  "event_type": "string",
  "action_type": "send_email"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|action_payload|object|true|none|The payload you would like to fire if the event_types values pass the filters.|
|name|[name](#schemaname)|true|none|none|
|labels|[labels](#schemalabels)|false|none|none|
|filters|[filters](#schemafilters)|true|none|none|
|status|[status](#schemastatus)|false|none|none|
|active|boolean|false|none|none|
|event_type|string|true|none|The event_type you would like to track - you can find a list of all possible|
|action_type|string|true|none|One of three values send_email, send_slack or http_request. Each of these will require a different set of values to be sent in the POST request. see the list here.|

#### Enumerated Values

|Property|Value|
|---|---|
|action_type|send_email|
|action_type|send_slack|
|action_type|http_request|

<h2 id="tocScastask">CasTask</h2>

<a id="schemacastask"></a>

```json
{
  "action_type": "send_email",
  "change_time": "2018-08-28T08:15:36Z",
  "status": "string",
  "labels": [
    "string"
  ],
  "object_uuid": "string",
  "name": "string",
  "event_type": "string",
  "action_payload": {},
  "active": "string",
  "filters": [
    {
      "operator": "string",
      "field": "string",
      "comparison_value": 0
    }
  ],
  "create_time": "2018-08-28T08:15:36Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|action_type|string|false|none|A keyword describing the event executed when the task is triggered|
|change_time|[change_time](#schemachange_time)|false|none|none|
|status|[status](#schemastatus)|false|none|none|
|labels|[labels](#schemalabels)|false|none|none|
|object_uuid|[object_uuid](#schemaobject_uuid)|false|none|none|
|name|[name](#schemaname)|false|none|none|
|event_type|string|false|none|The event that will trigger the task|
|action_payload|[action_payload](#schemaaction_payload)|false|none|none|
|active|string|false|none|Defines if this task is currently active|
|filters|[filters](#schemafilters)|false|none|none|
|create_time|[create_time](#schemacreate_time)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|action_type|send_email|
|action_type|http_request|
|action_type|send_slack|

<h2 id="tocScastaskbriefindex">CasTaskBriefIndex</h2>

<a id="schemacastaskbriefindex"></a>

```json
{
  "property1": {
    "action_type": "send_email",
    "change_time": "2018-08-28T08:15:36Z",
    "status": "string",
    "labels": [
      "string"
    ],
    "object_uuid": "string",
    "name": "string",
    "event_type": "string",
    "action_payload": {},
    "active": "string",
    "filters": [
      {
        "operator": "string",
        "field": "string",
        "comparison_value": 0
      }
    ],
    "create_time": "2018-08-28T08:15:36Z"
  },
  "property2": {
    "action_type": "send_email",
    "change_time": "2018-08-28T08:15:36Z",
    "status": "string",
    "labels": [
      "string"
    ],
    "object_uuid": "string",
    "name": "string",
    "event_type": "string",
    "action_payload": {},
    "active": "string",
    "filters": [
      {
        "operator": "string",
        "field": "string",
        "comparison_value": 0
      }
    ],
    "create_time": "2018-08-28T08:15:36Z"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|**additionalProperties**|[CasTask](#schemacastask)|false|none|none|

<h2 id="tocScastaskgetresponse">CasTaskGetResponse</h2>

<a id="schemacastaskgetresponse"></a>

```json
{
  "task": {
    "action_type": "send_email",
    "change_time": "2018-08-28T08:15:36Z",
    "status": "string",
    "labels": [
      "string"
    ],
    "object_uuid": "string",
    "name": "string",
    "event_type": "string",
    "action_payload": {},
    "active": "string",
    "filters": [
      {
        "operator": "string",
        "field": "string",
        "comparison_value": 0
      }
    ],
    "create_time": "2018-08-28T08:15:36Z"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|task|[CasTask](#schemacastask)|false|none|none|

<h2 id="tocScastasksgetresponse">CasTasksGetResponse</h2>

<a id="schemacastasksgetresponse"></a>

```json
{
  "tasks": {
    "property1": {
      "action_type": "send_email",
      "change_time": "2018-08-28T08:15:36Z",
      "status": "string",
      "labels": [
        "string"
      ],
      "object_uuid": "string",
      "name": "string",
      "event_type": "string",
      "action_payload": {},
      "active": "string",
      "filters": [
        {
          "operator": "string",
          "field": "string",
          "comparison_value": 0
        }
      ],
      "create_time": "2018-08-28T08:15:36Z"
    },
    "property2": {
      "action_type": "send_email",
      "change_time": "2018-08-28T08:15:36Z",
      "status": "string",
      "labels": [
        "string"
      ],
      "object_uuid": "string",
      "name": "string",
      "event_type": "string",
      "action_payload": {},
      "active": "string",
      "filters": [
        {
          "operator": "string",
          "field": "string",
          "comparison_value": 0
        }
      ],
      "create_time": "2018-08-28T08:15:36Z"
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|tasks|[CasTaskBriefIndex](#schemacastaskbriefindex)|false|none|none|

<h2 id="tocSpaascreate">PaasCreate</h2>

<a id="schemapaascreate"></a>

```json
{
  "name": "string",
  "paas_service_uuid": "string",
  "labels": [
    "string"
  ],
  "paas_security_zone_uuid": "string",
  "resource_limit": [
    {
      "resource": "string",
      "limit": 0
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|[name](#schemaname)|true|none|none|
|paas_service_uuid|string(uuid)|false|none|The template used to create the service, you can find an available list at the /service_templates endpoint.|
|labels|[labels](#schemalabels)|false|none|none|
|paas_security_zone_uuid|string(uuid)|false|none|The UUID of the security zone that the service is running in.|
|resource_limit|[object]|false|none|An array of objects, allowing you to set resource limits.|
|» resource|string|false|none|The name of the resource you would like to cap.|
|» limit|integer|false|none|The maximum number of the specific resource your service can use.|

<h2 id="tocSpaascreateresponse">PaasCreateResponse</h2>

<a id="schemapaascreateresponse"></a>

```json
{
  "request_uuid": "string",
  "listen_ports": {
    "IPv6": {
      "mysql": 0
    }
  },
  "paas_service_uuid": "string",
  "credentials": [
    {
      "password": "string",
      "username": "string",
      "type": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|request_uuid|string(uuid)|false|none|The UUID identifying the request.|
|listen_ports|object|false|none|Contains the IPv6 address and port that the Service will listen to, you can use these details to connect internally to a service.|
|» IPv6|object|false|none|none|
|»» mysql|integer|false|none|The key mysql will change depending on the service, The value 3306 is the listening port of the application|
|» paas_service_uuid|string(uuid)|false|none|The template used to create the service, you can find an available list at the /service_templates endpoint.|
|» credentials|[credentials](#schemacredentials)|false|none|none|

<h2 id="tocSpaasupdaterequest">PaasUpdateRequest</h2>

<a id="schemapaasupdaterequest"></a>

```json
{
  "name": "string",
  "labels": [
    "string"
  ],
  "resource_limit": [
    {
      "resource": "string",
      "limit": 0
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|[name](#schemaname)|false|none|none|
|labels|[labels](#schemalabels)|false|none|none|
|resource_limit|[object]|false|none|An array of objects, allowing you to set resource limits.|
|» resource|string|false|none|The name of the resource you would like to cap.|
|» limit|integer|false|none|The maximum number of the specific resource your service can use.|

<h2 id="tocScredentials">credentials</h2>

<a id="schemacredentials"></a>

```json
[
  {
    "password": "string",
    "username": "string",
    "type": "string"
  }
]

```

*Contains the initial setup credentials for Service.*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|password|string|false|none|The initial username to authenticate the Service.|
|username|string|false|none|The initial password to authenticate the Service.|
|type|string|false|none|The type of Service.|

<h2 id="tocSpaasservice">PaasService</h2>

<a id="schemapaasservice"></a>

```json
{
  "object_uuid": "string",
  "labels": [
    "string"
  ],
  "credentials": [
    {
      "password": "string",
      "username": "string",
      "type": "string"
    }
  ],
  "create_time": "2018-08-28T08:15:36Z",
  "listen_ports": {},
  "security_zone_uuid": "string",
  "service_template_uuid": "string",
  "usage_in_minutes": 0,
  "current_price": 0,
  "change_time": "2018-08-28T08:15:36Z",
  "status": "string",
  "name": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|object_uuid|[object_uuid](#schemaobject_uuid)|false|none|none|
|labels|[labels](#schemalabels)|false|none|none|
|credentials|[credentials](#schemacredentials)|false|none|none|
|create_time|[create_time](#schemacreate_time)|false|none|none|
|listen_ports|object|false|none|Contains the IPv6 address and port that the Service will listen to, you can use these details to connect internally to a service.|
|security_zone_uuid|string(uuid)|false|none|The UUID of the security zone that the service is running in.|
|service_template_uuid|string(uuid)|false|none|The template used to create the service, you can find an available list at the /service_templates endpoint.|
|usage_in_minutes|[usage_in_minutes](#schemausage_in_minutes)|false|none|none|
|current_price|[current_price](#schemacurrent_price)|false|none|none|
|change_time|[change_time](#schemachange_time)|false|none|none|
|status|[status](#schemastatus)|false|none|none|
|name|[name](#schemaname)|false|none|none|

<h2 id="tocSpaasservicebriefindex">PaasServiceBriefIndex</h2>

<a id="schemapaasservicebriefindex"></a>

```json
{
  "property1": {
    "object_uuid": "string",
    "labels": [
      "string"
    ],
    "credentials": [
      {
        "password": "string",
        "username": "string",
        "type": "string"
      }
    ],
    "create_time": "2018-08-28T08:15:36Z",
    "listen_ports": {},
    "security_zone_uuid": "string",
    "service_template_uuid": "string",
    "usage_in_minutes": 0,
    "current_price": 0,
    "change_time": "2018-08-28T08:15:36Z",
    "status": "string",
    "name": "string"
  },
  "property2": {
    "object_uuid": "string",
    "labels": [
      "string"
    ],
    "credentials": [
      {
        "password": "string",
        "username": "string",
        "type": "string"
      }
    ],
    "create_time": "2018-08-28T08:15:36Z",
    "listen_ports": {},
    "security_zone_uuid": "string",
    "service_template_uuid": "string",
    "usage_in_minutes": 0,
    "current_price": 0,
    "change_time": "2018-08-28T08:15:36Z",
    "status": "string",
    "name": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|**additionalProperties**|[PaasService](#schemapaasservice)|false|none|none|

<h2 id="tocSpaasservicegetresponse">PaasServiceGetResponse</h2>

<a id="schemapaasservicegetresponse"></a>

```json
{
  "task": {
    "object_uuid": "string",
    "labels": [
      "string"
    ],
    "credentials": [
      {
        "password": "string",
        "username": "string",
        "type": "string"
      }
    ],
    "create_time": "2018-08-28T08:15:36Z",
    "listen_ports": {},
    "security_zone_uuid": "string",
    "service_template_uuid": "string",
    "usage_in_minutes": 0,
    "current_price": 0,
    "change_time": "2018-08-28T08:15:36Z",
    "status": "string",
    "name": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|task|[PaasService](#schemapaasservice)|false|none|none|

<h2 id="tocSpaasservicesgetresponse">PaasServicesGetResponse</h2>

<a id="schemapaasservicesgetresponse"></a>

```json
{
  "tasks": {
    "property1": {
      "object_uuid": "string",
      "labels": [
        "string"
      ],
      "credentials": [
        {
          "password": "string",
          "username": "string",
          "type": "string"
        }
      ],
      "create_time": "2018-08-28T08:15:36Z",
      "listen_ports": {},
      "security_zone_uuid": "string",
      "service_template_uuid": "string",
      "usage_in_minutes": 0,
      "current_price": 0,
      "change_time": "2018-08-28T08:15:36Z",
      "status": "string",
      "name": "string"
    },
    "property2": {
      "object_uuid": "string",
      "labels": [
        "string"
      ],
      "credentials": [
        {
          "password": "string",
          "username": "string",
          "type": "string"
        }
      ],
      "create_time": "2018-08-28T08:15:36Z",
      "listen_ports": {},
      "security_zone_uuid": "string",
      "service_template_uuid": "string",
      "usage_in_minutes": 0,
      "current_price": 0,
      "change_time": "2018-08-28T08:15:36Z",
      "status": "string",
      "name": "string"
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|tasks|[PaasServiceBriefIndex](#schemapaasservicebriefindex)|false|none|none|

<h2 id="tocSpaasservicetemplate">PaasServiceTemplate</h2>

<a id="schemapaasservicetemplate"></a>

```json
{
  "name": "string",
  "object_uuid": "string",
  "category": "string",
  "labels": [
    "string"
  ],
  "product_no": 0,
  "resources": {
    "memory": 0,
    "connections": 0
  },
  "status": "string",
  "parameters_schema": [
    "string"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|[name](#schemaname)|false|none|none|
|object_uuid|[object_uuid](#schemaobject_uuid)|false|none|none|
|category|string|false|none|Describes the catagory of the service.|
|labels|[labels](#schemalabels)|false|none|none|
|product_no|integer|false|none|none|
|resources|object|false|none|The amount of concurrent connections for the service.|
|» memory|integer|false|none|The amount of memory required by the service, either RAM(MB) or SSD Storage(GB)|
|» connections|integer|false|none|The amount of concurrent connections for the service.|
|status|[status](#schemastatus)|false|none|none|
|parameters_schema|[string]|false|none|none|

<h2 id="tocSpaasservicetemplateindex">PaasServiceTemplateIndex</h2>

<a id="schemapaasservicetemplateindex"></a>

```json
{
  "property1": {
    "name": "string",
    "object_uuid": "string",
    "category": "string",
    "labels": [
      "string"
    ],
    "product_no": 0,
    "resources": {
      "memory": 0,
      "connections": 0
    },
    "status": "string",
    "parameters_schema": [
      "string"
    ]
  },
  "property2": {
    "name": "string",
    "object_uuid": "string",
    "category": "string",
    "labels": [
      "string"
    ],
    "product_no": 0,
    "resources": {
      "memory": 0,
      "connections": 0
    },
    "status": "string",
    "parameters_schema": [
      "string"
    ]
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|**additionalProperties**|[PaasServiceTemplate](#schemapaasservicetemplate)|false|none|none|

<h2 id="tocSpaasservicetemplatesgetresponse">PaasServiceTemplatesGetResponse</h2>

<a id="schemapaasservicetemplatesgetresponse"></a>

```json
{
  "paas_service_templates": {
    "9dbe21ed-2033-4253-8228-b5f39b076f04": {
      "object_uuid": "9dbe21ed-2033-4253-8228-b5f39b076f04",
      "status": "active",
      "parameters_schema": {},
      "category": "database",
      "name": "PostgreSQL 10.3 64GB (Gen 1)",
      "product_no": 1200014,
      "resources": {
        "memory": 65536,
        "connections": 4000
      },
      "labels": []
    },
    "56385ef4-5ec6-4aa4-9ff5-9cb10348875b": {
      "object_uuid": "56385ef4-5ec6-4aa4-9ff5-9cb10348875b",
      "status": "active",
      "parameters_schema": {},
      "category": "key_value_store",
      "name": "Redis 4.0 8GB (Gen 1)",
      "product_no": 1202013,
      "resources": {
        "memory": 8192
      },
      "labels": []
    },
    "9008f1f1-190e-4887-99f7-8a3e72fdd1f8": {
      "object_uuid": "9008f1f1-190e-4887-99f7-8a3e72fdd1f8",
      "status": "active",
      "parameters_schema": {},
      "category": "database",
      "name": "PostgreSQL 10.3 16GB (Gen 1)",
      "product_no": 1200012,
      "resources": {
        "memory": 16384,
        "connections": 4000
      },
      "labels": []
    },
    "1b888615-4e84-444b-b112-94c110fb1d8d": {
      "object_uuid": "1b888615-4e84-444b-b112-94c110fb1d8d",
      "status": "active",
      "parameters_schema": {},
      "category": "database",
      "name": "MySQL 5.7 64GB (Gen 1)",
      "product_no": 1201014,
      "resources": {
        "memory": 65536,
        "connections": 4000
      },
      "labels": []
    },
    "8175d5af-d974-456c-bd8e-b934770b3e6d": {
      "object_uuid": "8175d5af-d974-456c-bd8e-b934770b3e6d",
      "status": "active",
      "parameters_schema": {},
      "category": "database",
      "name": "PostgreSQL 10.3 4GB (Gen 1)",
      "product_no": 1200011,
      "resources": {
        "memory": 4096,
        "connections": 4000
      },
      "labels": []
    },
    "f6c714c0-384b-4674-b9d9-d74ae338e1a1": {
      "object_uuid": "f6c714c0-384b-4674-b9d9-d74ae338e1a1",
      "status": "active",
      "parameters_schema": {},
      "category": "database",
      "name": "MySQL 5.7 16GB (Gen 1)",
      "product_no": 1201012,
      "resources": {
        "memory": 16384,
        "connections": 4000
      },
      "labels": []
    },
    "bb106b9a-2f96-44d9-bdf0-c568086124a1": {
      "object_uuid": "bb106b9a-2f96-44d9-bdf0-c568086124a1",
      "status": "active",
      "parameters_schema": {},
      "category": "key_value_store",
      "name": "Redis 4.0 4GB (Gen 1)",
      "product_no": 1202012,
      "resources": {
        "memory": 4096
      },
      "labels": []
    },
    "a2367d6b-450b-44a8-bfab-0424bf826cf8": {
      "object_uuid": "a2367d6b-450b-44a8-bfab-0424bf826cf8",
      "status": "active",
      "parameters_schema": {},
      "category": "key_value_store",
      "name": "Redis 4.0 16GB (Gen 1)",
      "product_no": 1202014,
      "resources": {
        "memory": 16384
      },
      "labels": []
    },
    "8bcb216c-65ec-4c93-925d-1b8feaa5c2c5": {
      "object_uuid": "8bcb216c-65ec-4c93-925d-1b8feaa5c2c5",
      "status": "active",
      "parameters_schema": {},
      "category": "database",
      "name": "MySQL 5.7 4GB (Gen 1)",
      "product_no": 1201011,
      "resources": {
        "memory": 4096,
        "connections": 4000
      },
      "labels": []
    },
    "3211331b-f5d7-4826-884e-0aba4172df56": {
      "object_uuid": "3211331b-f5d7-4826-884e-0aba4172df56",
      "status": "active",
      "parameters_schema": {},
      "category": "database",
      "name": "MySQL 5.7 32GB (Gen 1)",
      "product_no": 1201013,
      "resources": {
        "memory": 32768,
        "connections": 4000
      },
      "labels": []
    },
    "646c7dcf-7e0b-41b8-8f99-9b6dce0e26e4": {
      "object_uuid": "646c7dcf-7e0b-41b8-8f99-9b6dce0e26e4",
      "status": "active",
      "parameters_schema": {},
      "category": "key_value_store",
      "name": "Redis 4.0 2GB (Gen 1)",
      "product_no": 1202011,
      "resources": {
        "memory": 2048
      },
      "labels": []
    },
    "873ae463-d1bb-4305-9fce-622912140662": {
      "object_uuid": "873ae463-d1bb-4305-9fce-622912140662",
      "status": "active",
      "parameters_schema": {},
      "category": "database",
      "name": "PostgreSQL 10.3 32GB (Gen 1)",
      "product_no": 1200013,
      "resources": {
        "memory": 32768,
        "connections": 4000
      },
      "labels": []
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|paas_service_templates|[PaasServiceTemplateIndex](#schemapaasservicetemplateindex)|false|none|none|

<h2 id="tocSpaassecurityzonecreate">PaasSecurityZoneCreate</h2>

<a id="schemapaassecurityzonecreate"></a>

```json
{
  "name": "new psz",
  "location_uuid": "45ed677b-3702-4b36-be2a-a2eab9827950"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|[name](#schemaname)|false|none|none|
|location_uuid|[location_uuid](#schemalocation_uuid)|false|none|none|

<h2 id="tocSpaassecurityzonecreateresponse">PaasSecurityZoneCreateResponse</h2>

<a id="schemapaassecurityzonecreateresponse"></a>

```json
{
  "request_uuid": "0df82edc-b0b9-461f-a72c-f210ddaddfc8",
  "paas_security_zone_uuid": "da792f47-a2d2-48a5-974c-3446c8374e6d"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|request_uuid|string(uuid)|false|none|none|
|paas_security_zone_uuid|string(uuid)|false|none|none|

<h2 id="tocSpaassecurityzoneupdate">PaasSecurityZoneUpdate</h2>

<a id="schemapaassecurityzoneupdate"></a>

```json
{
  "name": "new zone",
  "labels": [
    "Test Zone"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|The new name you give to the security zone.|
|location_uuid|string(uuid)|false|none|The new name you give to the security zone.|
|paas_security_zone_uuid|string(uuid)|false|none|The UUID for the security zone you would like to update.|

<h2 id="tocSpaassecurityzone">PaasSecurityZone</h2>

<a id="schemapaassecurityzone"></a>

```json
{
  "location_country": "string",
  "relations": {
    "object1": [
      {}
    ]
  },
  "create_time": "2018-08-28T08:15:36Z",
  "location_iata": "string",
  "object_uuid": "string",
  "labels": [
    "string"
  ],
  "location_name": "string",
  "status": "string",
  "location_uuid": "string",
  "change_time": "2018-08-28T08:15:36Z",
  "name": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|location_country|[location_country](#schemalocation_country)|false|none|none|
|relations|[relation](#schemarelation)|false|none|none|
|create_time|[create_time](#schemacreate_time)|false|none|none|
|location_iata|[location_iata](#schemalocation_iata)|false|none|none|
|object_uuid|[object_uuid](#schemaobject_uuid)|false|none|none|
|labels|[labels](#schemalabels)|false|none|none|
|location_name|[location_name](#schemalocation_name)|false|none|none|
|status|[status](#schemastatus)|false|none|none|
|location_uuid|[location_uuid](#schemalocation_uuid)|false|none|none|
|change_time|[change_time](#schemachange_time)|false|none|none|
|name|[name](#schemaname)|false|none|none|

<h2 id="tocSpaassecurityzonebriefindex">PaasSecurityZoneBriefIndex</h2>

<a id="schemapaassecurityzonebriefindex"></a>

```json
{
  "property1": {
    "location_country": "string",
    "relations": {
      "object1": [
        {}
      ]
    },
    "create_time": "2018-08-28T08:15:36Z",
    "location_iata": "string",
    "object_uuid": "string",
    "labels": [
      "string"
    ],
    "location_name": "string",
    "status": "string",
    "location_uuid": "string",
    "change_time": "2018-08-28T08:15:36Z",
    "name": "string"
  },
  "property2": {
    "location_country": "string",
    "relations": {
      "object1": [
        {}
      ]
    },
    "create_time": "2018-08-28T08:15:36Z",
    "location_iata": "string",
    "object_uuid": "string",
    "labels": [
      "string"
    ],
    "location_name": "string",
    "status": "string",
    "location_uuid": "string",
    "change_time": "2018-08-28T08:15:36Z",
    "name": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|**additionalProperties**|[PaasSecurityZone](#schemapaassecurityzone)|false|none|none|

<h2 id="tocSpaassecurityzonegetresponse">PaasSecurityZoneGetResponse</h2>

<a id="schemapaassecurityzonegetresponse"></a>

```json
{
  "paas_security_zone": {
    "property1": {
      "location_country": "string",
      "relations": {
        "object1": [
          {}
        ]
      },
      "create_time": "2018-08-28T08:15:36Z",
      "location_iata": "string",
      "object_uuid": "string",
      "labels": [
        "string"
      ],
      "location_name": "string",
      "status": "string",
      "location_uuid": "string",
      "change_time": "2018-08-28T08:15:36Z",
      "name": "string"
    },
    "property2": {
      "location_country": "string",
      "relations": {
        "object1": [
          {}
        ]
      },
      "create_time": "2018-08-28T08:15:36Z",
      "location_iata": "string",
      "object_uuid": "string",
      "labels": [
        "string"
      ],
      "location_name": "string",
      "status": "string",
      "location_uuid": "string",
      "change_time": "2018-08-28T08:15:36Z",
      "name": "string"
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|paas_security_zone|object|false|none|none|
|» **additionalProperties**|[PaasSecurityZone](#schemapaassecurityzone)|false|none|none|

<h2 id="tocSpaassecurityzonesgetresponse">PaasSecurityZonesGetResponse</h2>

<a id="schemapaassecurityzonesgetresponse"></a>

```json
{
  "paas_security_zone": {
    "property1": {
      "property1": {
        "location_country": "string",
        "relations": {
          "object1": [
            {}
          ]
        },
        "create_time": "2018-08-28T08:15:36Z",
        "location_iata": "string",
        "object_uuid": "string",
        "labels": [
          "string"
        ],
        "location_name": "string",
        "status": "string",
        "location_uuid": "string",
        "change_time": "2018-08-28T08:15:36Z",
        "name": "string"
      },
      "property2": {
        "location_country": "string",
        "relations": {
          "object1": [
            {}
          ]
        },
        "create_time": "2018-08-28T08:15:36Z",
        "location_iata": "string",
        "object_uuid": "string",
        "labels": [
          "string"
        ],
        "location_name": "string",
        "status": "string",
        "location_uuid": "string",
        "change_time": "2018-08-28T08:15:36Z",
        "name": "string"
      }
    },
    "property2": {
      "property1": {
        "location_country": "string",
        "relations": {
          "object1": [
            {}
          ]
        },
        "create_time": "2018-08-28T08:15:36Z",
        "location_iata": "string",
        "object_uuid": "string",
        "labels": [
          "string"
        ],
        "location_name": "string",
        "status": "string",
        "location_uuid": "string",
        "change_time": "2018-08-28T08:15:36Z",
        "name": "string"
      },
      "property2": {
        "location_country": "string",
        "relations": {
          "object1": [
            {}
          ]
        },
        "create_time": "2018-08-28T08:15:36Z",
        "location_iata": "string",
        "object_uuid": "string",
        "labels": [
          "string"
        ],
        "location_name": "string",
        "status": "string",
        "location_uuid": "string",
        "change_time": "2018-08-28T08:15:36Z",
        "name": "string"
      }
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|paas_security_zone|object|false|none|none|
|» **additionalProperties**|[PaasSecurityZoneBriefIndex](#schemapaassecurityzonebriefindex)|false|none|none|

<h2 id="tocSlinkedip">LinkedIp</h2>

<a id="schemalinkedip"></a>

```json
{
  "object_uuid": "string",
  "family": 4,
  "prefix": 0,
  "create_time": "2018-08-28T08:15:36Z",
  "ip": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|object_uuid|[object_uuid](#schemaobject_uuid)|false|none|none|
|family|integer|false|none|Either 4 or 6|
|prefix|integer|false|none|The prefix of the IP Address.|
|create_time|[create_time](#schemacreate_time)|false|none|none|
|ip|string|false|none|The IP Address (v4 or v6)|

#### Enumerated Values

|Property|Value|
|---|---|
|family|4|
|family|6|

<h2 id="tocSlinkedipbrief">LinkedIpBrief</h2>

<a id="schemalinkedipbrief"></a>

```json
{
  "object_uuid": "string",
  "family": 4,
  "prefix": 0,
  "create_time": "2018-08-28T08:15:36Z",
  "server_uuid": "string",
  "ip": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|object_uuid|[object_uuid](#schemaobject_uuid)|false|none|none|
|family|integer|false|none|Either 4 or 6|
|prefix|integer|false|none|The prefix of the IP Address.|
|create_time|[create_time](#schemacreate_time)|false|none|none|
|server_uuid|string(uuid)|false|none|The UUID of the server that this IP is attached to.|
|ip|string|false|none|The IP Address (v4 or v6)|

#### Enumerated Values

|Property|Value|
|---|---|
|family|4|
|family|6|

<h2 id="tocSlinkedipsgetresponse">LinkedIpsGetResponse</h2>

<a id="schemalinkedipsgetresponse"></a>

```json
{
  "ip_relations": [
    {
      "object_uuid": "string",
      "family": 4,
      "prefix": 0,
      "create_time": "2018-08-28T08:15:36Z",
      "server_uuid": "string",
      "ip": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|ip_relations|[[LinkedIpBrief](#schemalinkedipbrief)]|false|none|none|

<h2 id="tocSlinkedipgetresponse">LinkedIpGetResponse</h2>

<a id="schemalinkedipgetresponse"></a>

```json
{
  "ip_relation": {
    "object_uuid": "string",
    "family": 4,
    "prefix": 0,
    "create_time": "2018-08-28T08:15:36Z",
    "ip": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|ip_relation|[LinkedIp](#schemalinkedip)|false|none|none|

<h2 id="tocSlinkip">LinkIp</h2>

<a id="schemalinkip"></a>

```json
{
  "object_uuid": "77ddfb4a-5b50-430d-99bf-4c4dec1e8d0b"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|object_uuid|string(uuid)|false|none|none|

<h2 id="tocSlinkedstorage">LinkedStorage</h2>

<a id="schemalinkedstorage"></a>

```json
{
  "storage_type": "string",
  "target": 0,
  "bus": 0,
  "capacity": 0,
  "license_product_no": 0,
  "object_uuid": "string",
  "controller": 0,
  "lun": 0,
  "create_time": "2018-08-28T08:15:36Z",
  "last_used_template": "string",
  "bootdevice": true,
  "object_name": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|storage_type|string|false|none|Indicates the speed of the storage. This may be (storage, storage_high or storage_insane).|
|target|integer|false|none|Defines the SCSI target ID. The SCSI defines transmission routes like Serial Attached SCSI (SAS), Fibre Channel and iSCSI. The target ID is a device (e.g. disk).|
|bus|integer|false|none|The SCSI bus id. The SCSI defines transmission routes like Serial Attached SCSI (SAS), Fibre Channel and iSCSI. Each SCSI device is addressed via a specific number. Each SCSI bus can have multiple SCSI devices connected to it.|
|capacity|integer|false|none|The capacity of a storage/ISO-Image/template/snapshot in GB.|
|license_product_no|integer|false|none|If a template has been used that requires a license key (e.g. Windows Servers) this shows the product_no of the license (see the /prices endpoint for more details).|
|object_uuid|[object_uuid](#schemaobject_uuid)|false|none|none|
|controller|integer|false|none|Defines the SCSI controller id. The SCSI defines transmission routes such as Serial Attached SCSI (SAS), Fibre Channel and iSCSI.|
|lun|integer|false|none|Is the common SCSI abbreviation of the Logical Unit Number. A lun is a unique identifier for a single disk or a composite of disks.|
|create_time|[create_time](#schemacreate_time)|false|none|none|
|last_used_template|string(uuid)|false|none|Indicates the UUID of the last used template on this storage (inherited from snapshots).|
|bootdevice|boolean|false|none|Defines if this object is the bootdevice. Storages, Networks and ISO-Images can have a bootdevice configured, but only one bootdevice per Storage, Network or ISO-Image. The boot order is as follows => Network > ISO-Image > Storage.|
|object_name|[name](#schemaname)|false|none|none|

<h2 id="tocSlinkedstoragebrief">LinkedStorageBrief</h2>

<a id="schemalinkedstoragebrief"></a>

```json
{
  "storage_type": "string",
  "target": 0,
  "bus": 0,
  "capacity": 0,
  "license_product_no": 0,
  "object_uuid": "string",
  "controller": 0,
  "lun": 0,
  "create_time": "2018-08-28T08:15:36Z",
  "server_uuid": "string",
  "last_used_template": "string",
  "bootdevice": true,
  "object_name": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|storage_type|string|false|none|Indicates the speed of the storage. This may be (storage, storage_high or storage_insane).|
|target|integer|false|none|Defines the SCSI target ID. The SCSI defines transmission routes like Serial Attached SCSI (SAS), Fibre Channel and iSCSI. The target ID is a device (e.g. disk).|
|bus|integer|false|none|The SCSI bus id. The SCSI defines transmission routes like Serial Attached SCSI (SAS), Fibre Channel and iSCSI. Each SCSI device is addressed via a specific number. Each SCSI bus can have multiple SCSI devices connected to it.|
|capacity|integer|false|none|The capacity of a storage/ISO-Image/template/snapshot in GB.|
|license_product_no|integer|false|none|If a template has been used that requires a license key (e.g. Windows Servers) this shows the product_no of the license (see the /prices endpoint for more details).|
|object_uuid|[object_uuid](#schemaobject_uuid)|false|none|none|
|controller|integer|false|none|Defines the SCSI controller id. The SCSI defines transmission routes such as Serial Attached SCSI (SAS), Fibre Channel and iSCSI.|
|lun|integer|false|none|Is the common SCSI abbreviation of the Logical Unit Number. A lun is a unique identifier for a single disk or a composite of disks.|
|create_time|[create_time](#schemacreate_time)|false|none|none|
|server_uuid|string(uuid)|false|none|The same as the object_uuid|
|last_used_template|string(uuid)|false|none|Indicates the UUID of the last used template on this storage (inherited from snapshots).|
|bootdevice|boolean|false|none|Defines if this object is the bootdevice. Storages, Networks and ISO-Images can have a bootdevice configured, but only one bootdevice per Storage, Network or ISO-Image. The boot order is as follows => Network > ISO-Image > Storage.|
|object_name|[name](#schemaname)|false|none|none|

<h2 id="tocSlinkedstoragesgetresponse">LinkedStoragesGetResponse</h2>

<a id="schemalinkedstoragesgetresponse"></a>

```json
{
  "storage_relations": [
    {
      "storage_type": "string",
      "target": 0,
      "bus": 0,
      "capacity": 0,
      "license_product_no": 0,
      "object_uuid": "string",
      "controller": 0,
      "lun": 0,
      "create_time": "2018-08-28T08:15:36Z",
      "server_uuid": "string",
      "last_used_template": "string",
      "bootdevice": true,
      "object_name": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|storage_relations|[[LinkedStorageBrief](#schemalinkedstoragebrief)]|false|none|none|

<h2 id="tocSlinkedstoragegetresponse">LinkedStorageGetResponse</h2>

<a id="schemalinkedstoragegetresponse"></a>

```json
{
  "storage_relation": {
    "storage_type": "string",
    "target": 0,
    "bus": 0,
    "capacity": 0,
    "license_product_no": 0,
    "object_uuid": "string",
    "controller": 0,
    "lun": 0,
    "create_time": "2018-08-28T08:15:36Z",
    "last_used_template": "string",
    "bootdevice": true,
    "object_name": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|storage_relation|[LinkedStorage](#schemalinkedstorage)|false|none|none|

<h2 id="tocSlinkstorage">LinkStorage</h2>

<a id="schemalinkstorage"></a>

```json
{
  "object_uuid": "081b3a38-e4c0-419f-a7b3-58e3d9383fe5",
  "bootdevice": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|object_uuid|string(uuid)|true|none|The UUID of the storage you are requesting|
|bootdevice|boolean|false|none|Whether the server will boot from this storage device or not.|

<h2 id="tocSlinkedstorageupdate">LinkedStorageUpdate</h2>

<a id="schemalinkedstorageupdate"></a>

```json
{
  "bootdevice": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|ordering|integer|false|none|The ordering of the network interfaces. Lower numbers have lower PCI-IDs.|
|bootdevice|boolean|false|none|Whether the server boots from this network or not.|
|l3security|string|false|none|Defines information about IP prefix spoof protection (it allows source traffic only from the IPv4/IPv4 network prefixes). If empty, it allow no IPv4/IPv6 source traffic. If set to null, l3security is disabled (default).|

<h2 id="tocSlinkednetwork">LinkedNetwork</h2>

<a id="schemalinkednetwork"></a>

```json
{
  "network_type": "string",
  "l3security": [
    "string"
  ],
  "mcast": "string",
  "bootdevice": true,
  "network_uuid": "string",
  "l2security": "string",
  "vlan": "string",
  "mac": "string",
  "ordering": "string",
  "firewall": "string",
  "firewall_template_uuid": "string",
  "object_name": "string",
  "create_time": "2018-08-28T08:15:36Z",
  "object_uuid": "string",
  "public_net": true,
  "vxlan": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|network_type|string|false|none|(one of network, network_high, network_insane)|
|l3security|[string]|false|none|Defines information about IP prefix spoof protection (it allows source traffic only from the IPv4/IPv4 network prefixes). If empty, it allow no IPv4/IPv6 source traffic. If set to null, l3security is disabled (default).|
|mcast|string|false|none|none|
|bootdevice|boolean|false|none|Defines if this object is the bootdevice. Storages, Networks and ISO-Images can have a bootdevice configured, but only one bootdevice per Storage, Network or ISO-Image. The boot order is as follows => Network > ISO-Image > Storage.|
|network_uuid|string(uuid)|false|none|The UUID of the network you're requesting.|
|l2security|string|false|none|Defines information about MAC spoofing protection (filters layer2 and ARP traffic based on MAC source). It can only be (de-)activated on a private network - the public network always has l2security enabled. It will be true if the network is public, and false if the network is private.|
|vlan|string|false|none|none|
|mac|string|false|none|network_mac defines the MAC address of the network interface.|
|ordering|string|false|none|Defines the ordering of the network interfaces. Lower numbers have lower PCI-IDs.|
|firewall|string|false|none|none|
|firewall_template_uuid|string(uuid)|false|none|none|
|object_name|[name](#schemaname)|false|none|none|
|create_time|[create_time](#schemacreate_time)|false|none|none|
|object_uuid|[object_uuid](#schemaobject_uuid)|false|none|none|
|public_net|boolean|false|none|True if the network is public. If private it will be false. Each private network is a secure and fully transparent 2-Layer network between servers. There is no limit on how many servers can be connected to the same private network.|
|vxlan|string|false|none|none|

<h2 id="tocSlinkednetworkbrief">LinkedNetworkBrief</h2>

<a id="schemalinkednetworkbrief"></a>

```json
{
  "network_type": "string",
  "l3security": [
    "string"
  ],
  "mcast": "string",
  "bootdevice": true,
  "network_uuid": "string",
  "l2security": "string",
  "vlan": "string",
  "server_uuid": "string",
  "mac": "string",
  "ordering": "string",
  "firewall": "string",
  "firewall_template_uuid": "string",
  "object_name": "string",
  "create_time": "2018-08-28T08:15:36Z",
  "object_uuid": "string",
  "public_net": true,
  "vxlan": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|network_type|string|false|none|(one of network, network_high, network_insane)|
|l3security|[string]|false|none|Defines information about IP prefix spoof protection (it allows source traffic only from the IPv4/IPv4 network prefixes). If empty, it allow no IPv4/IPv6 source traffic. If set to null, l3security is disabled (default).|
|mcast|string|false|none|none|
|bootdevice|boolean|false|none|Defines if this object is the bootdevice. Storages, Networks and ISO-Images can have a bootdevice configured, but only one bootdevice per Storage, Network or ISO-Image. The boot order is as follows => Network > ISO-Image > Storage.|
|network_uuid|string(uuid)|false|none|The UUID of the network you're requesting.|
|l2security|string|false|none|Defines information about MAC spoofing protection (filters layer2 and ARP traffic based on MAC source). It can only be (de-)activated on a private network - the public network always has l2security enabled. It will be true if the network is public, and false if the network is private.|
|vlan|string|false|none|none|
|server_uuid|string(uuid)|false|none|The UUID of the network you're requesting.|
|mac|string|false|none|network_mac defines the MAC address of the network interface.|
|ordering|string|false|none|Defines the ordering of the network interfaces. Lower numbers have lower PCI-IDs.|
|firewall|string|false|none|none|
|firewall_template_uuid|string(uuid)|false|none|none|
|object_name|[name](#schemaname)|false|none|none|
|create_time|[create_time](#schemacreate_time)|false|none|none|
|object_uuid|[object_uuid](#schemaobject_uuid)|false|none|none|
|public_net|boolean|false|none|True if the network is public. If private it will be false. Each private network is a secure and fully transparent 2-Layer network between servers. There is no limit on how many servers can be connected to the same private network.|
|vxlan|string|false|none|none|

<h2 id="tocSlinkednetworksgetresponse">LinkedNetworksGetResponse</h2>

<a id="schemalinkednetworksgetresponse"></a>

```json
{
  "network_relations": [
    {
      "network_type": "string",
      "l3security": [
        "string"
      ],
      "mcast": "string",
      "bootdevice": true,
      "network_uuid": "string",
      "l2security": "string",
      "vlan": "string",
      "server_uuid": "string",
      "mac": "string",
      "ordering": "string",
      "firewall": "string",
      "firewall_template_uuid": "string",
      "object_name": "string",
      "create_time": "2018-08-28T08:15:36Z",
      "object_uuid": "string",
      "public_net": true,
      "vxlan": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|network_relations|[[LinkedNetworkBrief](#schemalinkednetworkbrief)]|false|none|none|

<h2 id="tocSlinkednetworkgetresponse">LinkedNetworkGetResponse</h2>

<a id="schemalinkednetworkgetresponse"></a>

```json
{
  "network_relation": {
    "network_type": "string",
    "l3security": [
      "string"
    ],
    "mcast": "string",
    "bootdevice": true,
    "network_uuid": "string",
    "l2security": "string",
    "vlan": "string",
    "mac": "string",
    "ordering": "string",
    "firewall": "string",
    "firewall_template_uuid": "string",
    "object_name": "string",
    "create_time": "2018-08-28T08:15:36Z",
    "object_uuid": "string",
    "public_net": true,
    "vxlan": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|network_relation|[LinkedNetwork](#schemalinkednetwork)|false|none|none|

<h2 id="tocSlinknetwork">LinkNetwork</h2>

<a id="schemalinknetwork"></a>

```json
{
  "object_uuid": "e753aa01-7f99-4325-9724-625c78e741b0"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|object_uuid|string(uuid)|false|none|none|

<h2 id="tocSlinkednetworkupdate">LinkedNetworkUpdate</h2>

<a id="schemalinkednetworkupdate"></a>

```json
{
  "ordering": 3,
  "bootdevice": false,
  "l3security": null
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|ordering|integer|false|none|The ordering of the network interfaces. Lower numbers have lower PCI-IDs.|
|bootdevice|boolean|false|none|Whether the server boots from this network or not.|
|l3security|string|false|none|Defines information about IP prefix spoof protection (it allows source traffic only from the IPv4/IPv4 network prefixes). If empty, it allow no IPv4/IPv6 source traffic. If set to null, l3security is disabled (default).|

<h2 id="tocSlinkedisoimage">LinkedIsoimage</h2>

<a id="schemalinkedisoimage"></a>

```json
{
  "bootdevice": true,
  "object_name": "string",
  "create_time": "2018-08-28T08:15:36Z",
  "object_uuid": "string",
  "private": "2018-08-28T08:15:36Z",
  "server_uuid": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|bootdevice|boolean|false|none|Whether the server boots from this iso image or not.|
|object_name|[name](#schemaname)|false|none|none|
|create_time|[create_time](#schemacreate_time)|false|none|none|
|object_uuid|[object_uuid](#schemaobject_uuid)|false|none|none|
|private|string(date-time)|false|none|Whether the ISO-Image is private or not.|
|server_uuid|string(uuid)|false|none|The UUID of the server that holds this iso image.|

<h2 id="tocSlinkedisoimagebrief">LinkedIsoimageBrief</h2>

<a id="schemalinkedisoimagebrief"></a>

```json
{
  "bootdevice": true,
  "object_name": "string",
  "create_time": "2018-08-28T08:15:36Z",
  "object_uuid": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|bootdevice|boolean|false|none|Whether the server boots from this iso image or not.|
|object_name|[name](#schemaname)|false|none|none|
|create_time|[create_time](#schemacreate_time)|false|none|none|
|object_uuid|[object_uuid](#schemaobject_uuid)|false|none|none|

<h2 id="tocSlinkedisoimagesgetresponse">LinkedIsoimagesGetResponse</h2>

<a id="schemalinkedisoimagesgetresponse"></a>

```json
{
  "network_relations": [
    {
      "bootdevice": true,
      "object_name": "string",
      "create_time": "2018-08-28T08:15:36Z",
      "object_uuid": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|network_relations|[[LinkedIsoimageBrief](#schemalinkedisoimagebrief)]|false|none|none|

<h2 id="tocSlinkedisoimagegetresponse">LinkedIsoimageGetResponse</h2>

<a id="schemalinkedisoimagegetresponse"></a>

```json
{
  "network_relation": {
    "bootdevice": true,
    "object_name": "string",
    "create_time": "2018-08-28T08:15:36Z",
    "object_uuid": "string",
    "private": "2018-08-28T08:15:36Z",
    "server_uuid": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|network_relation|[LinkedIsoimage](#schemalinkedisoimage)|false|none|none|

<h2 id="tocSlinkisoimage">LinkIsoimage</h2>

<a id="schemalinkisoimage"></a>

```json
{
  "object_uuid": "22f06c53-27a1-482f-94ed-1e464d259adf"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|object_uuid|string(uuid)|true|none|The UUID of the storage you are requesting|

<h2 id="tocSlinkedisoimageupdate">LinkedIsoimageUpdate</h2>

<a id="schemalinkedisoimageupdate"></a>

```json
{
  "bootdevice": false,
  "name": "update name"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|bootdevice|boolean|false|none|none|
|name|string|false|none|none|

<h2 id="tocSobject_uuid">object_uuid</h2>

<a id="schemaobject_uuid"></a>

```json
"string"

```

*The UUID of an object is always unique, and refers to a specific object.*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string(uuid)|false|none|The UUID of an object is always unique, and refers to a specific object.|

<h2 id="tocSname">name</h2>

<a id="schemaname"></a>

```json
"string"

```

*The human-readable name of the object. It supports the full UTF-8 charset, with a maximum of 64 characters.*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|The human-readable name of the object. It supports the full UTF-8 charset, with a maximum of 64 characters.|

<h2 id="tocSlabels">labels</h2>

<a id="schemalabels"></a>

```json
[
  "string"
]

```

*list of labels*

### Properties

*None*

<h2 id="tocScreate_time">create_time</h2>

<a id="schemacreate_time"></a>

```json
"2018-08-28T08:15:36Z"

```

*Defines the date and time the object was initially created.*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string(date-time)|false|none|Defines the date and time the object was initially created.|

<h2 id="tocSchange_time">change_time</h2>

<a id="schemachange_time"></a>

```json
"2018-08-28T08:15:36Z"

```

*Defines the date and time of the last object change.*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string(date-time)|false|none|Defines the date and time of the last object change.|

<h2 id="tocSlocation_uuid">location_uuid</h2>

<a id="schemalocation_uuid"></a>

```json
"string"

```

*Helps to identify which datacenter an object belongs to.*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string(uuid)|false|none|Helps to identify which datacenter an object belongs to.|

<h2 id="tocSlocation_name">location_name</h2>

<a id="schemalocation_name"></a>

```json
"string"

```

*The human-readable name of the location. It supports the full UTF-8 charset, with a maximum of 64 characters.*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string(uuid)|false|none|The human-readable name of the location. It supports the full UTF-8 charset, with a maximum of 64 characters.|

<h2 id="tocSlocation_country">location_country</h2>

<a id="schemalocation_country"></a>

```json
"string"

```

*Formatted by the 2 digit country code (ISO 3166-2) of the host country.*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string(uuid)|false|none|Formatted by the 2 digit country code (ISO 3166-2) of the host country.|

<h2 id="tocSlocation_iata">location_iata</h2>

<a id="schemalocation_iata"></a>

```json
"string"

```

*Uses IATA airport code, which works as a location identifier.*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string(uuid)|false|none|Uses IATA airport code, which works as a location identifier.|

<h2 id="tocSstatus">status</h2>

<a id="schemastatus"></a>

```json
"string"

```

*status indicates the status of the object.*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|status indicates the status of the object.|

<h2 id="tocScurrent_price">current_price</h2>

<a id="schemacurrent_price"></a>

```json
0

```

*The price for the current period since the last bill.*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|integer(float)|false|none|The price for the current period since the last bill.|

<h2 id="tocSusage_in_minutes">usage_in_minutes</h2>

<a id="schemausage_in_minutes"></a>

```json
0

```

*Total minutes the object has been running.*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|integer|false|none|Total minutes the object has been running.|

