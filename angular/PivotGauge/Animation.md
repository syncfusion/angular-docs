---
layout: post
title: Animation
description: animation
platform: js
control: PivotGauge
documentation: ug
api: /api/js/ejpivotgauge
---

# Animation

The animation option makes the pointer to rotate from minimum value to actual value with animation effects.  Animation could be enabled/disabled by using the [`enableAnimation`](/api/angular/ejcirculargauge#members:enableanimation) property.  Speed of the pointer could be controlled by using the [`animationSpeed`](/api/angular/ejcirculargauge#members:animationspeed) property. Time is represented in milliseconds.

{% highlight html %}
<ej-pivotgauge [enableAnimation]="true" [animationSpeed]=1000>
</ej-pivotgauge>

{% endhighlight %}
