# Tailori3D API

Textronics Design System have created an interactive platform for bespoke clothing. Textronics Tailori API is a plugin that simplifies access to the functionality of textronics services.

# Features

To know more about features of TheGuide, continue reading our documentation and check our available components.     
It provides following features:

* [3D Element Rendering](#)  
  It allows you to render Product, Options & Features.   

* [Contrast Options](#)  
  Allows to apply contrast fabric on the product.

* [Monogram](#)  
  This feature allows to give Company Branding on Prouduct i.e, Company Name, Logo, etc.

* [Auto Specific view](#)  
  Provides Zoomed View of Specific Part of a Product i.e., Shirt Collar, Sleeves, etc.

* [Auto Alignment Change](#)  
  To View Back and Front Details.

* [Summary](#)  
  Provides Summary of your customised product and its details.

* [Save and load favourite look](#)  
  Allows user to Save and custom product look.

  [View online Demo](http://www.textronic.online/tailori)

__________________________________________________________________________________________________________________________________

# Documentation

## Tailori structure

In Tailori3D API first we have to know how Tailori work,first we need to know structure of Tailori.

##### Tailori structure hierarchy

<pre>
├──── Product
    |
    ├─── Detail
    |   |
    |   ├─── Options
    |   |   |
    |   |   └─── Features
    |   |
    |   └─── Contrasts
    |       |
    |       └─── Contrasts Features
    |
    ├──── MonogramPlacement
    │
    ├──── MonogramFont
    │
    └──── MonogramColor</pre>

## Plugin initialization

To create object of Plugin.

```js

var TailoriConfiguration = new Tailori.TailoriConfig({
  // plugin options
});

```

## Plugin options

## Plugin methods

## Plugin Callback methods
