---
layout: post
title: Exporting-the-Digital-Gauge
description: exporting the digital gauge
platform: Angular
control: Digital Gauge
documentation: ug
---

# Exporting the Digital Gauge

**Digital Gauge** has an exporting feature where **Gauge** control is converted into image format and then exported to client-side. The method API **exportImage** exports the **Digital Gauge**. It has two arguments such as **file****name** and **file format**. For exporting, you can refer the following code example.

{% highlight html %}

<ej-digitalgauge id="DigitalGauge1"[items]="[textAlign: 'right', value: 'STOP'}]">
</ej-digitalgauge>

<button id="btnSubmit">Export</button>
<div id=" fileName ">FileName </div>
<div id=" fileFormat ">FileFormat </div>
<select id="fileFormat">
    <option value="JPEG">JPEG</option>
    <option value="PNG">PNG</option>
</select>

{% endhighlight %}

{% highlight javascript %}

     $(function () {
        $("#btnSubmit").ejButton({ width: "50px", text: "Export", click: "buttonclickevent", });
        $("#fileFormat").ejDropDownList({ selectedItemIndex: 0, width: "115px" });
        $("# DigitalGauge1").ejDigitalgauge({ value: "Syncfusion" });
    });
    $("# DigitalGauge1").ejDigitalGauge("exportImage", "Digital", "JPEG");
    function buttonclickevent() {
        var FileName = $("#fileName").val();
        var FileFormat = $("#fileFormat").ejDropDownList("option", "value");
        var flag = $("#DigitalGauge1").ejDigitalGauge("exportImage", FileName, FileFormat);
        if (!flag)
            alert("Sorry for the inconvenience. Export is currently not supported in Internet Explorer 9 and below version");
    }


{% endhighlight %}

Execute the above code examples to render the **Digital****Gauge** as follows.

![](Exporting-the-Digital-Gauge_images/Exporting-the-Digital-Gauge_img1.png)

