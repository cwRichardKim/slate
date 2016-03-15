---
title: API Reference

language_tabs:
  - ruby

toc_footers:
  - <a href='https://incidentreport-120.herokuapp.com'>InstaPort Home</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the [InstaPort](https://incidentreport-120.herokuapp.com) API! You can use our API to access API endpoints, which can get information on incidents or users in our database.

We have language bindings in Ruby! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This API documentation page was created with [Slate](https://github.com/tripit/slate).

# Authentication

Our current MVP allows full access to all of the end points and thus does not require any Authentication.  We will update this section of the documents once our authentication component is complete.

# Incidents

## Get All Incidents

> The http request returns JSON structured like this:

```json
[
  {
    "id":1,
    "title":"Example",
    "location":"South Hall",
    "severity":1,
    "incident_type":"Housing",
    "comments":"Example comments",
    "user":"Demo User",
    "groups":"Students",
    "status":0,
    "reported_by":null,
    "assigned_to":null,
    "created_at":"2016-03-11T19:52:46.401Z",
    "updated_at":"2016-03-11T19:52:46.401Z"
  },
  {
    "id":2,
    "title":"Example 2",
    "location":"Lane Hall",
    "severity":2,
    "incident_type":"Health and Safety",
    "comments":"Example comments",
    "user":"Demo User",
    "groups":"Campus Police",
    "status":0,
    "reported_by":null,
    "assigned_to":null,
    "created_at":"2016-03-11T19:52:46.401Z",
    "updated_at":"2016-03-11T19:52:46.401Z"
  }
]
```

This endpoint retrieves all incidents.

### HTTP Request

`GET http://incidentreport-120.herokuapp.com/incidents.json`



## Get a Specific Incident

> The http request returns JSON structured like this:

```json
{
  "id":1,
  "title":"Example",
  "location":"South Hall",
  "severity":1,
  "incident_type":"Housing",
  "comments":"Example comments",
  "user":"Demo User",
  "groups":"Students",
  "status":0,
  "reported_by":null,
  "assigned_to":null,
  "created_at":"2016-03-11T19:52:46.401Z",
  "updated_at":"2016-03-11T19:52:46.401Z"
}
```

This endpoint retrieves a specific incident.


### HTTP Request

`GET http://incidentreport-120.herokuapp.com/incidents/<incident_id>.json`

### URL Parameters

Parameter | Description
--------- | -----------
incident_id | The ID of the incident to retrieve

## Edit a Specific Incident


> Sending an HTTP Form-Data PUTS to this endpoint with all the required fields will return json as follows
```json
{
  "id":1,
  "title":"Example",
  "location":"South Hall",
  "severity":1,
  "incident_type":"Housing",
  "comments":"Example comments",
  "user":"Demo User",
  "groups":"Students",
  "status":0,
  "reported_by":null,
  "assigned_to":null,
  "created_at":"2016-03-11T19:52:46.401Z",
  "updated_at":"2016-03-11T19:52:46.401Z"
}

This endpoint edits a specified incident.

### HTTP Request

`GET http://incidentreport-120.herokuapp.com/incidents/{incident id}.json`

### Form Data

Key | Value
--------- | -----------
incident[title] | string
incident[location] | string
incident[comments] | text
incident[severity] | integer between 1-4
incident[incident_type] | string
incident[groups] | string
_method | 'patch'

## Create a New Incident


> Sending an HTTP Form-Data POST to this endpoint with all the required fields will return json as follows
```json
{
  "id":1,
  "title":"Example",
  "location":"South Hall",
  "severity":1,
  "incident_type":"Housing",
  "comments":"Example comments",
  "user":"Demo User",
  "groups":"Students",
  "status":0,
  "reported_by":null,
  "assigned_to":null,
  "created_at":"2016-03-11T19:52:46.401Z",
  "updated_at":"2016-03-11T19:52:46.401Z"
}
```

This endpoint creates a new incident.


### HTTP Request

`GET http://incidentreport-120.herokuapp.com/incidents.json`

### Form Data

Key | Value
--------- | -----------
incident[title] | string
incident[location] | string
incident[comments] | text
incident[severity] | integer between 1-4
incident[incident_type] | string
incident[groups] | string


# Users

## Create a New User

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "first_name": "Max",
  "last_name": "Maxerson",
  "email": "email@email.com",
  "phone": "(555)555-5555",
  "group": "Chemistry Department",
  "created_at": DateTime,
  "updated_at": DateTime
}
```

This endpoint creates a new User.

### HTTP Request

`POST http://incidentreport-120.herokuapp.com/users.json`

### URL Parameters

Parameter | Description
--------- | -----------
user[first_name]* | string (limit: 60)
user[last_name]* | string (limit: 60)
user[password]* | string (limit: 255)
user[email]* | string (limit: 255)
user[phone]* | string (limit: 15)
user[group]* | string (limit: 100)

\*Required (cannot be null)
