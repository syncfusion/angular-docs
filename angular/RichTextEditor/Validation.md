---
layout: post
title: Validation in RichTextEditor widget for Syncfusion Essential JS
description: Validation related changes in RichTextEditor widget
platform: angular
control: RTE
documentation: ug
keywords: RichTextEditor, Validation, Validation Rules, Validation Messages
api: /api/js/ejrte
---

# Validation 

You can validate the RichTextEditor’s value on form submission by applying [validationRules](https://help.syncfusion.com/api/js/ejrte#members:validationrules) and [validationMessage](https://help.syncfusion.com/api/js/ejrte#members:validationmessage) to the RichTextEditor.

N> [jquery.validate.min](http://cdn.syncfusion.com/js/assets/external/jquery.validate.min.js) script file should be referred for validation, for more details, refer [here](http://jqueryvalidation.org/documentation).

## jQuery Validation Methods

The following are jQuery validation methods.

_List of jQuery validation methods_

<table>
<tr>
<th>
Rules</th><th>
Description</th></tr>
<tr>
<td>
required</td><td>
 Requires value for the RichTextEditor control.</td></tr>
<tr>
<td>
minWordCount</td><td>
 Requires the value to be of given minimum words count.</td></tr>
<tr>
<td>
minlength</td><td>
 Requires the value to be of given minimum characters count.</td></tr>
<tr>
<td>
maxlength</td><td>
 Requires the value to be of given maximum characters count.</td></tr>
</table>

## Validation Rules

The validation rules help you to verify the content by adding validation attributes to the text area. This can be set by using [validationRules](https://help.syncfusion.com/api/js/ejrte#members:validationrules) property.


## Validation Messages 

You can set your own custom error message by using [validationMessage](https://help.syncfusion.com/api/js/ejrte#members:validationmessage) property. To display the error message, specify the corresponding annotation attribute followed by the message to display.


N> jQuery predefined error messages to that annotation attribute will be shown when this property is not defined. The below given example explain this behavior of ‘maxLength’ attribute,


When you initialize the RichTextEditor widget, it creates a text area hidden element which is used to store the value. Hence, the validation is performed based on the value stored in this hidden element.

Required field, `minlength`, maxlength, minWordCount and maxWordCount values validation is demonstrated in the below given example.


{% highlight html %}
<form id="form1">
<textarea id="rteSample" ej-rte width="100%" height="300px" [(value)]="content"  [validationRules]="validRule"  [validationMessage]="validMessage">
</textarea>
<div><br/>
<input type="submit" value="Validate">
 </div>
</form>
{% endhighlight %}

{% highlight ts %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'src/RTE/rte.component.html',
})
export class RTEComponent {
	  content: string;
	  validRule: any;
	validMessage: any;
  constructor() {
	  
	  $.validator.setDefaults({
        ignore: [],// To include hidden input validation.
        errorClass: 'e-validation-error', // to get the error message on jquery validation
        errorPlacement: function (error, element) {
            $(error).insertAfter(element.closest(".e-widget"));
        }
    });
	
      this.content = 'Description: The Rich Text Editor (RTE) control is an easy to render in client side. Customer easy to edit the contents and get the HTML content from RTE';
	  this.validRule={
  required: true,
  minlength: 15,
  maxlength: 150,
  minWordCount: 10,
  maxWordCount: 50,
};
this.validMessage={
  required: "Required RTE value",
  minWordCount: "Minimum word count not reached.",
  maxWordCount: "Maximum word count reached."
};
  }
}
{% endhighlight %}

![](Working-with-Content_images/Validation.png)