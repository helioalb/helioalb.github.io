---
layout: post
title:  "Create user in Wordpress via database"
date:   2020-11-19 08:45:03 -0300
categories: software
---

Inside your database:

```sql
INSERT INTO wp_users
            ( ` id ` ,
             ` user_login ` ,
             ` user_pass ` ,
             ` user_nicename ` ,
             ` user_email ` ,
             ` user_url ` ,
             ` user_registered ` ,
             ` user_activation_key ` ,
             ` user_status ` ,
             ` display_name ` )
VALUES      ('4',
             'helio',
             MD5('mypassword'),
             'Helio Albano',
             'myemail@example.com',
             'http://www.test.com/',
             '2020-11-17 00:00:00',
             '',
             '0',
             'Helio Albano');

INSERT INTO wp_usermeta
            ( ` umeta_id ` ,
             ` user_id ` ,
             ` meta_key ` ,
             ` meta_value ` )
VALUES      (NULL,
             '4',
             'wp_capabilities',
             'a:1:{s:13:"administrator";s:1:"1";}');

INSERT INTO wp_usermeta
            ( ` umeta_id ` ,
             ` user_id ` ,
             ` meta_key ` ,
             ` meta_value ` )
VALUES      (NULL,
             '4',
             'wp_user_level',
             '10');
```
