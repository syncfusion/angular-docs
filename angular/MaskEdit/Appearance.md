---
layout: post
title: Appearance
description: appearance
platform: Angular
control: MaskEdit
documentation: ug
---

# Appearance

## Theme

The **MaskEdit** control’s style and appearance can be controlled based on CSS classes. In order to apply styles to the **Textbox** control, you need to refer 2 files namely, **ej.widgets.core.min.css** and **ej.theme.min.css**. If the file **ej.widgets.all.min.css** is referred, then it is not necessary to include the files **ej.widgets.core.min.css** and **ej.theme.min.css** in your project**,** as **ej.widgets.all.min.css** is the combination of these two. 

By default, there are 12 themes support available for **MaskEdit** control namely:

* default-theme
* flat-azure-dark
* fat-lime
* flat-lime-dark
* flat-saffron
* flat-saffron-dark
* gradient-azure
* gradient-azure-dark
* gradient-lime
* gradient-lime-dark
* gradient-saffron
* gradient-saffron-dark

## CSS Class

The **CSS** can be customized by using the **cssClass** in the **MaskEdit**. You can customize the **MaskEdit** with **cssClass** property to appear like your desired control.

The following steps explain the implementation of MaskEdit with **cssClass** property.

In the HTML page, add a &lt;div&gt; element to render the MaskEdit widget.  

{% highlight html %}

<input id="maskedit" ej-maskedit [value]="value" [maskFormat]="format" [cssClass]="customCss" [inputMode]="inputMode" />
    
{% endhighlight %}

{% highlight html %}

import { Component, ViewEncapsulation } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'src/maskedit/maskedit.component.html',
  styleUrls: ['app/maskedit/maskedit.component.css'],
  encapsulation: ViewEncapsulation.None 
})
export class MaskEditComponent {
    public value: number;
    public format: any;
    public inputMode: any;
    constructor() {
        this.value = 4242422424;
        this.format = "99 999-99999";
        this.inputMode = ej.InputMode.Text;
    }
}

{% endhighlight %}


Customize the CSS properties in custom CSS class.

{% highlight css %}

.customCss .e-box {
    border-color: #9d241b;
}
.customCss .e-input {
    background-color: #f6db8d;            
}
.customCss .e-select {
    background-color: #ecf6ac;
    border-color: #3c36e7;
}

{% endhighlight %}

The output for MaskEdit after applying **cssClass** is as follows.

![](/angular/MaskEdit/Appearance_images/Appearance_img1.png)

## Rounded Corner Support

MaskEdit provides you with rounded corner support whose appearance is different from normal textbox controls.

The following steps explain the implementation of MaskEdit with **showRoundedCorner** property.

In the HTML page, add a &lt;div&gt; element to render the MaskEdit widget. 

{% highlight html %}

<input id="maskedit" ej-maskedit [value]="value" [maskFormat]="format" 
[showRoundedCorner]="true" [inputMode]="inputMode" />
    
{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'src/maskedit/maskedit.component.html'
})
export class MaskEditComponent {
    public value: number;
    public format: any;
    public inputMode: any;
    constructor() {
        this.value = 123456;
        this.format = "99 999-99999";
        this.inputMode = ej.InputMode.Text;
    }
}

{% endhighlight %}

Output of MaskEdit when **showRoundedCorner** is “**true**”.

![](/angular/MaskEdit/Appearance_images/Appearance_img2.png)

## WatermarkText Support

The **MaskEdit** control provide water mark text support. You can display the initial value in the control by water mark.

The following steps explain the implementation of MaskEdit with **watermarkText** property.

In the HTML page, add a &lt;div&gt; element to render the MaskEdit widget.

{% highlight html %}

<input id="maskedit" ej-maskedit [name]="name" [maskFormat]="format" 
[watermarkText]="watermarkText" [inputMode]="inputMode" />
    
{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'src/maskedit/maskedit.component.html'
})
export class MaskEditComponent {
    public name: string;
    public format: any;
    public inputMode: any;
    public watermarkText: string;
    constructor() {
        this.name = "mask";
        this.format = "99 999-99999";
        this.inputMode = ej.InputMode.Text;
        this.watermarkText = "Enter the Mask";
    }
}

{% endhighlight %}

Output of MaskEdit when **waterMarkText** is “**true**”.


![](/angular/MaskEdit/Appearance_images/Appearance_img3.png)

## Text Alignment Support

The **MaskEdit** provides text alignment support that allows you to set the alignment of text in the control by using the **textAlign** property.

The following steps explain the implementation of MaskEdit with **textAlign** property.

In the HTML page, add a &lt;div&gt; element to render the MaskEdit widget

{% highlight html %}

<input id="maskedit" ej-maskedit [name]="name" [maskFormat]="format" [textAlign]="textAlign" 
[inputMode]="inputMode" />
    
{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'src/maskedit/maskedit.component.html'
})
export class MaskEditComponent {
    public name: string;
    public format: any;
    public inputMode: any;
    public textAlign: any;
    constructor() {
        this.name = "mask";
        this.format = "99 999-99999";
        this.inputMode = ej.InputMode.Text;
        this.textAlign = ej.TextAlign.Right;
    }
}

{% endhighlight %}

The output for Textboxes when **textAlign** is set to **“right”**.

![](/angular/MaskEdit/Appearance_images/Appearance_img4.png)