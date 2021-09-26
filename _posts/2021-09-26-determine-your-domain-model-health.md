---
layout: post
title:  "Determine Your Domain Model Health"
date:   2021-09-26 04:45:03 -0300
categories: software ddd
---

From Vernon Vaughn's book "Implementing Domain-Driven Design"

|Yes/No|
|------|
|Does the software you call a "domain model" have mostly public getters and setters, and no business logic or almost none at all - you know, objects that are mostly attribute value holders?|
|Are the software components that frequently use your "domain model" the ones that house most of the business logic of your system, and do those heavily invoke the public getters and setters on the "domain model"? You probably call this particular client layer of the "domain model" a **Service Layer** ou **Application Layer**. If instead this describes your user interface, answer "Yes" to this question and write a thousand times on a whiteboard that you'll never, ever do that again.|
|**Hint: The correct answers are either "Yes" to both questions or "No" to both questions.**|
