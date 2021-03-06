---
layout: post
title: Using Essential Angular Chart in real-time scenario 
description: Learn how to update the chart dynamically with real-time data. 
platform: Angular
control: Chart
documentation: ug
---

# Real-Time Chart 

Chart can be updated dynamically with the real time data. Whenever you add a point or remove a point from the dataSource, you can call the `redraw` method to request the chart to redraw its content.    

N> You can get the chart **instance** using instance method.

{% highlight html %}

<!--Rendering empty Chart without data-->
<ej-chart id="chartcontainer"
      <e-seriescollection>
        <e-series>
 	       <e-points>
           </e-points>
    	</e-series>
      </e-seriescollection>> 
</ej-chart>

   <script>

    //Using set interval to update chart dynamically
    window.setInterval(updateChart, 200);

    //Function that updates chart dynamically
    function updateChart(){

        //Creating chart instance
        var chart =  $("#chartcontainer").ejChart("instance");      
        
        if (chart.model.series[0].points.length > 10)
               chart.model.series[0].points.splice(0, 1);
        
        var point = chart.model.series[0].points;
        var xValue = point.length > 0 ? point[point.length - 1].x + 1 : 1;
        point[point.length] = { x:  xValue, y: getRandomNum( 1000 ) }
                
        //Update Chart dynamically using redraw option
        //chart.redraw() can also be used here instead of redraw option
        $("#chartcontainer").ejChart("redraw");      
       }
   
   </script>
{% endhighlight %}

[Click](http://js.syncfusion.com/demos/web/#!/azure/chart/live) here to view the online demo sample for real-time Chart.


