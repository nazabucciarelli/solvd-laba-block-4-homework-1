# 1st Homework of the Java Test Automation Course (4th block) - Solvd Laba
This repository stores the 1st homework given by our mentor in the 4th block of
the Java Test Automation Course at Solvd Laba. In this block we started to
learn about Test Automation itself. In this specific homework, we had to 
implement at least 4 API tests for the endpoints that https://dummyjson.com 
provides. These tests had to be done with response validations.

## Explanation

To accomplish the requirements of the homework, I've initialized a Carina
project and removed all the sample files excepting the config.properties file.

For each entity's API testing I did the following: 

In a package with a suitable name from src/main/java, I created classes that represent the APIs' methods.
For example, GetCartById. This class must extend from AbstractApiMethodV2.
In this API method, I had to use the annotations @Endpoint, @SuccessfulHttpStatus, @RequestTemplatePath(only for post or put).
In the @Endpoint annotation I had to set the url, with the placeholder ${config.api_url} and ${id} if needed. 
Then I've created a method to set the value of the id using the replaceUrlPlaceHolder() method.
After, I've created a class in src.test.java.com.solvd.dummy_api_test.api
to run each API method. Let’s name it APICartTest. This class must implement the IAbstractTest interface. 
After, I had to create methods with the @Test and @MethodOwner annotations. 
The methods' name must have the name of the API method and the “Test” postfix. 
Inside each method, I've created an instance of its suitable API method and called the setId method to replace the “id” placeholder from the url.
Finally, I've called the callAPIExpectSuccess method, to check the response format and, from it, I created a rs.schema file to validate this response.
First, I've created a “_get” folder in src.test.resources.api.carts to store the schema file there, and after that, 
I called the validateResponseAgainstSchema method and sent the relative path from the src.test.resources folder to the schema itself.

These steps I gave, are in general the same for each API test, but obviously
these steps are not the same as in a POST or PUT test, since in such cases we
additionally need to create a rq.json and a .properties file to give random
data to the requests.


## What did I learn?

In this homework I've learnt how to automate APIs' testing with the Carina 
framework.

## Technologies

- Java
- Carina Framework

## Set-Up

To run this project you will need at least the version 11 of Java.
First, clone this repository in a folder of your PC.
You have to put the following command in a terminal:

```bash
  git clone this-repo-url
```
You will need an IDE to open the project folder and also Maven, to download
all the necessary dependencies. Once you are with the project opened, you
can either run the whole tests' classes from the com.solvd.dummy_api_test.api 
package by pressing the green play button at class level or each method with 
the @Test annotation separately by pressing that button but at method level.

## Author

- [@Nazareno Bucciarelli](https://github.com/nazabucciarelli)