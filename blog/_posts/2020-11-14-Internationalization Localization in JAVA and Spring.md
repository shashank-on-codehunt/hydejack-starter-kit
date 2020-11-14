---
layout: post
title: Internationalization and Localization in Spring and JAVA
description: >
  Guide to Server-Side programming for Internationalization and Localization 
categories: [devlog]
tags:       [Localization, Internationalization, Spring,POC,devlog]
sitemap: false
image: assets\Internationalization\InternationalizationCover.jpg
---
0. this unordered seed list will be replaced by toc as unordered list
{:toc}

# Localization vs. Internationalization

## Localization

Localization refers to the adaptation of a product, application or document content to meet the language, cultural and other requirements of a specific target market (a locale)

Localization is sometimes written in English as **l10n**

localization is often a substantially more complex issue. It can entail customization related to:

- umeric, date and time formats
- Use of currency
- Keyboard usage
- Collation and sorting
- Symbols, icons and colors
- Text and graphics containing references to objects, actions or ideas which, in a given culture, may be subject to misinterpretation or
viewed as insensitive.
- Varying legal requirements
- and many more things.

## Internationalization

Some people use other terms, such as **globalization**

Internationalization is the design and development of a product, application or document content that enables easy localization for target audiences that vary in culture, region, or language.

Internationalization is often written in English as **i18n**

Internationalization typically entails:

1. Designing and developing in a way that removes barriers to localization or international deployment.
    1. enabling the use of Unicode
    2. ensuring the proper handling of legacy character encodings where appropriate,
    3. taking care over the concatenation of strings
    4. avoiding dependence in code of user-interface string values
2. Providing support for features that may not be used until localization occurs
    1. adding markup in your **DTD** to support bidirectional text
    2. for identifying language
    3. adding to CSS support for vertical text or other non-Latin typographic features
3. Enabling code to support local, regional, language, or culturally related preferences
    1. include date and time formats
    2. local calendars
    3. number formats
    4. numeral systems
    5. sorting and presentation of lists
    6. handling of personal names and forms of address
4. Separating localizable elements from source code or content

## Basics of i18n in JAVA

Already present in java.util package 

## Locale class

Representing specific geographical , political and cultural region we plan to support 

## Resource Holding

In form of classes or properties holding Locale related information 

### Properties File

- Using properties file key value pair , this is [bundle.properties](http://bundle.properties)
- 'bundle' is the base name
- Handled by ***PropertyResourceBundle***

```
hello=Hello
welcome=Welcome to my app
ok=OK
cancel=Cancel
tryagain=Please try again
```

### using Java Class

```java
package res;
import java.util.ListResourceBundle;
public class Bundle extends ListResourceBundle {
    @Override
    protected Object[][] getContents() {
        return new Object[][] {
                {"hello", "Hello"},
                {"ourfeatures", new String[] {"Collaborative Translation", "Localization Workflow Management", "Localization Process Automation"}}
        };
    }
}
```

This approach is better for having more complex object type translations 

## ResourceBundle

class objects fetching data for relevant locales 

```java
Locale locale_ru_RU = new Locale("ru", "RU");
ResourceBundle resourceBundle = ResourceBundle.getBundle("res.bundle", locale_ru_RU);
System.out.println(resourceBundle.getString("welcome"));
```

## Rules to Follow

- All resources in common package
- All Share same Base-Name
- One with Base name should be default e.g.

```
[bundle.properties](http://bundle.properties) 
```

assuming 'bundle' is base name 

- Additional properties file must be named in this pattern

```
bundle_fr.properties 
```

- In case of language differs per country then we can have as follow

```
bundle_en_US.properties
bundle_en_UK.properties
```

- or we can also narrow down to additional variant

```
Bundle_th_TH_TH.java
```

---

# Web with Spring

## MessageSource

Spring developers created the MessageSource interface for internationalization purposes within Spring Boot applications

We will be using its ResourceBundleMessageSource implementation for our language resource resolving purposes, which relies on ResourceBundle hence the rules are same as discussed previously 

In Spring Boot Auto-configuration class 

```java
String basename = context.getEnvironment().getProperty("spring.messages.basename", "messages");
```

so by default it tries to pick up [message.properties](http://message.properties) 

In case you want to change the default name ,we can specify same in our [application.properties](http://application.properties) file 

```java
spring.messages.basename=lang/res
```

here we are saying inside lang we will have [res.properties](http://res.properties) as base 

## LocaleResolver

deals with locale resolution required when localizing web applications to specific locales.

There are 4 major Implementations 

### FixedLocaleResolver

Always resolves the singular Fixed language mentioned in properties file 

### AcceptHeaderLocaleResolver

Resolves the locale using an "accept-language' HTTP header retrieved from an HTTP Request 

### SessionLocaleResolver

Resolves the locale and Stores it in the HttpSession of the user. It is persisted as long as session is Alive 

### CookieLocaleResolver

Resolve the locale and Stores it in a cookie stored in user's machine 

```java
@Bean // <--- mark as spring bean 
public LocaleResolver localeResolver() {
    CookieLocaleResolver localeResolver = new CookieLocaleResolver(); // <---LocaleResolver is implemented using CookieLocaleResolver
    localeResolver.setDefaultLocale(Locale.US); // <--- in case no cookie is found
    return localeResolver;
}
```

now our Application knows how to resolve and Store locales. 

## LocaleChangeInterceptor

However we need an Interceptor that will check for each request for 'LocaleData' parameter on the HTTP Request. 

```java
@Bean
public LocaleChangeInterceptor localeChangeInterceptor() {
    LocaleChangeInterceptor localeChangeInterceptor = new LocaleChangeInterceptor();
    // Defaults to "locale" if not set
    localeChangeInterceptor.setParamName("localeData");

    return localeChangeInterceptor;
}
```

## InterceptorRegistry

Make Sure that you are in following Class 

```java
@SpringBootApplication
public class JavaI18nSpringBootApplication implements WebMvcConfigurer {..}
```

and update the InterceptorRegistry with the overridden method 

```java
@Override
public void addInterceptors(InterceptorRegistry interceptorRegistry) {
    interceptorRegistry.addInterceptor(localeChangeInterceptor());
}
```

# Practical Example from Github

[https://github.com/shashank-on-codehunt/SpringPOCs/tree/Internationalisation](https://github.com/shashank-on-codehunt/SpringPOCs/tree/Internationalisation)

# References

1. [https://www.w3.org/International/questions/qa-i18n](https://www.w3.org/International/questions/qa-i18n)
2.  [https://lokalise.com/blog/java-internationalization-learn-the-basics/](https://lokalise.com/blog/java-internationalization-learn-the-basics/)
3. [https://lokalise.com/blog/spring-boot-internationalization/](https://lokalise.com/blog/spring-boot-internationalization/)
4. [https://www.baeldung.com/spring-boot-characterencodingfilter](https://www.baeldung.com/spring-boot-characterencodingfilter)