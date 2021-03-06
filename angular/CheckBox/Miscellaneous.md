---
layout: post
title: Miscellaneous
description: miscellaneous
platform: Angular
control: CheckBox
documentation: ug
---

# Miscellaneous

## Checkbox Id

**Checkbox** id is not displayed in user interface. Here, **id** mentions the id attribute of the root element of **Checkbox** control. When you assign a value for **id** property, then this older id is replaced by new id. This id value should be unique. 

Set id for **Checkbox** control as follows.

{% highlight html %}

    <table width="600px">
    <tr>
        <td> Checkboxes </td>
        <td>
            <ej-checkbox type="checkbox" class="nodetext" id="check1" [(id)]="id"></ej-checkbox></td>
    </tr>
    </table>

{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: './default.component.html',
})
export class DefaultComponent {
    id:string;
    constructor() {
        this.id="sync";
    }
}

{% endhighlight %}

## Checkbox Id Prefix

Id prefix value is the one that is appended to id value. It is used to mention the prefix for the wrapper’s id attribute. When you assign a value for **idPrefix** property, the older prefix id is replaced by new prefix id. 

Set prefix id for **Checkbox** control as follows.

  {% highlight html %}

       <table width="600px">
    <tr>
        <td> Checkboxes </td>
        <td>
            <ej-checkbox type="checkbox" class="nodetext" id="check1" [(idPrefix)]="idPrefix"></ej-checkbox></td>
    </tr>
    </table>

{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: './default.component.html',
})
export class DefaultComponent {
    idPrefix:string;
    constructor() {
        this.idPrefix="JS";
    }
}

{% endhighlight %}

## Checkbox Name

The name attribute is used to identify from data after it is submitted to the server, or to reference from data using **Angular** on the client side. **Checkbox** also contains name attribute. This name should be a unique one. It is used to receive the **Checkbox** value. Without using name, you can’t get the particular checkbox values at the time of submitting form.

## Checkbox Value

For **Checkboxes**, the contents of the value property do not appear in the user interface. The value property contains only a meaning when submitting a form. When a Checkbox is in checked state and when the form is submitted, the name of the **Checkbox** is sent along with the value of the value property (When the checkbox is not checked, no information is sent).

You can set name and value for **Checkbox** control as follows.

{% highlight html %}

    <table width="600px">
    <tr>
        <td> Checkboxes </td>
        <td>
            <ej-checkbox type="checkbox" class="nodetext" id="check1" [(name)]="name" [(value)]="value"></ej-checkbox></td>
    </tr>
    </table>

{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: './default.component.html',
})
export class DefaultComponent {
    value: string;
    name: string;
    constructor() {
        this.value = "received";
        this.name = "Conformation";
    }
}

{% endhighlight %}




