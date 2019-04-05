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
| Props                                          | Description  | Required
| -----------------------------------------------|------------| -------:|
| ServiceUrl                                     | ServiceUrl is a url where we place all our data that we need to call, <br />For eg. product, draping parts, buttons, fabrics, etc. <br />**Provided by textronics.**  | * |
| Key                                    | Unique id generated when user logs in with given username and password <br>**Provided by textronics.** </br> | * |			
| DefaultProduct                                        | Product Name <br /> For eg. 'Product':'MEN-SHIRT'| * |
| ContainerId                                    | Image container Id where rendered 3D images are placed (i.e. id).<br />For eg. 'ContainerId': scene | * |
| Texture                                    | Set default texture id to render default texture.<br />For eg. 'Texture': 7144E49A5 | * |
| AutoSpecific                                   | If *true* Zoomed view of specific part is automatically rendered *else* not.|         |
| AutoAlignment                                  | Auto Alignment is the option for Front View and Back View.Boolean values "true" or "false" is used to change the view.<br />For eg. 'AutoAlignment':false, |         |

## Plugin methods
### `getDetails()`
##### Description
This method is returning the details of current product
##### Required parameters
No parameters Required

##### Example
```js
  TailoriConfiguration.getDetails();
```
------------------------------------------------
### `getOptions()`
##### Description
This method is returning the options of current details
##### Required parameters
| parameters  | Type  | Description                                      |
|-------------|-------|--------------------------------------------------|
| Detail Id | string  | Pass the detail id which you want to get options |

##### Example
```js
  TailoriConfiguration.getOptions(DetailId);
```
------------------------------------------------
### `getFeatures()`
##### Description
This method is returning the features of current details or options
##### Required parameters
| parameters  | Type  | Description                                      |
|-------------|-------|--------------------------------------------------|
| Detail Id or Option Id | string  | If you want to get all options features then pass the detail id, or if you want to get particular options feature then pass options id |
| Type | boolean  | If you getting  feature using detail id then pass true, either pass false  |

##### Example
```js
  TailoriConfiguration.getFeatures(DetailId/OptionId,Type);
```
------------------------------------------------
### `getContrasts()`
##### Description
This method is returning the contrast of current details
##### Required parameters
| parameters  | Type  | Description                                      |
|-------------|-------|--------------------------------------------------|
| Detail Id/All | string  | Pass the detail id which you want to get contrasts, also if you want to get all contrast of product then pass All insted of detail id |

##### Example
```js
  TailoriConfiguration.getContrasts(DetailId/'All');
```
------------------------------------------------  

## Plugin Callback methods

## Example
