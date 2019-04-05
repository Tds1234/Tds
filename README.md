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
├──── Product (Men-Shirt,Men-Suit etc..)
    |
    ├─── Detail (Model,Cuff,Sleeves etc..)
    |   |
    |   ├─── Options (Rounded Cuff,Straight Cuff etc..)
    |   |   |
    |   |   └─── Features (Rounded Single Button Cuff,Rounded Double Button Cuff etc..)
    |   |
    |   └─── Contrasts Features (Full Contrast,Inside Cuff Contrast etc..)
    |           
    |
    ├──── MonogramPlacement (Collar,Pocket,Cuff etc..)
    │
    ├──── MonogramFont (Times new roman,Arial etc..)
    │
    └──── MonogramColor (29C5072[hex-value] etc..)</pre>

## Plugin initialization

1) Download plugin and add script

```html
<script src="js/tailori.js"></script>
```

2) To create object of Plugin.

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
This method is returning the options of current details.
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
This method is returning the features of current details or options.
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
This method is returning the contrast of current details.
##### Required parameters
| parameters  | Type  | Description                                      |
|-------------|-------|--------------------------------------------------|
| Detail Id/All | string  | Pass the detail id which you want to get contrasts, also if you want to get all contrast of product then pass All insted of detail id |

##### Example
```js
  TailoriConfiguration.getContrasts(DetailId/'All');
```
------------------------------------------------  
### `getMonogramPlacements()`
##### Description
This method is returning the monogram placement of current product.
##### Required parameters
No parameters Required

##### Example
```js
  TailoriConfiguration.getMonogramPlacements();
```
------------------------------------------------
### `getMonogramFonts()`
##### Description
This method is returning the monogram fonts of current product.
##### Required parameters
No parameters Required

##### Example
```js
  TailoriConfiguration.getMonogramFonts();
```
------------------------------------------------
### `getMonogramColors()`
##### Description
This method is returning the monogram colors of current product.
##### Required parameters
No parameters Required

##### Example
```js
  TailoriConfiguration.getMonogramColors();
```
------------------------------------------------
### `getAlignments()`
##### Description
This method is returning the alignments of current product.
##### Required parameters
No parameters Required

##### Example
```js
  TailoriConfiguration.getAlignments();
```
------------------------------------------------
### `getSummary()`
##### Description
This method is returning the summary of current select detail,option,feature and fabric.
##### Required parameters
No parameters Required

##### Example
```js
  TailoriConfiguration.getSummary();
```
------------------------------------------------
### `setFeature()`
##### Description
This method is used for changing the feature or loading the feature for customization.
##### Required parameters
| parameters  | Type  | Description                                      |
|-------------|-------|--------------------------------------------------|
| Feature Id | string  | simply pass the feature id which is you want to load or change |

##### Example
```js
  TailoriConfiguration.setFeature(FeatureId);
```
------------------------------------------------  
### `setTexture()`
##### Description
This method is used for rendering the whole object.
##### Required parameters
| parameters  | Type  | Description                                      |
|-------------|-------|--------------------------------------------------|
| Texture Id | string  | simply pass the Texture id which is you want render the object |

##### Example
```js
  TailoriConfiguration.setTexture(TextureId);
```
------------------------------------------------  
### `setLibConfigTexture()`
##### Description
This method is used for rendering the specific object.This method are used only for LibConfig option like Tie,Waistcoat etc.
##### Required parameters
| parameters  | Type  | Description                                      |
|-------------|-------|--------------------------------------------------|
| Texture Id | string  | simply pass the Texture id which is you want render the object |

##### Example
```js
  TailoriConfiguration.setLibConfigTexture(TextureId);
```
------------------------------------------------  
### `ChangeAlignmentTo()`
##### Description
This method is used for changing alignment of object.
##### Required parameters
| parameters  | Type  | Description                                      |
|-------------|-------|--------------------------------------------------|
| alignment | string  | pass the alignment name like face,back |

##### Example
```js
  TailoriConfiguration.ChangeAlignmentTo(Alignment);
```
------------------------------------------------
### `LoadProduct()`
##### Description
This method is used for changing current product to another product.
##### Required parameters
| parameters  | Type  | Description                                      |
|-------------|-------|--------------------------------------------------|
| Product name | string  | pass the product name which you want to change or load |

##### Example
```js
  TailoriConfiguration.LoadProduct(ProductName);
```
------------------------------------------------
### `ResetProduct()`
##### Description
This method is used for reset or reconfigure the product.
##### Required parameters
No parameters Required

##### Example
```js
  TailoriConfiguration.ResetProduct();
```
------------------------------------------------
### `ResetModal()`
##### Description
This method is used for reseting the position of 3DModel.
##### Required parameters
No parameters Required

##### Example
```js
  TailoriConfiguration.ResetModal();
```
------------------------------------------------
### `Zoom()`
##### Description
This method zooming in/out of 3DModel.
##### Required parameters
| parameters  | Type  | Description                                      |
|-------------|-------|--------------------------------------------------|
| Type | string  | pass 'in' for zoom in or 'out' for zoom out|

##### Example
```js
  TailoriConfiguration.Zoom(Type);
```
------------------------------------------------

## Plugin Callback methods
### `OnConfigLoad()`
##### Description
This method call when all configuration are load
##### Return values
No return values.

##### Example
```js
  TailoriConfiguration.OnConfigLoad = function(){
    // Logic..
  }
```
------------------------------------------------
### `OnObjectChange()`
##### Description
This method call when all configuration are load
##### Return values
| Return value  | Type  | Description                                      |
|-------------|-------|--------------------------------------------------|
| Feature Id | string  | returning current selected or change feature id|

##### Example
```js
  TailoriConfiguration.OnObjectChange = function(FeatureId){
    // Logic..
  }
```
------------------------------------------------
### `OnObjectLoad()`
##### Description
This method call when object/feature are load completed.
##### Return values
| Return value  | Type  | Description                                      |
|-------------|-------|--------------------------------------------------|
| Feature Id | string  | returning current selected or change feature id|

##### Example
```js
  TailoriConfiguration.OnObjectLoad = function(FeatureId){
    // Logic..
  }
```
------------------------------------------------
### `OnTextureChange()`
##### Description
This method call when texture are load.
##### Return values
| Return value  | Type  | Description                                      |
|-------------|-------|--------------------------------------------------|
| Texture Id | string  | returning current rendered texture id|

##### Example
```js
  TailoriConfiguration.OnTextureChange = function(FeatureId){
    // Logic..
  }
```
------------------------------------------------
### `OnFeatureChange()`
##### Description
This method call when feature are change.
##### Return values
| Return value  | Type  | Description                                      |
|-------------|-------|--------------------------------------------------|
| Detail Id | string  | returning current selected or change detail id|
| Feature Id | string  | returning current selected or change feature id|

##### Example
```js
  TailoriConfiguration.OnFeatureChange = function(DetailId,FeatureId){
    // Logic..
  }
```
------------------------------------------------
### `OnLibConfigChange()`
##### Description
This method call when you set libconfig feature (seperately draping feature).
##### Return values
| Return value  | Type  | Description                                      |
|-------------|-------|--------------------------------------------------|
| Detail Id | string  | returning current selected or change detail id|
| Feature Id | string  | returning current selected or change feature id|

##### Example
```js
  TailoriConfiguration.OnLibConfigChange = function(DetailId,FeatureId){
    // Logic..
  }
```
------------------------------------------------

## Example
Using Tailori3D Plugin

```js

var Tailoriconfig = new Tailori.TailoriConfig({
  ServiceUrl:"http://ip/WEBAPI3D",
  Key:"1234656",
  DefaultProduct:"Men-Shirt",
  ContainerId:"Scene",
  Texture: "7144E49A5",
  AutoAlignment: true,
  CursorZoom: true
});

Tailoriconfig.OnConfigLoad = function(){
  alert("All configuration load..");

  var Details = Tailoriconfig.getDetails();

};

$("#resetmodal").click(function(){
  Tailoriconfig.ResetModal();
});


```
