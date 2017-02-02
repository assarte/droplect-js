# Droplect.js - Bootstrap 3 dropdown-select component

Personally, I created this plugin as pure as possible to replace HTML `<select>` inputs in dropdown mode by Bootstrap 3 dropdown component in order to keep select's simplicity combined with formatting features of BS dropdown.

## Installation
You can just download the latest version from its GitHub repository at https://github.com/assarte/droplect-js or using composer:
```
composer install webapper/droplect.js
```

Ensure the files will be placed into your project's www document-root where remote user agents can access it!

----------
## Usage

You should include the JS and CSS files in your HTML ***after*** the place of where you included jQuery and Bootstrap:
```html
<link href="webapper/droplect-js/src/droplect.css" rel="stylesheet">
<script src="webapper/droplect-js/src/droplect.js"></script>
```
> **notice**: *you can customize the user-interface of droplect by customizing the basic BS3 dropdown component and/or overriding our basic droplect.css.*

### Single-selection mode

Droplect extends BS3 dropdowns by its new toggle mode `droplect` and it can map the selected value into an existing `<input>` by ID using `data-map-to` setting, the droplect will copy the selected item's value of `data-value` attribute (see `<li>` tags):

```html
 <div class="dropdown">
     <input type="hidden" id="tricky" name="my-no-more-selects">
     <button id="dLabel" type="button" class="btn btn-default btn-droplect" data-toggle="droplect" data-map-to="tricky" aria-haspopup="true" aria-expanded="false">
         Droplect trigger
         <span class="caret"></span>
     </button>
     <ul class="droplect dropdown-menu" aria-labelledby="dLabel">
         <li data-value="option-1"><a href="#">Action</a></li>
         <li data-value="option-2"><a href="#">Another action</a></li>
         <li data-value="option-3"><a href="#">Something else here</a></li>
         <li role="separator" class="divider"></li>
         <li data-value="option-4"><a href="#">Separated link</a></li>
     </ul>
 </div>
```
As long as it's a part of a `<form>` which can be sent, the droplect's value in our sample can be accessed by accessing the `my-no-more-selects` POST/GET request parameter.

### Multiple-selection mode
If you want to use a droplect in multi-selection mode you just need to add `data-multiple="multiple"` attribute setting into its button and leave it without any `data-map-to` as of multiple selection mapping should be managed by your hand, using an HTML solution to keep better consistency and flexibility of your markup.

In this sample code below we use checkbox inputs, you probably noticed that all the `data-value` attributes are used regardless the use of `value` attributes of `<input>` tags.
```html
<div class="dropdown">
	<button id="multisel-droplect" type="button" class="btn btn-default btn-droplect form-control" data-toggle="droplect" data-multiple="multiple" aria-haspopup="true" aria-expanded="false">Combine my options! <span class="caret"></span></button>
	<ul class="droplect dropdown-menu" aria-labelledby="multisel-droplect">
		<li class="dropdown-header">Choose something</li>
		<li data-value="option-1"><a href="#" class="checkbox"><label><input type="checkbox" name="multisel[]" value="option-1">Action</label></a></li>
		<li data-value="option-2"><a href="#" class="checkbox"><label><input type="checkbox" name="multisel[]" value="option-2">Another action</label></a></li>
		<li data-value="option-3"><a href="#" class="checkbox"><label><input type="checkbox" name="multisel[]" value="option-3">Something else here</label></a></li>
	    <li role="separator" class="divider"></li>
	    <li data-value="option-4"><a href="#" class="checkbox"><label><input type="checkbox" name="multisel[]" value="option-4">Separated link</label></a></li>
	</ul>
</div>
```

## Legal info
This component based on the original Bootstrap v3.3.7 dropdown.js, although I changed the most of it it's about time to credits for original dropdown's authors - thanks guys!

By the way I'm not much into legals and stuff I mention to my code under the terms of [WTFPL](http://www.wtfpl.net/).