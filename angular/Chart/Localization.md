---
layout: post
title: Localization of Essential Angular Chart
description: Learn how to localize chart based on a specific culture.
platform: Angular
control: Chart
documentation: ug
---

# Localization

EjChart supports localization for its axis labels and tooltip. To render the chart with specific culture you have to refer the corresponding **globalize** culture script and need to specify the culture name in [`locale`] property of chart.   

{% highlight html %}


<head> 
<!--Refer french globalize culture script-->
<script src="../scripts/cultures/globalize.culture.fr-FR.min.js"></script>
</head>

<body>
    <ej-chart id="chartcontainer" locale='fr-FR'>
    </ej-chart>
</body>


{% endhighlight %}

![](Localization_images/Localization_img1.png)

[Click](http://js.syncfusion.com/demos/web/#!/azure/chart/chartcustomization/localization) here to view the localization chart online demo sample.


