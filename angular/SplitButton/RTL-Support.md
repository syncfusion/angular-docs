---
layout: post
title: RTL-Support
description: rtl support
platform: angular
control: Split Button
documentation: ug
---

# RTL Support

In some cases it is necessary to use right to left alignment. **RTL** support is provided by using **enableRTL** property. In **RTL** mode when there is more than one content (image/text, image/image) in **Split Button**, then the content is aligned in right to left format. For example, when text is in left and image is in right position, after applying right to left alignment these position are interchanged.

The following steps explains you the details about rendering the button with Right to left alignment support

In the **HTML** page, add the following button elements to configure **Split Button** widget.

{% highlight html %}

    <ej-splitbutton id="splitButton_rtl" [(enableRTL)]="rtl" target="#target" size="large" text="login" [(showRoundedCorner)]="showrounded" contentType="textandimage" prefixIcon="e-icon e-login"></ej-splitbutton>
    <ul id="target">
    <li><span>User</span></li>
    <li><span>Guest</span></li>
    <li><span>Admin</span></li>
    </ul> 
    <style>
    .spltspan {
        margin-left: 120px;
    }
    </style>

{% endhighlight %}


{% highlight html %}

import {Component} from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: './default.component.html',
})
export class DefaultComponent {
    rtl: boolean;
    showrounded: boolean;
    constructor() {
        this.rtl = true;
        this.showrounded = true;
    }
}

{% endhighlight %}

Execute the above code to render the following output.

![](/Angular/SplitButton/RTL-Support_images/RTL-Support_img1.png) 

