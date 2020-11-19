---
layout: post
title:  "AWS lambda + MySQL"
date:   2020-11-16 22:51:03 -0300
categories: software
---

# AWS lambda + MySQL

## Role

Create a role as `AWS service` -> `Lambda`. Give to it the `AWSLambdaVPCAccessExecutionRole` permission. Name this rolas as `lambda-vpc-role`.

## Create the project

`npm init`


## Install mysql2

`npm install mysql2 --save`

### db.js

```javascript
// db.js
async function connect(){
  if(global.connection && global.connection.state !== 'disconnected')
    return global.connection

  const { DB_HOST, DB_USER, DB_PASSWORD } = process.env

  const mysql = require('mysql2/promise')

  const connection = await mysql.createConnection({
    host: DB_HOST,
    user: DB_USER,
    password: DB_PASSWORD
  })

  global.connection = connection

  return connection
}

async function getUser(id){
  const conn = await connect()
  const [data] = await conn.query("SELECT * FROM users WHERE id=?", id)

  return data[0]
}

module.exports = {getUser}
```

### index.js

```javascript
// index.js

exports.handler = async (event) => {
  if (!isAuthorized(event)) return { statusCode: 403 }

  const db = require('./db')
  const user = await db.getUser(event.pathParameters.userId);

  if (!user.someImportantAttribute)
    return {
      statusCode: 404
    }

  return {
    statusCode: 200,
    body: JSON.stringify(user)
  }
}

function isAuthorized(event) {
  const { USER, PASSWORD } = process.env
  const credentials = event.headers.Authorization.split(' ')

  return credentials[0].toUpperCase() === 'BASIC' &&
    credentials[1] === Buffer.from(`${USER}:${PASSWORD}`).toString('base64')
}

```
