GetAmplify SDK for PHP
======================

This SDK allows developers to easily use the GetAmplify API with PHP. This repository contains the open source PHP SDK that allows you to utilize the above on your website. 

You will need your API Key, API Secret and Project ID which you can find in your [Settings](http://getamplify.com/configurations/settings/api-key).

For more information - please refer [Docs](http://getamplify.com/learn/product-guide/) 

Introduction
------------

The GetAmplify PHP SDK provides a few simple ways to to send user events and set user properties.

Installation
------------

Copy the SDK library file to a location within your web application's include path, and include it into any scripts that you wish to make API calls from.

```php
include 'getamplify-sdk.php';
````

Usage
-----
Before calling any of the common methods you must create an instance of amplify class with valid API key, secret and project ID:

```php  
    $amplifyObject = new Amplify('API_Key','API_Secret','Project_Id');
````

1. Identifying a User
---------------------
Before calling any of the common methods you must create an instance of amplify class with valid API key, secret and project ID:

```php  
    $amplifyObject->identify('Email_Address','Name');
````

Example
```php  
    $amplifyObject->identify('sandeep@getamplify.com','Sandeep');
````

2. Sending an event
-------------------
Before calling any of the common methods you must create an instance of amplify class with valid API key, secret and project ID:

```php  
    $amplifyObject->event(
                    'Email_Address',
                     array(
                            'Event_Name' => array(
                                                    'Property_Name'=>'Property_Value',
                                                    'Property2_Name'=>'Property2_Value'
                                                )
                            )
                        );
````

Example
```php  
    $amplifyObject->event(
                    'sandeep@getamplify.com',
                     array(
                            'addtocart' => array(
                                                    'product'=>'Samsung Note2',
                                                    'category'=>'Mobile',
                                                    'price'=>'456.78'
                                                )
                            )
                        );
````

### Requirements
* PHP >= 5.2.0
* cURL
