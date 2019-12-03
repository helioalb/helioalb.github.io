---
layout: post
title:  "Express, extract params and querystring"
date:   2019-12-03 08:24:13 -0300
categories: software 
---

## Example

Suppose this uri: 

```
http://localhost:3000/travels/sao-paulo/londrina?startDate=2019-12-03&endDate=2019-12-04
```

and the follow route:

```javascript
router.get('/travels/:from/:to', (req, res, next) => {
  console.log('Params: ', req.params)
  console.log('Query Params', req.query)

  res.end()
})
```

The output:

```shell
Params:  { from: 'sao-paulo', to: 'londrina' }
Query Params { startDate: '2019-12-03', endDate: '2019-12-04' }
```
