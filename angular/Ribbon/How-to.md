---
layout: post
title:  Get-Ribbon-object
description: get ribbon object
documentation: ug
platform: angular
keywords: get ribbon object
api: /api/angular/ejribbon
---

# How to

## Get Ribbon object

After Ribbon initialization, Ribbon object is stored in a container element of Ribbon and it can be accessed for further processing. 

{% highlight javascript %}

    // "defaultRibbon" is Id of Ribbon control
    var ribbonObject = $("#defaultRibbon").ejRibbon("instance");

      [or]

    var ribbonObject = $("#defaultRibbon").data("ejRibbon");

{% endhighlight %}



