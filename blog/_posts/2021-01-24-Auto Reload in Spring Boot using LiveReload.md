---
layout: post
title: Auto Reload is Spring Boot using Dev Tools and Live-Reload
description: >
    Live Reload feature is used to reflect the changes on browser automatically on code change , this is a Huge Time Saver for any developer. In Spring boot to do that we use Spring dev tools. Internally its a web socket communication from web server to browser , for node js or javascript grant or gulp are present in order to perform live reload. 
categories: [devlog]
tags:       [Intellij,Spring,Productivity,Thymeleaf]
sitemap: false
image: /assets/DevToolsSpring/DevToolsCover.jpg
comments: true
---
0. this unordered seed list will be replaced by toc as unordered list
{:toc}

# Steps To Setup

### Dev Tools

Add the dependency spring-boot-devtools to your project’s build file i.e. Gradle or Maven 

```jsx
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-devtools</artifactId>
    <scope>runtime</scope>
    <optional>true</optional>
</dependency>
```

### Live Reload

Install LiveReload extension for your browser (Usually Chrome is preferred) 

1. go to app store [https://chrome.google.com/webstore/category/extensions](https://chrome.google.com/webstore/category/extensions)
2. select Live Reload and install and Enable it. 

    ![{{ site.baseurl }}/assets/DevToolsSpring/Untitled.png]({{ site.baseurl }}/assets/DevToolsSpring/Untitled.png)

3. Restart your Spring Boot application.

### Usage

1. Now on code change your code and on browser automatically things would start to reflect on Browser.

## Troubleshooting

Sometimes there are issues in case you are in Intellij

- Make sure to go to settings > Compiler > Build project Automatically
    - make sure that this checkbox is ticked.

![{{ site.baseurl }}/assets/DevToolsSpring/Untitled%201.png]({{ site.baseurl }}/assets/DevToolsSpring/Untitled%201.png)

- Double shift and go to registry
    - Search for compiler.automake.allow.when.app.running and mark it as "checked"

![{{ site.baseurl }}/assets/DevToolsSpring/Untitled%202.png]({{ site.baseurl }}/assets/DevToolsSpring/Untitled%202.png)

## Customizations

- Make sure if you are using Thymeleaf to switch caching off by adding following line in [application.properties](http://application.properties) file
    - Dev tools automatically does that , however in case you are facing the issue, do add it.

```jsx
spring.thymeleaf.cache=false
```

- add specific path , understand that this refers to the package from componentscan root folder
    - This will make sure that auto live reload runs only when you are working in these package

```jsx
spring.devtools.restart.additional-paths = /path_To_Folder
```

- Similarly to exclude any folder

```jsx
spring.devtools.exclude = /path_of_Excluded_Folder
```

- To Disable live-Reload , update following property in [application.properties](http://application.properties) file
    - Especially in the UAT or Prod environments
    - its always advisable to remove this dependency all together.

```jsx
spring.devtools.livereload.enabled=false
```

# Conclusion

Dev tools are very powerful developer tools that can not only help us in live Reload however also for "Remote Debug Tunneling" - for docker containers and "Remote Update and Restart" pushing changes to remote. 

# Additional Resources for Reference

1. [https://www.youtube.com/watch?v=_3uMgaAncmA](https://www.youtube.com/watch?v=_3uMgaAncmA)
2. [https://www.youtube.com/watch?v=Dpk-RUsZBug](https://www.youtube.com/watch?v=Dpk-RUsZBug)
3. [https://www.codejava.net/frameworks/spring-boot/spring-boot-auto-reload-changes-using-livereload-and-devtools](https://www.codejava.net/frameworks/spring-boot/spring-boot-auto-reload-changes-using-livereload-and-devtools)