---
layout: post
title: Debugging Like a Pro in Intellij
description: >
  Java Debugging Overview
categories: [devlog]
tags:       [Intellij, Debugging,devlog]
sitemap: false
---
0. this unordered seed list will be replaced by toc as unordered list
{:toc}

To start the Debugging Short cut : Shift + F9

# Inline Debugger

![{{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled.png]({{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled.png)

## Step over :

to run over the particular line , one statement at a time 

## **Step into** :

F7 : Steps into the particular method during debugging 

## **Force Step into** :

Alt +Shift + F7 : in case we want to step into java api methods or library methods 

## **Drop Frame** :

in case by mistake you went ahead from the required line , we can simply drop a frame and go back 

![{{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%201.png]({{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%201.png)

## **Show Execution Point** :

if you are going through code and miss where the code was execution point was during debugging , click on show Execution Point 

![{{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%202.png]({{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%202.png)

## **Run to Cursor** :

To avoid going line by line , we can directly click on this and go the particular line straight away 

![{{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%203.png]({{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%203.png)

---

# Variable Pane

- Shows the variables that are relevant to particular stack in Frame Section

![{{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%204.png]({{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%204.png)

## Watches

- To check the value of the variable in all the call stack , we can use watches
- Multiple ways to do it
    - drag drop variable from variables tab
    - right click on variable pane and click add to watches
    - or in watches section add '+'

![{{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%205.png]({{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%205.png)

## Evaluate Expression

To verify any assumptions , or test a particular statement(s) all together we can use Evaluate Expression 

![{{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%206.png]({{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%206.png)

---

# Modify code behavior without changing source

- in variable pane select the variable and right click and set value
- Behavior of the code changes

![{{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%207.png]({{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%207.png)

# Pause (when program seems stuck)

- if program gets stuck , one can click on PAUSE button

![{{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%208.png]({{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%208.png)

- See the call stack from the debugger tab (Frame Section )

![{{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%209.png]({{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%209.png)

- To Resume : use resume button
- To Rerun : use reRun button above Resume
- To Stop debugging your program : Stop button

---

# Break Point

- Add breakpoint in the gutter area

![{{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2010.png]({{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2010.png)

- Click on breakpoint to set conditions of when to execute

![{{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2011.png]({{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2011.png)

- We can Enable or Disable the particular break point

## More Features of Breakpoint

### Mute or Check all Break Point

![{{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2012.png]({{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2012.png)

### Log Rather than Suspend

- Right click on breakpoint and click on more
- rather than suspending the program we can log the breakpoint
- Note: color of such breakpoints will change

![{{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2013.png]({{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2013.png)

Output would be visible in the debug window 

![{{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2014.png]({{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2014.png)

### Group your Breakpoints

- Usually we want to group breakpoints for a particular purpose , this can be done in view all breakpoints then click on particular one to group it to respective groups.

![{{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2015.png]({{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2015.png)

### Change Breakpoint Description

- In the same screen while grouping , there is also option to 'edit Description' this allows user to provide custom information.

### Breakpoint on Interface (Method Breakpoint)

- When we use breakpoint on particular method on interface, it stops at whichever implementation gets hit
- there is change in breakpoint symbol (its a method breakpoint)

![{{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2016.png]({{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2016.png)

- We can specify when do we want to stop our breakpoint, method entry , exit or both

![{{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2017.png]({{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2017.png)

- hence we can also put breakpoints on interfaces like Runnable method 'run' . this would help to identify which method got called

### Field Breakpoint

- if we are checking for a particular field value , instead of checking all the methods that modify that particular field we can directly put the breakpoint on it.
- the symbol of breakpoint is updated here as shown below
- we can also select when it should trigger , while its 'accessed' , 'modified' or both

![{{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2018.png]({{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2018.png)

### Exception Breakpoint

- we can select particular exception and find exact where and when its thrown using this
- Select Java Exception Breakpoint

![{{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2019.png]({{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2019.png)

- Select you particular exception
- And hence we would be able to 'pause' before that exception is thrown , we can also see the values being passed in the editor pane

![{{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2020.png]({{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2020.png)

# Working with Lambdas

## Apply Breakpoint on Lambdas

- on Clicking set breakpoint , IDE will ask for which particular operation you want to apply debugger , we can select all , or particular lambda operator

![{{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2021.png]({{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2021.png)

- this would allow you to test particular expression inside a lambda

![{{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2022.png]({{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2022.png)

## Step into

- Press step into , this will highlight all the possible places in lambda where error can occur

![{{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2023.png]({{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2023.png)

- Select the particular value and then , keep pressing Step into to iterate through all the values

## Stream Debugger

- One can Debug the Streams much better using Stream debugger
- Just click the button , when you reach the particular point

![{{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2024.png]({{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2024.png)

- Check how it gets exactly converted

![{{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2025.png]({{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2025.png)

### Flat Mode

- Click on flat mode to check all the operations at once
- you can also select particular value to see the operations done on the particular one.

![{{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2026.png]({{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2026.png)

# Using Memory View

- we can track in memory how many times a particular call has been executed
    - if used wisely turns very helpful in finding the objects and instances in memory
- this can be done by using debugger memory view section
- Make sure the memory section has been enabled
- Load Classes

![{{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2027.png]({{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2027.png)

- Click on particular class , e.g. java.lang.String
- now check with 'equals' or any method to check the objects of that class

![{{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2028.png]({{ site.baseurl }}/assets/Debugging%20Your%20Code%20like%20a%20Pro%20in%20Intellij%20c146c5234603485896684e3e75ab4098/Untitled%2028.png)

# References

Debugging Basics Youtube Link from Intellij 

[https://www.youtube.com/watch?v=lAWnIP1S6UA](https://www.youtube.com/watch?v=lAWnIP1S6UA)

Advanced Debugging Features 

[https://www.youtube.com/watch?v=AOrnx-9zNBQ](https://www.youtube.com/watch?v=AOrnx-9zNBQ&list=PLPZy-hmwOdEXdOtXdFzyx_XCnrF_oD2Ft)