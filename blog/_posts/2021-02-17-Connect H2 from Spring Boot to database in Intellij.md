---
layout: post
title: Connect H2 from Spring Boot to  database in Intellij
description: >
    Intellij (Ultimate Only) has the Database connection option to add database connection , however while connecting in-memory database like H2 (here part of Spring Boot) often we get problem . 
categories: [devlog]
tags:       [Intellij,H2]
sitemap: false
image: /assets/ConnectH2toInteliijDb/cover.jpg
comments: true
---
0. this unordered seed list will be replaced by toc as unordered list
{:toc}

# Solution Steps

## Set up Application .properties file

- make sure that you have provided url and set ddl-auto to update

```jsx
spring.h2.console.enabled=true
server.port=9090
spring.datasource.url=jdbc:h2:./db/testDb;DB_CLOSE_ON_EXIT=FALSE;AUTO_SERVER=TRUE
spring.jpa.hibernate.ddl-auto=update
```

## Setup the Database

- Click on plus sign on Database tab (Usually situated on the right  side of the system)
    - Click datasource from url

![{{ site.baseurl }}/assets/ConnectH2toInteliijDb/Untitled.png]({{ site.baseurl }}/assets/ConnectH2toInteliijDb/Untitled.png)

- Update following data as following , update credentials as per your  usecase.

![{{ site.baseurl }}/assets/ConnectH2toInteliijDb/Untitled%201.png]({{ site.baseurl }}/assets/ConnectH2toInteliijDb/Untitled%201.png)

# Result

- Resulting would be that your  tables will be shown inside  'Public' , as shown below

![{{ site.baseurl }}/assets/ConnectH2toInteliijDb/Untitled%202.png]({{ site.baseurl }}/assets/ConnectH2toInteliijDb/Untitled%202.png)