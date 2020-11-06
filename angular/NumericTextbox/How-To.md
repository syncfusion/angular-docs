---
layout: post
title: How to
description: how to
platform: Angular
control: NumericTextbox
documentation: ug
---

# How To

## Use Normal Textboxes as Syncfusion textboxes

In an application or a web page, you may use normal textboxes along with other Syncfusion components, since there is no separate Essential JavaScript plugin for textboxes.

So, you may want to make a normal textbox to look like Syncfusion textbox in order to achieve uniform look and appearance in your web page.

This can be achieved by adding **“e-textbox”** class to the HTML element.

By adding this class, the textbox will have standard look and appearance as other components for all the themes supported by Syncfusion.

{% highlight html %}

<input type="text" class="e-textbox" [value]="value"/>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'src/numerictextbox/numerictextbox.component.html'
})
export class NumericTextboxComponent { 
    public value: any;
    constructor() {
        this.value = "This is a normal Textbox";
    }
}

{% endhighlight %}

Textbox will be rendered as shown below.

![](/angular/NumericTextbox/How-to_images/normaltextbox_customize.png) 

Normal textbox as Syncfusion textbox
{:.caption}