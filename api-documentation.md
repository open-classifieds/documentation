---
layout: page
title:  API Documentation for classifieds
date:   2015-05-21
categories: HowTo
tags: api,development
permalink: /api-documentation/
---
# API V1 Documentation
_Note: If you are using Open Classifieds you need at least version 2.5.0_

# WORK IN PROGRESS
Available for OC 2.5.0

----------
<!-- MarkdownTOC -->

- [About](#about)
    - [REST](#rest)
    - [Routes](#routes)
    - [Output](#output)
    - [Result filtering, sorting & searching](#result-filtering-sorting--searching)
    - [Issues and bug reports](#issues-and-bug-reports)
- [Authentication](#authentication)
    - [API Key of your installation](#api-key-of-your-installation)
    - [User API Token](#user-api-token)
- [Public Resources](#public-resources)
    - [Categories](#categories)
    - [Locations](#locations)
    - [Get all Custom fields ads](#get-all-custom-fields-ads)
    - [Get all Custom fields users](#get-all-custom-fields-users)
- [Authenticated by API Key Resources](#authenticated-by-api-key-resources)
    - [Login User](#login-user)
    - [Listings](#listings)
    - [User info](#user-info)
- [Authenticated by User Key Resources](#authenticated-by-user-key-resources)
    - [Profile](#profile)
    - [Advertisememt](#advertisememt)
    - [Favorites](#favorites)
    - [Messages](#messages)

<!-- /MarkdownTOC -->



## About

This is the official API Documentation for Yclas and Open Classifieds. With this API you will be able to extend the usage of your site, for example with native iOS and Android APPS. Only available for Open Classifieds 2.5.0 and all Yclas installations.

Contact us if you are interested to purchase the native mobile APPS [here](http://open-classifieds.com/contact).


### REST
This API uses REST as principle. Allowed methods are GET,POST, PUT and DELETE.

Best practices and inspiration by [Vinay](http://www.vinaysahni.com/best-practices-for-a-pragmatic-restful-api) and [Simon](http://simonguest.com/2013/07/05/designing-a-web-api-for-mobile-apps/). Used [kohana-restful-api](https://github.com/SupersonicAds/kohana-restful-api) as code base.


### Routes

We use routes similar to a crud system but they are mapped to actions internally.

Base route:
`/api/v1/<controller>(/<action>(/<id>))(.<format>`
 
Parameters between () are optional.

Example:
    `PUT /api/v1/categories/update/3`

Is the same as:
    `PUT /api/v1/categories/3`

Mapping of actions:

- GET => index 
- PUT => update 
- POST => create 
- DELETE => delete

In case you do not specify an action and you are using and ID, we swap the values internally.

### Output
The API supports different outputs. By default all will be returned as JSON but other outputs are available such:

- JSON
- CSV
- XML
- HTML

Example of usage:

- `GET /api/v1/categories/3.xml` get category 3 data as XML
- `GET /api/v1/categories/3.json` get category 3 data as JSON
- `GET /api/v1/categories/3` get category 3 data as JSON
- `GET /api/v1/category.csv` get all categories as CSV

### Result filtering, sorting & searching
This are sent as parameter (Post or Query) to the endpoint.

#### Filter
You can pass any field we indicate in the documentation, ex:

`GET /api/v1/category?id_category_parent=1&has_image=1`
This gets the categories that the parent is = 1 and have image.

Allowed operators `>=` (greater or equal), `<=` (less or equal), `!=` (different than) and `__between`.

To user the operator `__between` the value needs to be comma separated, and the field needs to get appended `__between` ex:
`GET /api/v1/listing?price__between=100,303`

This will filter ads with field `price` bigger or equal than 100 and smaller or equal to 303.

#### Sorting
Sorting: Similar to filtering, a generic parameter sort can be used to describe sorting rules. The sort parameter takes in list of comma separated fields, each with a possible unary negative to imply descending sort order. 
Let's look at some examples:

- `GET /api/v1/listing?sort=-published` - Retrieves a list of tickets in descending published date
- `GET /api/v1/listing?sort=-published,title` - Retrieves a list of ads in descending order of published date and by title of the add

#### Searching
Besides filtering on some endpoints you will be allowed to make a search using the `q` parameter.

`GET /api/v1/listing?q=something+to+search`

#### Pagination
You can paginate any result by using the params page (number of page) and items_per_page (elements to display).

`GET /api/v1/listing?q=something+to+search&page=3&items_per_page=10`

We return `X-Total-Count` header with the total amount of elements found and a header `link` with next,prev,last,first links.


#### Limiting fields returned
Limiting which fields are returned by the API

`GET /api/v1/listing?fields=id,subject,customer_name,updated_at&state=open&sort=-updated_at`


**Remember: You can use all this parameters together!**

`GET /api/v1/listing?q=something+to+search&status>=1&id_category=77&sort=-title,price&page=3&items_per_page=10`


### Issues and bug reports

Please use [GitHub](https://github.com/open-classifieds/openclassifieds2/issues/new) to report any issue you may face.

----------

## Authentication

This API uses 3 different kind of endpoints. 2 are authenticated and 1 does not require any kind.

**We highly recommend usage of HTTPS to make all the request encripted and more safe**

### API Key of your installation

In order to use some api endpoint you will be required to have an API Key of your site.

To get it:
- Login at your classifieds site
- Paste in your browser  `/oc-panel/Config/update/api_key`
- Copy the config_value

That's your api_key for your site to use in further requests.


### User API Token


----------

## Public Resources

This API endpoints do not require any kind of authentication, therefore are public.

### Categories
Retrieve all the categories.
`GET /api/v1/cateories`

Get single category info.
This includes all the fields of the category + siblings and parents of the category + custom fields ads.
`GET /api/v1/cateories/3`

### Locations
Retrieve all the locations.
`GET /api/v1/locations`

Get single location info
This includes all the fields of the location + siblings and parents of the location .
`GET /api/v1/locations/3`

### Get all Custom fields ads
This is meta information regarding extra fields for the advertisememt.
`GET /api/v1/customfields/ads`

### Get all Custom fields users
This is meta information regarding extra fields for the user.
`GET /api/v1/customfields/users`

----------

## Authenticated by API Key Resources

To use this resources/endpoints you will need a an API Key that you get [here](#authentication).

We use the parameter `apikey` to send this information.

### Login User

Using this method we will get an Auth Key for hte user to perform other actions on the API.
#### End Point

`GET /api/v1/auth`

#### Query Params

- email
- password
- apikey

#### Example

`GET /api/v1/auth?email=someemail@gmail.com&password=1234&apikey=SsrLIhDSmXjCHmp9SsrLIhDSmXjCHmp9`

#### Result

We return a user_token that we will use all the authenticated api request based on this on user_token. Store it somewhere safe.
`{"user_token":"06f8bbb8c7da102e5decf0820fb0d6c0b282d637"}`

In case user not found, or not apikey provided we will returnt the correct message and HTTP status.
`{"code":401,"error":"Wrong Api Key"}`
`{"code":401,"error":"Wrong user name or password"}`

### Listings
This returns published ads.

DONE TODO DOCS
`GET /api/v1/listing?q=something+to+search&id_category=77&sort=-title,price&page=3&items_per_page=10`

Example, get published ads of user 5 in category 7, sorted by created date:
`GET /api/v1/listing?id_user=5&id_category=7&sort=-created`


Returns the info of an Ad, only if published.
`GET /api/v1/listing/3`

### User info
Public information of user.
`GET /api/v1/user/5`


----------

## Authenticated by User Key Resources

To use this resources/endpoints you will need a user token that you get [here](#authenticated-by-user-key-resources). 

This will identify the user for any request.

### Profile

**Edit Profile**
`PUT /api/v1/profile/5`

**Edit Profile Picture**
`PUT /api/v1/profile/picture/5`

### Advertisememt

**Post Advertisememt**
`POST /api/v1/ads`

**Edit Advertisement**
Edit ad number 5
`PUT /api/v1/ads/5`

**Delete Advertisement**
`DELETE /api/v1/ads/5`

### Favorites
**Get all Favorite Advertisememt**
`GET /api/v1/favorites`

**Favorite Advertisememt**
`POST /api/v1/favorites/5`

`DELETE /api/v1/favorites/5`

### Messages

**Get all Messages**
`GET /api/v1/messages`

**Message Advertisememt**
`POST /api/v1/messages/ad/5`

**Get Message Advertisememt**
`GET /api/v1/messages/ad/5`

**Message User**
`POST /api/v1/messages/user/3`

**Get Message User**
This will get the answers to a message thread
`GET /api/v1/messages/user/3`


