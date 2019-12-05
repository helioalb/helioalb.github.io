---
layout: post
title:  "Mock-Server whith nodejs"
date:   2019-12-03 08:24:13 -0300
categories: software
---

In my last works, I have been worked integrations with partners and a common scenario is:

The partner provides documentation and a homologation endpoint. At this point, it is clear how to use the API and it is clear the desired response, but....

The homolog server doesn't work properly :( 

In this case, I have been used the [json-server](https://github.com/typicode/json-server) to make my fake homolog server.

A simple example of how it works:

Suppose that the end-point are `/users` and `/dogs`.

You just need to create a file, for example, `db.json` and put something like that:
```javascript
{
  "users": [
    {
      "id": 1,
      "name": "Ana"
    },
    {
      "id": 2,
      "name": "Helio"
    }
  ],
  "dogs": [
    {
      "id": 1,
      "name": "Dorothy"
    },
    {
      "id": 2,
      "name": "Bebel"
    }
  ]
}
```

Now, install the json-server

```shell
  npm install -g json-server
```

and run the follow command:

```javascript
  json-server -p 3002 --watch db.json
```


```shell
curl --request GET \
  --url http://localhost:3002/users
```

result:

```shell
[
  {
    "id": 1,
    "name": "Ana"
  },
  {
    "id": 2,
    "name": "Helio"
  }
]
```

```shell
curl --request GET \
  --url http://localhost:3002/users/1
```

result:

```shell
{
  "id": 1,
  "name": "Ana"
}
```

```shell
curl --request GET \
  --url http://localhost:3002/dogs/1
```

result:

```shell
{
  "id": 1,
  "name": "Dorothy"
}
```

But in real-world endpoints are not so simple.Suppose that instead `/users` the endpoint is `/api/v1/customers`.

You can make a rote file to address this problem. The file is something like that:

`routes.js`

```javascript
{
  "/api/v1/customers/:id": "/users/:id"
}
```

Start the server:

```shell
json-server -p 3002 --watch db.json --routes routes.json
```

```shell
curl --request GET \
  --url http://localhost:3002/api/v1/customers/1
```

result

```shell
{
  "id": 1,
  "name": "Ana"
}
```

The project has amazing documentation, it's worth checking out.
