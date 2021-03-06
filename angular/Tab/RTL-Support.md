---
layout: post
title: RTL-Support
description: rtl support
platform: Angular
control: Tab
documentation: ug
---

# RTL Support

**Tab** control provides support for load contents in right to left format. This is achieved by setting [enableRTL](https://help.syncfusion.com/api/js/ejtab#members:enablertl) property to “**true**”.

The following code example is used to render the **Tab** element in RTL format. 

Add the following **HTML** to render **Tab** with **RTL** format.

{% highlight html %}

<ej-tab id="dishtype" [enableRTL]="true">
    <ul>
        <li><a href="#pizza">Pizza Menu</a></li>
        <li><a href="#sandwich">Sandwich Menu</a></li>
    </ul>
    <div id="pizza" style="background-color: #F5F5F5">
        <!--Food item description-->
        <p>Pizza cooked to perfection tossed with milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.</p>
    </div>
    <div id="sandwich" style="background-color: #F5F5F5">
        <!--dish description-->
        <p>Sandwich cooked to perfection tossed with bread, milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.</p>
    </div>
</ej-tab>

{% endhighlight %}

The following screenshot illustrates the **Tab** with **RTL** format.

![](RTL-Support_images/RTL-Support_img1.png)