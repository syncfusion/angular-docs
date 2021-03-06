---
layout: post
title: Globalization-Support
description: globalization support
platform: Angular
control: NumericTextbox
documentation: ug
---

# Globalization Support

**Globalization** is language support based on the culture in **NumericTextBox** . You can achieve the **Globalization** using “**locale”** property in **NumericTextBox** . 

The widget provides multi-language support using globalization. You can customize the NumericTextBox with your own language style by using this feature. You can change the globalization by using the **locale** property. The default value for **locale** property is **en-US** in NumericTextBox control. More than 350 culture specific files are available to localize the value.
 
 N> All the culture-specific script files are available within the below specified location, once you have installed Essential Studio in your machine, therefore it is not necessary to download these files explicitly.

<table>
<tr>
<td>

    '(installed location)\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets\scripts\i18n'
</td>
</tr>
<tr>
<td>
    For example, If you have installed the Essential Studio package within C:\Program Files (x86), then navigate to the below location, 
    C:\Program Files (x86)\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets\scripts\i18n

</td></tr>
</table>

Refer the below German culture file in head section of HTML page after the reference of **ej.web.all.min.js** file.

 {% highlight javascript %}
   
           <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/i18n/ej.culture.de-DE.min.js"></script>
                
 {% endhighlight %}


You can dynamically change the language based on their culture.

**Configure Globalization**

The following example describes the way to use Globalization for NumericTextBox widget.

{% highlight html %}

<input id="numeric" type="text" ej-numerictextbox [value]="value" [decimalPlaces]="decimalPlaces" [locale]="locale"/>
        
{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'src/numerictextbox/numerictextbox.component.html'
})
export class NumericTextboxComponent { 
    public value: number;
    public decimalPlaces: number;
    public locale: string;
    constructor() {
        this.value = 12345;
        this.decimalPlaces = 2;
        this.locale = "de-DE";
    }
}

{% endhighlight %}

The output for **NumericTextBox** with Globalization.

![](/angular/NumericTextbox/Globalization-Support_images/Globalization-Support_img1.png)

NumericTextBox with de-DE locale
{:.caption}

![](/angular/NumericTextbox/Globalization-Support_images/Globalization-Support_img2.png)

NumericTextBox with en-US locale
{:.caption}